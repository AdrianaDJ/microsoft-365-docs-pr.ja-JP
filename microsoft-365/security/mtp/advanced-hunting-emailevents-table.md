---
title: 高度な検索スキーマの EmailEvents テーブル
description: 高度な検索スキーマの EmailEvents テーブルにある Microsoft 365 メールに関連付けられているイベントについて説明します。
keywords: 高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、EmailEvents、network message id、sender、recipient、attachment id、attachment name、マルウェア verdict、フィッシング verdict、attachment count、link count、url 数
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 86cc32cf395f2216eb3e167e372d1225734c4c28
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842634"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender



`EmailEvents`[高度な](advanced-hunting-overview.md)検索スキーマの表には、Microsoft Defender for Office 365 の電子メールの処理に関連するイベントに関する情報が含まれています。 このテーブルの情報を返すクエリを作成するには、この参照を使用できます。

>[!TIP]
> テーブルでサポートされているイベントの種類 (値) の詳細については、 `ActionType` セキュリティセンターで利用可能な [組み込みスキーマリファレンス](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) を使用してください。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | 日付型 | イベントが記録された日付と時刻 |
| `EmailId` | string | 一意のメールと受信者の識別子 |
| `NetworkMessageId` | string | Microsoft 365 によって生成される電子メールの一意識別子。 |
| `InternetMessageId` | string | 送信メール システムにより設定された、メールの一般向けの識別子 |
| `SenderMailFromAddress` | string | MAIL FROM ヘッダーの送信者メール アドレス (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromAddress` | string | 受信者のメール クライアントで受信者に表示される、FROM ヘッダーの送信者メール アドレス |
| `SenderMailFromDomain` | string | MAIL FROM ヘッダーの送信者ドメイン (エンベロープ送信者またはリターン パス アドレスとも呼ばれる) |
| `SenderFromDomain` | string | 受信者のメール クライアントで受信者に表示される、MAIL FROM ヘッダーの送信者ドメイン |
| `SenderIPv4` | string | 検出された、最後にメッセージをリレーしたメール サーバーの IPv4 アドレス |
| `SenderIPv6` | string | 検出された、最後にメッセージをリレーしたメール サーバーの IPv6 アドレス |
| `RecipientEmailAddress` | string | 受信者のメール アドレス、または配布リストの展開後の受信者のメール アドレス |
| `Subject` | string | メールの件名 |
| `EmailClusterId` | string | コンテンツのヒューリスティック分析に基づいてまとめられた、似通ったメールのグループの識別子 |
| `EmailDirection` | string | ネットワークに対するメールの方向: Inbound、Outbound、Intra-org |
| `DeliveryAction` | string | メールの配信アクション: Delivered、Junked、Blocked、または Replaced |
| `DeliveryLocation` | string | メールの配信場所: 受信トレイ/フォルダー、オンプレミス/外部、迷惑メール、検疫、失敗、中断、削除済みアイテム |
| `PhishFilterVerdict` | string | メールがフィッシングであるかどうかに関する、メール フィルタリング スタックの判定: Phish または Not Phish |
| `PhishDetectionMethod` | string | フィッシングとして電子メールを検出するために使用される方法: 悪意のある URL 評価、安全なリンク URL 分析、高度なフィッシングフィルター、一般フィッシングフィルター、スプーフィング防止: 組織内、ドメイン偽装、ユーザー偽装、ブランド偽装 |
| `MalwareFilterVerdict` | string | メールにマルウェアが含まれているかどうかに関する、メールのフィルター処理スタックの判定 (マルウェア、マルウェア以外) |
| `MalwareDetectionMethod` | string | 電子メール内のマルウェアを検出するために使用される方法: マルウェア対策エンジン、ファイルの評価、安全な添付ファイル |
| `FinalEmailAction` | string | フィルターの判定、ポリシー、ユーザー アクションに基づいてメールに対して実行される最終的なアクション: メッセージを迷惑メール フォルダーに移動、X-ヘッダーの追加、件名の変更、メッセージのリダイレクト、メッセージの削除、検疫フォルダーへの配信、アクションなし、Bcc メッセージ |
| `FinalEmailActionPolicy` | string | 適用されたアクション ポリシー: 高信頼度のスパム対策、スパム対策、バルク メール スパム対策、フィッシング スパム対策、ドメイン偽装フィッシング対策、ユーザー偽装フィッシング対策、スプーフィング フィッシング対策、グラフ偽装フィッシング対策、マルウェア対策、安全な添付ファイル、Enterprise Transport Rules (ETR) |
| `FinalEmailActionPolicyGuid` | string | メールに対する最終アクションを決定したポリシーの一意の識別子 |
| `AttachmentCount` | int | メール内の添付ファイル数 |
| `UrlCount` | int | メールに埋め込まれている URL の数 |
| `EmailLanguage` | string | 検出されたメールのコンテンツの言語 |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 間での捜索](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
