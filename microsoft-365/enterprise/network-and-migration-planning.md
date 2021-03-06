---
title: Office 365 のネットワークと移行の計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: この記事には、ネットワークの計画、テスト、Office 365 への移行に関する情報へのリンクが含まれています。
ms.openlocfilehash: 2b08b05b8863fd9351510878f9438264bb2999f5
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948450"
---
# <a name="network-and-migration-planning-for-office-365"></a>Office 365 のネットワークと移行の計画

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

この記事には、ネットワークの計画とテスト、および Office 365 への移行に関する情報へのリンクが記載されています。
  
Office 365 に初めて展開するか、Office に移行する前に、これらのトピックの情報を使用して必要な帯域幅を推定し、Office 365 に展開または移行するのに十分な帯域幅があるかどうかをテストして確認することができます。

この記事は [、Office 365 のネットワーク計画とパフォーマンスチューニング](https://aka.ms/tune)に含まれています。

Microsoft 365 およびその他の Microsoft クラウドプラットフォームおよびサービスに対してネットワークを最適化するための手順については、「 [エンタープライズアーキテクトのための Microsoft クラウドネットワーク](https://aka.ms/cloudarchnetworking) 」のポスターを参照してください。
   
## <a name="estimate-network-bandwidth-requirements"></a>ネットワーク帯域幅の要件を見積もる
<a name="EstimateBandwidthRequirements"> </a>

Office 365 を使用すると、組織のインターネット回線の使用率が向上する可能性があります。 Office 365 が完全に展開され、少なくとも20% の容量を維持している間に、使用可能な帯域幅の量が増加しているかどうかを判断することが重要です。
  
帯域幅を推定するには、次の手順を使用します。
  
1. 各インターネット出口を使用するクライアントの数を評価します。 Terabit ネットワークが可能な限り多くの接続を処理できるようにします。 
    
2. クライアントが使用できる Office 365 サービスと機能を決定します。 さまざまなサービスや利用状況のプロファイルを持つユーザーのグループが存在する可能性があります。
    
3. クライアントのパイロットグループに対するネットワークの使用を測定します。 パイロットクライアントが、組織内のユーザーのさまざまなプロファイルおよび地理的に異なる場所を代表するものであることを確認します。 [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)と[Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network)の従来の電卓、または自社のネットワークで実行した[ケーススタディ](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)に対して、結果をクロスチェックすることができます。 
    
4. ネットワークに変更を加える前に、パイロットグループの測定値を使用して、組織のニーズ全体を推定し、見積もりを検証するために再テストします。
    
## <a name="test-your-existing-network"></a>既存のネットワークをテストする
<a name="calculators"> </a>

 **ネットワークツール。** インターネット帯域幅をテストおよび検証して、ダウンロード、アップロード、および待機時間の制約を決定します。 これらのツールは、完全に展開された後と同様に、移行のためのネットワークの機能を決定するのに役立ちます。 
    
- [Microsoft リモート接続アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=517243): Exchange Online 環境での接続をテストします。
    
- Outlook および Office 365 の問題を修正するには、 [Microsoft Support And Recovery Assistant For Office 365](https://diagnostics.office.com/#/Download?env=SOC) を使用します。 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Office 365 のネットワーク計画と移行パフォーマンスの向上のためのベストプラクティス
<a name="BestPractices"> </a>

Office 365 の動作を向上させる方法の詳細については、これらのベストプラクティスをさらに掘り下げて説明します。
  
1. すぐにユーザーのサポートを開始する必要がありますか。 ネットワークが連携していない場合に、SharePoint Online、Exchange Online、Lync Online などの Office 365 を使用する際のヒントについては、「 [office 365 を低速ネットワークで使用するためのベストプラクティス](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 」を参照してください。 この記事では、Office 365 の動作を最適化するための TechNet および Support.office.com のコンテンツのロードについて説明し、web ページをカスタマイズする簡単な方法について説明します。また、最適な Office 365 環境に合わせて Internet Explorer 設定を設定する方法についても説明します。 
    
2. 「 [Office 365 のネットワーク接続の原則](https://aka.ms/o365networkingprinciples) 」を参照して、office 365 のトラフィックを安全に管理し、最適なパフォーマンスを得るための接続の原則について理解します。 この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。 
    
3. Windows 更新プログラムのスケジュールを慎重に管理することによって、メールの移行のパフォーマンスを向上させます。 クライアントコンピューターをバッチ処理で更新し、ネットワーク帯域幅の使用を制限するために Office 365 に移行する前にすべてのクライアントコンピューターが更新されるようにすることができます。 詳細については、「 [365 Office のデスクトップを手動で更新および構成する (最新の更新プログラム](https://support.microsoft.com/gp/office-2013-365-update))」を参照してください。
    
4. Office 365 のネットワークトラフィックは、信頼されたインターネットサービスとして扱われ、組織によっては、信頼されていないインターネットサービスへのネットワークトラフィックに関する、従来のフィルタリングやスキャンの多くをバイパスできるようになります。 これには、プロキシユーザー認証やパケット検査などの送信処理の削除に加えて、適切なネットワークアドレス変換 (NAT) を使用してインターネットへのローカル出口を保証し、増加したネットワーク要求を処理するのに十分な帯域幅容量を含めることが含まれます。 ネットワーク上の信頼されたインターネットサービスとして Office 365 を処理するようにネットワークを構成する方法の詳細については、「 [office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)」を参照してください。
    
1. [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)を確認します。 Office 365 に送られる追加のトラフィックは、送信プロキシ接続の増加と、TLS/SSL を介したセキュリティで保護されたトラフィックの増加につながります。
    
2. 送信プロキシでユーザー認証が必要な場合は、接続が遅くなったり、機能が失われたりすることがあります。 Office 365 ドメインの認証要件を省略すると、このオーバーヘッドを減らすことができます。
    
3. 多数の共有予定表とメールボックスがある場合、Outlook から Exchange への接続数が増加する可能性があります。 たとえば、Outlook クライアントは、使用されている共有予定表ごとに、最大2つの追加の接続を開くことができます。 このような状況では、出口プロキシが接続を処理できることを確認するか、Outlook 用 Office 365 への接続のプロキシをバイパスするようにします。
    
4. パブリック IP アドレスに対してサポートされるデバイスの最大数と、複数の IP アドレス間で負荷分散を行う方法を決定します。 詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。
    
5. ネットワーク上のコンピューターからの送信接続を調査している場合は、このフィルター処理を Office 365 ドメインにバイパスすると、接続性とパフォーマンスが向上します。 さらに、送信検査をバイパスすることで、単一のインターネット出口の必要性がなくなり、Office 365 の宛先のネットワーク要求に対してローカルのインターネット出口が有効になります。
    
6. 内部ネットワーク設定を見つけるお客様は、パフォーマンスに影響を与える場合があります。 最大転送単位 (MTU) サイズ、ネットワーク自動ネゴシエーションまたは自動検出、インターネットへのサブ最適なルートなどの設定は、よく見られる場所です。
    
## <a name="network-planning-reference-for-office-365"></a>Office 365 のネットワーク計画リファレンス
<a name="NetReference"> </a>

これらのトピックには、詳細な Office 365 のネットワーク参照情報が含まれています。
  
- [Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [コンテンツ配信ネットワーク](content-delivery-networks.md)
    
- [Office 365 の外部ドメイン ネーム システムのレコード](external-domain-name-system-records.md)
    
- [Office 365 サービスでの IPv6 サポート](ipv6-support.md)
    
- [Office 365 ネットワーク接続の原則](https://aka.ms/o365networkingprinciples)
    
- [Office 365 のビデオネットワークについてよく寄せられる質問 (FAQ)](office-365-video-networking-faq.md)
    
- [Office 365 サービスに接続するネットワーク デバイスの計画](plan-for-network-devices.md)
    
- [Office 365 サービスのセットアップガイド](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
