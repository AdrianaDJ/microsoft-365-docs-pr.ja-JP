---
title: Office 365 シナリオで ExpressRoute の BGP コミュニティを使用する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Azure ExpressRoute で BGP コミュニティを使用して、Office 365 シナリオの IP プレフィックスと必要な帯域幅の数を管理する方法について説明します。
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692069"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Office 365 シナリオで ExpressRoute の BGP コミュニティを使用する

Azure ExpressRoute を使用した Office 365 への接続は、Office 365 エンドポイントが展開されているネットワークを表す特定の IP サブネットの BGP 広告に基づいています。 Office 365 のグローバルな性質と、Office 365 を構成するサービスの数により、多くの場合、お客様はネットワークで受け入れる広告を管理する必要があります。 IP サブネットの数を減らす。この記事の残りの部分では IP プレフィックスと呼ばれ、BGP ネットワーク管理の用語と整合するために、次のようなお客様の目標を達成しています。
  
- 承認された**ip プレフィックスの数を管理**する-限られた数の ip プレフィックスのみをサポートする内部ネットワークインフラストラクチャまたはネットワークキャリアを備えているお客様と、制限付き番号の上にプレフィックスを受け付けるように料金を与えるネットワークキャリアを持つお客様は、365ネットワークに既にアドバタイズされているプレフィックスの合計数を評価して、

- **Azure ExpressRoute 回線で必要な帯域幅の量を管理** する-お客様は、ExpressRoute のパスとインターネットパスを介して Office 365 サービスの帯域幅エンベロープを制御する必要がある場合があります。 これにより、お客様は Skype for Business などの特定のアプリケーションに対して ExpressRoute の帯域幅を予約し、残りの Office 365 アプリケーションをインターネットパスを介してルーティングすることができます。

このような目標をお客様に提供するために、次の例に示されているように、Office 365 のサービス固有の BGP community 値を使用してタグ付けされています。
  
> [!NOTE]
> 他のアプリケーションに関連付けられているネットワークトラフィックは、コミュニティの値に含まれていることが予想されます。 これは、共有サービスとデータセンターを使用したサービスとしてのグローバルソフトウェアに想定される動作です。 これは、上の2つの目的で、プレフィックスの数や帯域幅を考慮することで最小化されています。

|**サービス**|**BGP コミュニティの値**|**メモ**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Exchange および EOP サービスが含まれています。\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business Online & Microsoft Teams サービス  <br/> |
|その他の Office 365 サービス\*  <br/> |12076:5100  <br/> |Azure Active Directory (認証およびディレクトリ同期のシナリオ) と Office 365 ポータルサービスが含まれています。  <br/> |
|\* ExpressRoute に含まれるサービスシナリオの範囲については、「 [Office 365 エンドポイント](https://aka.ms/o365endpoints) 」の記事に記載されています。  <br/> \*\*今後、追加サービスと BGP コミュニティの値を追加することができます。 [BGP コミュニティの現在の一覧を参照してください](https://azure.microsoft.com/documentation/articles/expressroute-routing/)。  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>BGP コミュニティを使用するための最も一般的なシナリオは何ですか。

お客様は、BGP コミュニティを使用して、Azure ExpressRoute を介してネットワークに受け入れられる IP プレフィックスのグループを規制することができます。そのため、特定の Office 365 サービスの合計 IP プレフィックス数と予想帯域幅エンベロープに影響します。 すべての Office 365 で、Azure ExpressRoute または BGP コミュニティの使用に関係なく、インターネットにバインドされたトラフィックが必要になることを理解しておくことが重要です。 この機能は、次の3つのシナリオで最も一般的に使用されます。
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>シナリオ 1: Office 365 IP プレフィックスの数を最小限に抑える

Contoso Corporation は、現在 Office 365 を使用して Exchange Online と SharePoint Online を使用している5万の個人企業です。 「ExpressRoute の要件を確認する」では、Contoso 社のネットワークデバイスでは、多くの地域の場所にあるルーティングテーブルのサイズを処理できません100追加のルートエントリ。 Contoso 社のレビュー ExpressRoute が Office 365 サービスの完全なセットに対して提供する IP プレフィックスの合計数です。これは100を超えたことを示しています。 100の追加ルートエントリの下に留まるため、Contoso 社は、Office 365 用の ExpressRoute の使用を、ExpressRoute Microsoft ピアリング経由で受信した SharePoint Online BGP community value (12076:5020) だけに範囲を置いています。

|**使用される BGP コミュニティタグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネットルート**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; の OneDrive For business  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべての Office 365 サービス  <br/>  その他のすべての Microsoft クラウドサービス  <br/>  Office 365 ポータル、Office 365 認証、 &amp; ブラウザーの office  <br/>  Exchange Online、Exchange Online Protection、および Skype for Business Online  <br/> |

> [!NOTE]
> 各サービスに対してより低いプレフィックス数を実現するために、サービス間で最小限の重複が保持されます。 この動作は仕様です。
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>シナリオ 2: 特定の Office 365 サービスに対して ExpressRoute および内部帯域幅を使用する場合

分散異種ネットワークを使用する大規模な多国籍企業の Fabrikam Inc は、多くの Office 365 サービスのサブスクライバーです。これには以下が含まれます。Exchange Online、SharePoint Online、Skype for Business Online。 Fabrikam の内部ルーティングインフラストラクチャは、ルーティングテーブルで数千の IP プレフィックスを処理できます。ただし、Fabrikam は、ネットワークパフォーマンスに最も敏感で、その他すべての Office 365 アプリケーションで既存のインターネット帯域幅を使用する Office 365 アプリケーションに対して、ExpressRoute と内部帯域幅をプロビジョニングすることのみを希望しています。
  
そのため、Fabrikam は Azure ExpressRoute 帯域幅を、ExpressRoute Microsoft ピアリング経由で受信した Skype for Business Online BGP Community 値12076:5030 にのみスコープします。 Office 365 に関連付けられている残りのネットワークトラフィックでは、引き続きインターネット出口ポイントが使用されます。

|**使用される BGP コミュニティタグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネットルート**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Skype SIP 信号、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべての Office 365 サービス  <br/>  その他のすべての Microsoft クラウドサービス  <br/>  Office 365 ポータル、Office 365 認証、 &amp; ブラウザーの office  <br/>  Skype for Business テレメトリ、Skype クライアントのクイックヒント、パブリック IM 接続  <br/>  Exchange Online、Exchange Online Protection、および SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>シナリオ 3: Office 365 サービス用にのみ Azure ExpressRoute のスコープを限定する

Woodgrove Bank は、Office 365 を含むいくつかの Microsoft クラウドサービスのお客様です。 ネットワーク容量と消費を評価した後、Woodgrove Bank は、サポートされている Office 365 サービスの優先パスとして Azure ExpressRoute を展開することを決定します。 ルーティングテーブルは、すべての Office 365 IP プレフィックスと、プロビジョニングされた Azure ExpressRoute のすべてのセットをサポートできます。すべての予測される帯域幅と待機時間のニーズがサポートされます。
  
Office 365 以外の Microsoft cloud services に関連付けられているネットワークトラフィックを確実にするために、Woodgrove Bank は office 365 の ExpressRoute を office 365 固有の BGP community 値、12076:5010、12076:5020、12076:5030、12076:5100 にタグ付けされたすべての IP プレフィックスに適用します。

|**使用される BGP コミュニティタグ**|**Azure ExpressRoute 経由でルーティング可能な機能**|**必要なインターネットルート**|
|:-----|:-----|:-----|
|Exchange、Skype for Business & Microsoft Teams、SharePoint、 &amp; その他のサービス  <br/> (12076:5010、12076:5020、12076:5030、12076:5100)  <br/> |Exchange Online &amp; Exchange Online Protection  <br/> SharePoint Online &amp; の OneDrive For business  <br/> Skype SIP 信号、ダウンロード、音声、ビデオ、デスクトップ共有  <br/> Office 365 ポータル、Office 365 認証、 &amp; ブラウザーの office  <br/> | DNS、CRL、 &amp; CDN 要求  <br/>  Azure ExpressRoute で特にサポートされていないその他のすべての Office 365 サービス  <br/>  その他のすべての Microsoft クラウドサービス  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>BGP コミュニティを使用するための主要な計画に関する考慮事項

お客様が BGP コミュニティを利用して、ExpressRoute を宣伝してお客様のネットワーク経由で伝達する方法に影響を与える場合は、以下の点を考慮してください。
  
- ネットワーク設計で BGP コミュニティを使用する場合は、ルート対称が引き続き維持されることが重要です。 場合によっては、BGP コミュニティの追加または削除によって、対称ルーティングが中断され、対称ルーティングを再確立するために、ルーティング構成を更新する必要があります。

- BGP community の値で Azure ExpressRoute のスコープを指定することは、顧客のアクションです。 Microsoft は、顧客によって構成されたスコープに関係なく、ピアリング関係に関連付けられているすべての IP プレフィックスを通知します。

- Azure ExpressRoute は、お客様が割り当てられた BGP コミュニティに基づく Microsoft のネットワーク上でのアクションをサポートしていません。

- Office 365 で使用される IP プレフィックスは、サービス固有の BGP コミュニティ値でのみマークされています。場所固有の BGP コミュニティはサポートされていません。 Office 365 サービスはグローバルな性質を持っているため、テナントの場所または Office 365 クラウド内のデータに基づくフィルター処理プレフィックスはサポートされていません。 推奨される方法は、要求している Office 365 サービスの物理的な場所に関係なく、ユーザーのネットワーク上の場所から Microsoft グローバルネットワークへの最短または最も優先されるネットワークパスを調整するようにネットワークを構成することです。

- 各 BGP community 値に含まれる IP プレフィックスは、値に関連付けられた Office 365 アプリケーションの IP アドレスを含むサブネットを表します。 場合によっては、複数の Office 365 アプリケーションがサブネット内に複数の IP アドレスを持ち、その結果、IP プレフィックスが複数のコミュニティ値に存在することがあります。 これは、割り当ての断片化が原因であると想定されていますが、プレフィックス数や帯域幅管理の目標に影響を与えることはありません。 Office 365 の BGP コミュニティを活用して影響を最小限に抑えるには、「必要な機能を拒否する」を使用するのではなく、「必要な機能を許可する」というアプローチを使用することをお勧めします。

- BGP コミュニティを使用しても、基盤となるネットワーク接続の要件や、Office 365 を使用するために必要な構成は変更されません。 Office 365 にアクセスする必要があるお客様は、引き続きインターネットにアクセスできるようにする必要があります。

- BGP コミュニティによる Azure ExpressRoute の範囲指定は、内部ネットワークが Microsoft ピアリング関係を介して参照できるルートにのみ影響します。 スコープルーティングと共に、PAC または WPAD 構成の使用など、追加のアプリケーションレベルの構成を行う必要がある場合があります。

- Microsoft によって割り当てられた BGP コミュニティを使用することに加えて、お客様は、内部ルーティングに影響を与えるために Azure ExpressRoute で学んだ Office 365 の IP プレフィックスに独自の BGP コミュニティを割り当てることもできます。 一般的なユースケースとしては、特定の ExpressRoute ピアの場所で学習したすべてのルートに、場所ベースの BGP コミュニティを割り当て、顧客ネットワークの下流の情報を使用して、Microsoft のネットワークで最短または最も優先されるネットワークパスを調整します。 Office 365 シナリオで ExpressRoute を使用して、顧客が割り当てられている BGP コミュニティを使用することは、Microsoft control または visibility の範囲外です。

次の短いリンクを使用して、に戻ることができ [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) ます。
  
## <a name="related-topics"></a>関連トピック

[Office 365 ネットワーク接続の評価](assessing-network-connectivity.md)
  
[Office 365 向け Azure ExpressRoute](azure-expressroute.md)
  
[Office 365 向け ExpressRoute の管理](managing-expressroute-for-connectivity.md)
  
[Office 365 向け ExpressRoute でのルーティング](routing-with-expressroute.md)
  
[Office 365 向け ExpressRoute でのネットワーク計画](network-planning-with-expressroute.md)
  
[Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Skype for Business Online での ExpressRoute および QoS](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[ExpressRoute を使用したコール フロー](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365 向け ExpressRoute の実装](implementing-expressroute.md)
  
[BGP コミュニティのサポート](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング](performance-tuning-using-baselines-and-history.md)
  
[Office 365 のパフォーマンスに関するトラブルシューティングの計画](performance-troubleshooting-plan.md)
  
[Azure ExpressRoute for Office 365 のトレーニング](https://channel9.msdn.com/series/aer)
