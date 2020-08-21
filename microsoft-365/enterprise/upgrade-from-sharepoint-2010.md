---
title: SharePoint 2010 からのアップグレード
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: 2020年10月13日の両方のエンドのサポートとして、SharePoint 2010 および Sharepoint Server 2010 からアップグレードするための情報とリソースを見つけます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 57e44cf14a74f6a5a2098512e0a2339037d70655
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691613"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010 からのアップグレード

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2010 と SharePoint Server 2010 は **、2021年4月 13**日にサポート終了になります。 この記事では、既存の SharePoint Server 2010 データを Microsoft 365 の SharePoint Online に移行したり、オンプレミスの SharePoint Server 2010 環境をアップグレードしたりするのに役立つリソースについて説明します。
  
## <a name="what-is-end-of-support"></a>サポート終了とは

SharePoint Server 2010 と SharePoint Foundation 2010 ソフトウェアがサポートライフサイクルの最後に達すると (Microsoft が新機能、バグ修正プログラム、セキュリティ修正プログラムを提供する時間)、これはソフトウェアの "サポート終了" と呼ばれるか、場合によっては ' 定年 "と呼ばれます。 製品のサポート終了 (または EOS) によって、実際には機能しなくなります。ただし、ソフトウェアのサポートが終了すると、Microsoft は次の機能を提供しなくなります。
  
- 発生する可能性のある問題のテクニカル サポート。
    
- サーバーの安定性と運用に影響を与える可能性のある問題が検出された場合のバグ修正プログラム。
    
- 検出された脆弱性に対するセキュリティの修正。これにより、サーバーがセキュリティ侵害に対して脆弱になる可能性があります。
    
- タイム ゾーンの更新。
    
つまり、これ以降の更新プログラム、修正プログラム、修正プログラムが製品に提供されることはありません (セキュリティ更新プログラムや修正プログラムを含む)。また、Microsoft サポートは、そのサポートの努力をより新しいバージョンに完全に移行する予定です。 SharePoint Server 2010 の方法をサポートしていない場合は、製品をアップグレードしたり、重要なデータを移行したりする前に、不要になったデータをトリミングする機会を活用する必要があります。
  
> [!NOTE]
> 通常、ソフトウェアライフサイクルは製品の最初のリリースから10年後に持続します。 次のバージョンのソフトウェア、または Microsoft 365 移行 (またはその両方) にアップグレードするのに役立つ、 [microsoft ソリューションプロバイダ](https://go.microsoft.com/fwlink/?linkid=841249) を検索できます。 特に、SharePoint で使用している SQL Server のバージョンによっては、重要な基礎テクノロジに対するサポート終了日について認識していることを確認してください。 製品ライフサイクルの詳細については、「 [固定ライフサイクルポリシー](https://support.microsoft.com/help/14085) 」を参照してください。
  
## <a name="what-are-my-options"></a>使用できるオプション

最初に、 [製品ライフサイクルサイト](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)でサポートが終了する日付を確認します。 次に、この日付に関する知識を使用して、アップグレードまたは移行の時間を計画してください。 ご使用の製品は、リストされている日付には機能しなく  *なり*  ますが、使用を続行できますが、インストールにはその日付以降にパッチを適用する必要がないため、製品の次のバージョンによりスムーズに移行できるようにする戦略が必要になります。 
  
このマトリックスは、製品の機能やユーザーデータを移行する際に、コースをプロットするのに役に立ちます。
  
| サポート終了製品 | 中 | 高 |
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013 (社内)  <br/> |SharePoint Online  <br/> |
||Sharepoint Server 2013 と SharePoint Online のハイブリッド  <br/> |SharePoint Server 2016 (社内)  <br/> |
| | |SharePoint クラウドハイブリッド検索  <br/> |
   
小数点部桁数 (良好なオプション) でオプションを選択する場合は、SharePoint Server 2010 からの移行後すぐに、もう一度アップグレードの計画を開始する必要があります。 

SharePoint Server 2010 のサポート終了を回避するために実行できる3つのパスを次に示します。

![SharePoint Server 2010 のアップグレードパス](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

>[!Note]
>SharePoint Server 2010 および SharePoint Foundation 2010 のサポート終了が2021年4月13日に予定されていますが、最新の日付については常に[製品ライフサイクルサイト](https://support.microsoft.com/lifecycle)をチェックする必要があることに*注意してください*。
>

  
## <a name="where-should-i-go-next"></a>次にどこに行くべきですか。

SharePoint Server 2013 と SharePoint Foundation 2013 は、オンプレミスのサーバーにインストールすることができます。 それ以外の場合は、Microsoft Microsoft 365 の一部であるオンラインサービスである SharePoint Online を使用できます。 次のいずれかを選択できます。
  
- SharePoint Online への移行
    
- オンプレミスの SharePoint Server または SharePoint Foundation のアップグレード
    
- 上記の両方の実施
    
- [SharePoint ハイブリッド](https://docs.microsoft.com/sharepoint/hybrid/hybrid) ソリューションの実装 
    
サーバーファームの保持、カスタマイズの維持または移行、および SharePoint Server が依存するハードウェアのアップグレードに関連する非表示のコストに注意してください。 これらのすべてについて把握しておくと、オンプレミスのアップグレードを続行するのが容易になります。 それ以外の場合は、カスタマイズされていない従来の SharePoint サーバーでファームを実行すると、SharePoint Online への計画された移行の恩恵を受けることができます。 オンプレミスの SharePoint Server 環境では、すべてのデータをオンプレミスで保持するハードウェア管理の量を減らすために、SharePoint Online に何らかのデータを配置することを選択することもできます。 データの一部を SharePoint Online に移動する方が経済的な場合があります。
  
> [!NOTE]
> SharePoint 管理者は、Microsoft 365 サブスクリプションを作成し、新しい SharePoint Online サイトをセットアップしてから、SharePoint Server 2010 から切断し、最新の SharePoint Online サイトに対して最も重要なドキュメントのみを削除することができます。 その後、残りのデータが SharePoint Server 2010 サイトからオンプレミスのアーカイブにドレインされる場合があります。 
  
|**SharePoint Online**|**オンプレミスの SharePoint Server**|
|:-----|:-----|
|時間コストが高い (計画 / 実行 / 確認)  <br/> |時間コストが高い (計画 / 実行 / 確認)  <br/> |
|資金コストが安い (ハードウェアの購入の必要なし)  <br/> |ファンドのコストが高くなる (ハードウェアの購入)  <br/> |
|一度の移行でのコスト  <br/> |将来繰り返される一度の移行でのコスト  <br/> |
|所有権および保守の費用合計が低い  <br/> |所有権および保守の費用合計が高い  <br/> |
   
Microsoft 365 に移行するときには、1回限りの移行にかかる時間が長くなります (データを整理したり、クラウドに取りかかることを決定したりする場合)。 ただし、データが移行されると、その時点からのアップグレードが自動的に行われ、ハードウェアおよびソフトウェアの更新プログラムを管理する必要がなくなります。また、ファームの稼働時間は、Microsoft サービスレベル契約 ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)) によって支えられます。
  
### <a name="migrate-to-sharepoint-online"></a>SharePoint Online への移行

SharePoint Online では、 [サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)を確認することにより、必要なすべての機能が提供されていることを確認してください。
  
現時点では、SharePoint Server 2010 (または SharePoint Foundation 2010) から SharePoint Online に直接移行する方法はありません。このため、作業の多くは手動で行います。 これにより、移行の前に、不要になったデータとサイトをアーカイブし、排除する機会が得られます。 他のデータをストレージにアーカイブすることができます。 また、サポート終了時に SharePoint Server 2010 と SharePoint Foundation 2010 のどちらも停止しないことに注意してください。したがって、管理者は、ユーザーがデータの移動を忘れた場合に、SharePoint が実行中の期間を持つことができます。
  
SharePoint Server 2013 または SharePoint Server 2016 にアップグレードし、データを SharePoint Online に配置する場合は、 [Sharepoint 移行 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (情報を OneDrive for business に移行するため) を使用して移動することもできます。 
  
|**SharePoint Online の利点**|**SharePoint Online の短所**|
|:-----|:-----|
|Microsoft が SPO ハードウェアおよびすべてのハードウェアの管理を行う。  <br/> |オンプレミスの SharePoint Server で利用できる機能と、SPO で利用できる機能が異なる。  <br/> |
|サブスクリプションの全体管理者であり、管理者を SPO サイトに割り当てることができます。  <br/> |オンプレミスの sharepoint Server でファーム管理者が使用できる一部のアクションは、Microsoft 365 の SharePoint 管理者ロールに存在しない (または必要ない)。ただし、SharePoint 管理、サイトコレクションの管理、サイト所有権は組織にとってローカルです。  <br/> |
|Microsoft は、基礎となるハードウェアおよびソフトウェア (SharePoint Online が実行されている SQL server を含む) に対するパッチ、修正、更新を適用します。  <br/> |サービスの基となるファイル システムへのアクセスがないため、一部のカスタマイズが制限される。  <br/> |
|Microsoft が[サービス レベル契約](https://go.microsoft.com/fwlink/?linkid=843153)を発行し、サービス レベルの問題に迅速に対応する。  <br/> |バックアップと復元、その他の回復オプションは、SharePoint Online のサービスによって自動化される。バックアップは、使用されていない場合に上書きされる。  <br/> |
|セキュリティ テストとサーバーのパフォーマンス チューニングは、Microsoft によって、継続的なサービスとして実施される。  <br/> |ユーザー インターフェイスとその他の SharePoint 機能の変更はサービスによってインストールされ、オン/オフの切り替えが必要な場合がある。  <br/> |
|Microsoft 365 は、さまざまな業界標準を満たしています。 [microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |移行の際に [FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) でできることが限られる。  <br/> アップグレードの多くは、手動か、[SharePoint Online と OneDrive 移行コンテンツ ロードマップ](https://go.microsoft.com/fwlink/?linkid=843184)に記載されている SPO 移行 API により実施される。  <br/> |
|Microsoft のサポート エンジニアもデータセンターの従業員も、ユーザーのサブスクリプションに対する無制限の管理アクセス権はない。  <br/> |新しいバージョンの SharePoint に対応するために、ハードウェア インフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリ ファームが必要な場合は、追加のコストがかかる可能性がある。  <br/> |
|ソリューションプロバイダーは、データを SharePoint Online に移行するための1回限りのジョブを支援します。  <br/> |SharePoint Online のすべての変更がコントロール内にあるわけではありません。 移行後、メニュー、ライブラリ、およびその他の機能の設計の違いが、一時的に利便性に影響する場合があります。  <br/> |
|オンライン製品は、サービスによって自動的に更新されますが、機能は廃止される可能性があります。ただし、サポートライフサイクルが実際に終了することはありません。  <br/> |SharePoint Server (または SharePoint Foundation) および基盤となる SQL server のサポート終了期間が終了しています。  <br/> |
   
新しい Microsoft 365 サイトを作成することを決定し、必要に応じてデータを手動で移行する場合は、 [microsoft 365 のオプション](https://www.microsoft.com/microsoft-365/)を参照してください。
  

  
### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

Sharepoint オンプレミス製品の最新バージョン (SharePoint Server 2019) の場合、SharePoint Server のアップグレードは  *直列*になる必要があります。これは、sharepoint server 2010 から sharepoint server 2016 または sharepoint 2019 に直接アップグレードすることはできません。 
  
シリアルアップグレードのパス: 

- Sharepoint server 2010 sharepoint server \> 2013 \> sharepoint server 2016
   
SharePoint 2010 から SharePoint Server 2016 への完全なパスを使用することを選択した場合、これには時間と計画が必要になります。 アップグレードには、アップグレードされたハードウェア (SQL server もアップグレードする必要があることに注意してください)、ソフトウェア、および管理に関するコストが関係しています。 また、カスタマイズをアップグレードしたり、破棄したりする必要がある場合もあります。 SharePoint Server ファームをアップグレードする前に、すべての重要なカスタマイズに関するメモを収集してください。
  
> [!NOTE]
> SharePoint 2010 ファームのサポート終了を維持し、新しいハードウェアに SharePoint Server 2016 ファームをインストールする (個別のファームを並行して実行する) ことができます。その後、コンテンツをダウンロードして再アップロードするために、コンテンツの手動による移行を計画して実行することができます (例:)。 これらの手動による移動 (2010 からのドキュメント、手動による移動を実行しているアカウントのエイリアスを使用して、現在最後に変更されたアカウントを含む) には、このような手動による移動には潜在的な落とし穴があります (サイト、サブサイト、アクセス許可、およびリスト構造を再作成します)。 ストレージに移動できるデータや、不要になったデータについては、十分に検討してください。 これにより、移行の影響が軽減されます。 どちらの方法でも、アップグレード前に環境をクリーンにします。 アップグレードする前に、既存のファームが機能していることを確認してください。 
  
以下の、**サポートされるアップグレード パスとサポート外のアップグレード パス**を確認してください。 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
**カスタマイズ**を行っている場合は、移行パスの手順ごとにアップグレードの計画を立てることが重要となります。詳細は以下を参照してください。 
  
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**オンプレミスの利点**|**オンプレミスの欠点**|
|:-----|:-----|
|サーバーハードウェア上の SharePoint ファーム (および SQL) のすべての側面を完全に制御します。  <br/> |すべてのブレークと修正は会社の責任になります (ただし、製品のサポートが終了していない場合は、有料の Microsoft サポートを受けられます)。  <br/> |
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。  <br/> |アップグレード、パッチ、セキュリティ修正、ハードウェアのアップグレード、および SharePoint Server の SQL ファームがオンプレミスで管理されています。  <br/> |
|SharePoint Online よりも詳細なカスタマイズオプションへのフルアクセス。  <br/> |[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165) は、オンプレミスで手動で構成する必要があります。  <br/> |
|オンプレミスで実行されるセキュリティテストとサーバーパフォーマンスの調整 (管理下)。  <br/> |Microsoft 365 では、オンプレミスの SharePoint Server と相互運用できない SharePoint Online の機能を使用することができます  <br/> |
|ソリューションプロバイダーは、SharePoint Server の次のバージョン (および以降) にデータを移行するのに役立ちます。  <br/> |SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 証明書が自動的に使用されることはない。  <br/> |
|オンプレミスの SharePoint Server での、名前付け規則、バックアップと復元、その他の回復オプションの完全なコントロール。  <br/> |オンプレミスの SharePoint Server は製品ライフサイクルに依存しています。  <br/> |
   
### <a name="upgrade-resources"></a>アップグレードのリソース

最初に、ハードウェア要件とソフトウェア要件を比較します。 現在のハードウェアでのアップグレードに関する基本的な要件を満たしていない場合は、まずファームまたは SQL サーバーのハードウェアをアップグレードする必要があります。または、サイトのパーセンテージを SharePoint Online の ' 永続 ' ハードウェアに移動することを決定することがあります。 評価が済んだら、サポートされているアップグレードパスと方法に従います。
  
- **ハードウェア/ソフトウェア要件**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **ソフトウェアの境界と制限**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **アップグレード プロセスの概要**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>Sharepoint Online とオンプレミスの sharepoint Server との間に SharePoint ハイブリッドソリューションを作成する

別の方法として、sharepoint Server 2013 または2016または2019ファームを sharepoint Online に接続して、sharepoint ハイブリッド [ソリューション](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)を作成することもできます (一部の移行ニーズについては、オンプレミスとオンラインの両方の環境に適している場合があります)。
  
ハイブリッド SharePoint Server ファームが移行目標であると判断した場合は、オンラインに移行するサイトとユーザーを計画し、オンプレミスのままにしておく必要があります。 この決定には、SharePoint Server ファームのコンテンツ (企業への高、中、または低レベルの影響を与えるデータを決定する) のレビューとランク付けを行うことができます。 SharePoint Online と共有する必要があるのは、(a) ログインのユーザーアカウントであり、(b) SharePoint Server 検索インデックスを使用しているかどうかによっては、サイトの使用方法を確認するまでわかりません。 後で会社がすべてのコンテンツを SharePoint Online に移行することを決定した場合は、残りのすべてのアカウントとデータをオンラインにして、オンプレミスのファームを使用停止にすることができ、その時点から Microsoft 365 コンソールを通じて SharePoint ファームの管理/管理が行われます。
  
既存のハイブリッドの種類と、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解しておいてください。

| オプション | 説明 |
|:-----|:-----|
|[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165)。  <br/> |移行の際に [FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) でできることが限られる。  <br/> アップグレードの多くは、手動か、[SharePoint Online と OneDrive 移行コンテンツ ロードマップ](https://go.microsoft.com/fwlink/?linkid=843184)に記載されている SPO 移行 API により実施される。  <br/> |
|Microsoft のサポート エンジニアもデータセンターの従業員も、ユーザーのサブスクリプションに対する無制限の管理アクセス権はない。  <br/> |新しいバージョンの SharePoint に対応するために、ハードウェア インフラストラクチャをアップグレードする必要がある場合や、アップグレードにセカンダリ ファームが必要な場合は、追加のコストがかかる可能性がある。  <br/> |
|パートナーが、SharePoint Online へのデータの移行を一度で行えるようにサポートできる。  <br/> ||
|オンライン製品に関しては、サービス全体における更新が自動的に行われる。機能は廃止になる可能性もあるが、サポート自体は継続する。  <br/> ||
   
新しい Microsoft 365 サイトを作成することを決定し、必要に応じてデータを手動で移行する場合は、 [microsoft 365 のオプション](https://www.microsoft.com/microsoft-365/)を参照してください。
  
### <a name="upgrade-sharepoint-server-on-premises"></a>オンプレミスの SharePoint Server のアップグレード

SharePoint のバージョンをスキップしてアップグレードする方法はありません。SharePoint Server 2016 のリリースの場合も同様です。アップグレードは以下のように順次に行われます。
  
- Sharepoint 2007 \> sharepoint server 2010 \> sharepoint server 2013 \> sharepoint server 2016
   
SharePoint 2007 から SharePoint Server 2016 へのパス全体を取得するには、多くの時間を要します。また、アップグレードされたハードウェア (SQL サーバーもアップグレードする必要があります)、ソフトウェア、管理に関するコストも発生します。機能の重要度に応じて、カスタマイズをアップグレードしたり、カスタマイズした内容を破棄したりする必要があります。
  
> [!NOTE]
> サポートが終了した SharePoint 2007 ファームの使用を継続し、新しいハードウェアに SharePoint Server 2016 ファームをインストールして (ファームが共存している状態で別々に実行)、コンテンツの手動による移行 (コンテンツのダウンロードや再アップロードなど) を計画したり実行したりすることは可能です。ただし、手動による移動 (最後に変更されたアカウントを、手動で移動するアカウントのエイリアスに置き換えたドキュメントの移動など) に関する問題には注意を払う必要があり、サイト、サブサイト、アクセス許可、リスト構造の再構成などの作業は早めに行う必要があります。ストレージに移行するデータと、必要ないデータを区別し、どういった操作が移行による負担を軽減できるのかを今検討することが非常に重要です。
  
いずれにしても、アップグレードする前に環境を整えることが重要です。アップグレードする前に既存のファームが機能していることを確認してください。使用を停止するものについても、念のため確認してください。 
  
以下の、**サポートされるアップグレード パスとサポート外のアップグレード パス**を確認してください。 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
**カスタマイズ**を行っている場合は、移行パスの手順ごとにアップグレードの計画を立てることが重要となります。詳細は以下を参照してください。 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**オンプレミスの利点**|**オンプレミスの欠点**|
|:-----|:-----|
|サーバー ハードウェアからの、SharePoint ファームの機能すべての完全なコントロール。  <br/> |下記の破損と修理のすべてが貴社の責任になる (製品のサポートが終了していない場合は、有料の Microsoft サポートの利用が可能)。  <br/> |
|ハイブリッドの SharePoint Online サブスクリプションにオンプレミス ファームを接続するオプションを備えた、オンプレミスの SharePoint Server のフル機能一式。  <br/> |オンプレミスに管理される SharePoint Server のアップグレード、パッチ、セキュリティ修正プログラム、およびすべての保守。  <br/> |
|高度なカスタマイズのためのフル アクセス許可。  <br/> |[Microsoft コンプライアンスサービス](https://go.microsoft.com/fwlink/?linkid=843165) は、オンプレミスで手動で構成する必要があります。  <br/> |
|オンプレミスで実行される、セキュリティ テストとサーバーのパフォーマンス チューニング (自分でコントロール)。  <br/> |Microsoft 365 では、オンプレミスの SharePoint Server と相互運用できない SharePoint Online の機能を使用することができます  <br/> |
|パートナーが、SharePoint Server の次のバージョン (さらにその先も対象) へのデータ移行をサポートできる。  <br/> |SharePoint Server サイトでは、SharePoint Online で表示される [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 証明書が自動的に使用されることはない。  <br/> |
|オンプレミスの SharePoint Server での、名前付け規則、バックアップと復元、その他の回復オプションの完全なコントロール。  <br/> |製品のライフサイクルによって、オンプレミスの SharePoint Server の機能が異なる。  <br/> |
   
### <a name="upgrade-resources"></a>アップグレードのリソース

ハードウェアとソフトウェアの要件を満たしていることを確認してから、サポートされているアップグレード方法に従って操作を行ってください。
  
- **ハードウェア/ソフトウェア要件**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **ソフトウェアの境界と制限**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **アップグレード プロセスの概要**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250) | [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251) | [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252) | [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online とオンプレミスの間で、SharePoint ハイブリッド ソリューションを作成する

オンプレミスでの完全コントロールでの移行か、SharePoint Online の低コストの所有権による移行かを検討している場合、SharePoint Server 2013 のファームあるいは 2016 のファームをハイブリッドとして、SharePoint Online に接続できます。[SharePoint ハイブリッド ソリューションの詳細情報](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
ハイブリッド SharePoint Server ファームにメリットがあると判断した場合は、既存のハイブリッドの種類と、オンプレミスの SharePoint ファームと Microsoft 365 サブスクリプションとの間の接続を構成する方法について理解しておく必要があります。
  
これがどのように機能するかを確認する方法の1つは、Microsoft 365 開発/テスト環境を作成することです。これは、 [テストラボガイド](m365-enterprise-test-lab-guides.md)を使用してセットアップできます。 試用版または購入済みの Microsoft 365 サブスクリプションを取得したら、SharePoint Online にサイトコレクション、web、およびドキュメントライブラリを作成して、データを移行できるようにします (手動で移行 API を使用するか、個人用サイトのコンテンツを OneDrive for Business に移行する場合は-ハイブリッドウィザードを経由します)。
  
> [!NOTE]
> ハイブリッドオプションを使用するには、SharePoint Server 2010 ファームをまず、オンプレミスの SharePoint Server 2013 または SharePoint Server 2016 にアップグレードする必要があることに注意してください。 Sharepoint Foundation 2010 および SharePoint Foundation 2013 は、SharePoint Online とのハイブリッド接続を作成できません。 

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 のクライアントおよびサーバーおよび Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![Office 2010 サーバー/クライアント サポート終了についての画像、 Windows 7 のポスター](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

この 1 ページのポスターで、Office 2010 サーバー/クライアント製品と Windows 7 がサポート終了に達してしまうことを防ぐさまざまな手段をすばやく理解できます。ここには、特に推奨される手段と、Microsoft365 Enterprise のオプション サポートが含まれます。

このポスターを [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/migration-microsoft-365-enterprise-workload/Office2010Windows7EndOfSupport.pdf) して、レター形式、リーガル形式、またはタブロイド形式 (11 x 17) で印刷することもできます。
        
## <a name="related-topics"></a>関連項目

[Office 2007 または2010サーバーおよびクライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)
  
[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)
  
[SharePoint 2010 から SharePoint 2013 へのアップグレードのベスト プラクティス](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)
  
[SharePoint 2013 でのデータベース アップグレードの問題のトラブルシューティング](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Microsoft ソリューションプロバイダーを検索してアップグレードに役立てる](https://go.microsoft.com/fwlink/?linkid=841249)
  
[更新された SharePoint 2013 製品サービス ポリシー](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)
  
[更新された SharePoint Server 2016 製品サービス ポリシー](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
  
