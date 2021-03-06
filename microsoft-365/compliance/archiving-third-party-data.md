---
title: サード パーティのデータをアーカイブする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 メールボックスにサードパーティのデータをインポートする方法について説明します。
ms.openlocfilehash: d3a5c3509b0c45dc2cacb15eec7af80e5a2e547d
ms.sourcegitcommit: f07442d077eb4357fa5d99d051b035705eb30efa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "49002372"
---
# <a name="archive-third-party-data"></a>サード パーティのデータをアーカイブする

Microsoft 365 では、管理者がデータコネクタを使用して、ソーシャルメディアプラットフォーム、インスタントメッセージングプラットフォーム、およびドキュメントコラボレーションプラットフォームから Microsoft 365 組織のメールボックスにサードパーティのデータをインポートしてアーカイブすることができます。 データコネクタを使用して Microsoft 365 でサードパーティのデータをインポートおよびアーカイブすることの主な利点の1つは、インポート後にさまざまな Microsoft 365 コンプライアンスソリューションを適用できることです。 これにより、組織の Microsoft 以外のデータが、組織に影響する規制や基準に準拠していることを確認できます。

## <a name="third-party-data-connectors"></a>サードパーティのデータ コネクタ

次の表に、Microsoft 365 コンプライアンスセンターで利用可能なサードパーティデータコネクタの一覧を示します。 また、この表には、Microsoft 365 でのインポートとアーカイブ後にサードパーティのデータに適用できるコンプライアンスソリューションの概要も記載されています。 各コンプライアンスソリューションの詳細については、 [次のセクション](#overview-of-compliance-solutions-that-support-third-party-data) を参照してください。また、サードパーティのデータがどのように役立つかについても説明します。

> [!TIP]
> **サードパーティのデータ** 列のリンクをクリックして、そのデータ型のコネクタを作成するための手順を順を追って説明します。

|サードパーティのデータ  |訴訟ホールド|電子情報開示  |保持設定  |レコード管理  |通信コンプライアンス  |インサイダー リスクの管理  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[&T ネットワーク <sup>1</sup>](archive-att-network-archiver-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bell ネットワーク <sup>1</sup>](archive-bell-network-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bloomberg メッセージ](archive-bloomberg-message-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Cisco Jabber <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[エンタープライズ番号 <sup>1</sup>](archive-enterprise-number-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[FX Connect <sup>2</sup>](archive-fxconnect-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[人事 (HR)](import-hr-data.md) ||||||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)
|[IceChat](archive-icechat-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[O2 ネットワーク <sup>1</sup>](archive-o2-network-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[物理バッジのデバッグ](import-physical-badging-data.md) ||||||![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[ピボット <sup>2</sup>](archive-pivot-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Reuters の処理 <sup>2</sup>](archive-reutersdealing-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[余裕期間の電子情報 <sup>2</sup>](archive-slack-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Symphony <sup>2</sup>](archive-symphony-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[TELUS ネットワーク <sup>1</sup>](archive-telus-network-data.md)    |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[テキスト区切り <sup>2</sup>](archive-text-delimited-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Verizon ネットワーク <sup>1</sup>](archive-verizon-network-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Web ページ <sup>2</sup>](archive-webpagecapture-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Facebook <sup>2</sup>からの Workplace](archive-workplacefromfacebook-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[会議を拡大/縮小 <sup>2</sup>](archive-zoommeetings-data.md)     |![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
||||||||

> [!NOTE]
> TeleMessage によって提供されるデータコネクタ<sup>1 つ</sup>。 Microsoft 365 でデータをアーカイブする前に、TeleMessage を使用して組織のアーカイブサービスを設定する必要があります。 詳細については、このデータ型のステップバイステップの手順の前提条件に関するセクションを参照してください。<br/><br/>Globanet によって提供されるデータコネクタ<sup>2 個</sup>。 Microsoft 365 でデータをアーカイブする前に、Globanet を使用して組織のアーカイブサービスを設定する必要があります。 詳細については、このデータ型のステップバイステップの手順の前提条件に関するセクションを参照してください。

前の表に記載されているサードパーティのデータ (HR データおよび物理 baddriverdata を除く) は、ユーザーメールボックスにインポートされます。 サードパーティのデータをサポートするコンプライアンスソリューションは、データが格納されているユーザーメールボックスに適用されます。

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>サードパーティのデータをサポートするコンプライアンスソリューションの概要

次のセクションでは、Microsoft 365 コンプライアンスソリューションが、前の表に記載されているサードパーティデータの管理に役立つ事柄について説明します。

### <a name="litigation-hold"></a>訴訟ホールド

ユーザーのメールボックスに [訴訟ホールド](create-a-litigation-hold.md) を配置して、サードパーティのデータを保持します。 保持を作成するときに、削除され、変更されたサードパーティデータが指定した期間保持され、メールボックスから完全に削除されるように保持期間 ( *時間ベースの保持* とも呼ばれます) を指定できます。 または、コンテンツを無期限に ( *無限保持* と呼ばれます)、または訴訟ホールドが解除されるまで保持することができます。

### <a name="ediscovery"></a>電子情報開示

Microsoft 365 の3つの主要な電子情報開示ツールは、コンテンツ検索、コア電子情報開示、および上級電子情報開示です。

- **[コンテンツ検索](content-search.md)。** コンテンツ検索ツールを使用して、インポートしたサードパーティデータのメールボックスを検索できます。 検索クエリと条件を使用して検索結果を絞り込んだり、検索結果をエクスポートしたりすることができます。

- **[コア電子情報開示](get-started-core-ediscovery.md)。** このツールは、サポート案件データにアクセスできるユーザーを制御するケースを作成したり、検索条件に一致するユーザーメールボックスまたはメールボックスの内容を保持したりすることができるようにすることで、基本的な検索およびエクスポート機能を基盤に構築されています。 つまり、ユーザーメールボックスにインポートされたサードパーティのデータに電子情報開示を保持することができます。

- **[高度な電子情報開示](overview-ediscovery-20.md)。** この強力なツールは、ケースに保管担当者を追加し、保管担当者のデータを保持するようにし、保管担当者のサードパーティのデータをレビューに読み込み、テーマや重複の検出などの詳細な分析を行うことで、コア電子情報開示のケース機能を拡張します。 サードパーティのデータをレビューセットに読み込むと、クエリを実行して絞り込んだ結果セットにフィルターを適用することができます。

   コア電子情報開示と上級電子情報開示の両方を使用すると、組織の法的または社内調査に関連する可能性があるサードパーティのデータを管理できます。

### <a name="retention-settings"></a>保持設定

保持 [ポリシー](retention.md) をユーザーメールボックスに適用して、保存期間の経過後にサードパーティのデータ (およびその他のメールボックスの内容) を削除することができます。 また、アイテム保持ポリシーを使用して、特定の年齢のサードパーティデータを削除したり、保持ラベルを使用して、サードパーティのデータの保持期間の期限が切れたときに [廃棄の確認をトリガー](disposition.md) したりすることもできます。

### <a name="records-management"></a>レコード管理

Microsoft 365 の [レコード管理](records-management.md) 機能を使用すると、サードパーティのデータをレコードとして宣言できます。 これは、メールボックス内のサードパーティデータを record としてマークする保持ラベルを適用するユーザーが手動で行うことができます。 または、サードパーティデータの機密情報、キーワード、またはコンテンツタイプを識別することによって、保持ラベルを自動的に適用することもできます。

### <a name="communication-compliance"></a>通信コンプライアンス

[コミュニケーションコンプライアンス](communication-compliance.md)を使用して、サードパーティのデータが組織のデータ標準に準拠しているかどうかを確認できます。 これを行うには、組織内の不適切なメッセージに対する修復アクションを検出、キャプチャ、および取得します。 たとえば、不快感を与える言語、機密情報、法令遵守のためにインポートするサードパーティデータを監視できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

選択的な人事データなど、サードパーティのデータからの信号は、内部のリスクを最小限にするために [Insider リスク管理](insider-risk-management.md) ソリューションで使用できます。これにより、組織内のリスクの高いアクティビティを検出、調査、および操作できるようになります。 たとえば、HR データコネクタによってインポートされたデータは、従業員データの盗難を検出するリスク指標として使用されます。

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Microsoft パートナーと協力してサードパーティのデータをアーカイブする

サードパーティのデータをインポートおよびアーカイブする別の方法として、組織が Microsoft パートナーと連携することがあります。 Microsoft コンプライアンスセンターで利用可能なデータコネクタでサードパーティのデータ型がサポートされていない場合は、サードパーティのデータソースからアイテムを定期的に抽出するように構成されたカスタムコネクタを提供できるパートナーと連携して、サードパーティの API によって Microsoft クラウドに接続し、それらのアイテムを Microsoft 365 にインポートできます。 また、パートナーコネクタは、アイテムのコンテンツをサードパーティのデータソースから電子メールメッセージに変換し、それを Microsoft 365 のメールボックスにインポートします。

この方法で操作できるパートナーの一覧と、この方法のステップバイステップのプロセスについては、「 [Microsoft 365 でサードパーティのデータをアーカイブするためにパートナーと連携する](work-with-partner-to-archive-third-party-data.md)」を参照してください。
