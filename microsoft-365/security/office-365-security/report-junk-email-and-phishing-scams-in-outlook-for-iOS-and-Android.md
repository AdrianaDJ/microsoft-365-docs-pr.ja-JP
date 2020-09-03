---
title: IOS および Android 用の Outlook で迷惑メールとフィッシング詐欺メールを報告する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、iOS および Android 用の Outlook に組み込まれている迷惑メールと迷惑メールの報告オプションについて説明しています。
ms.openlocfilehash: 216f60eb168190603c7c9aba58cef27c2bf15b01
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867461"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Exchange Online で iOS および Android 用の Outlook で迷惑メールとフィッシング詐欺メールを報告する

[ハイブリッド先進認証](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview?view=o365-worldwide)を使用する Exchange online またはオンプレミスのメールボックスを含む Microsoft 365 組織では、IOS および Android 用の Outlook の組み込みのレポート作成オプションを使用して誤検知 (スパムとしてマークされた良好な電子メール)、誤検知 (無効な電子メールが許可されている)、および Exchange Online PROTECTION (EOP) へ

## <a name="what-do-you-need-to-know-before-you-begin"></a>開始する前に把握しておくべき情報

- Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。 詳細については、「 [管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。

- 指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。 詳細については、「 [Exchange Online でスパムおよびフィッシングメッセージをユーザーに送信するためのメールボックスを指定](user-submission.md)する」を参照してください。

- Microsoft へのメッセージの報告の詳細については、「 [microsoft にメッセージとファイルを報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。

  > [!NOTE]
  > 迷惑メール報告がユーザー送信ポリシーの Outlook に対して無効になっている場合、迷惑メールまたはフィッシングメッセージは迷惑メールフォルダーに移動され、管理者または Microsoft には報告されません。

## <a name="report-spam-and-phishing-messages-in-outlook-for-ios-and-android"></a>IOS および Android 用の Outlook でスパムメッセージとフィッシングメッセージを報告する

受信トレイ内のメッセージ、または迷惑メール以外の他の電子メールフォルダーについては、次の手順を使用して、iOS および Android 用のスパムおよびフィッシングメッセージを報告します。

1. 1つ以上のメッセージを選択します。
2. 右上隅にある3つの垂直点をタップします。 [アクション] メニューが開きます。

   ![[アクション] メニューから迷惑メールまたはフィッシング詐欺メールを報告する](../../media/Android-report-as-junk-dialog.png)

3. [ **迷惑メールを報告** ] をタップしてから、[ **迷惑メール** または **フィッシング詐欺**] を選択

   ![迷惑メールまたはフィッシング詐欺メールを報告する](../../media/Android-report-junk-or-phishing.png)

4. 表示されるダイアログで、[ **レポート** ] または [ **いいえ**] を選択できます。 [ **いいえ**] を選択した場合、[ **迷惑** メール] をタップすると、メッセージは [迷惑メール] フォルダーに移動します。 **フィッシング** をタップすると、メッセージは [削除済みアイテム] フォルダーに移動します。 [ **レポート** ] を選択して、メッセージのコピーも Microsoft に送信します。

   ![迷惑メールまたはフィッシング詐欺メールレポートのオプションを報告する](../../media/Android-junk-email-reporting-options.png)

気が変わった場合は、表示されるトースト通知で [ **元に戻す** ] を選択します。 メッセージは受信トレイフォルダーに残ります。

## <a name="report-non-spam-messages-from-the-junk-folder-in-outlook-for-ios-and-android"></a>Outlook for iOS および Android 用の迷惑メールフォルダーから非スパムメッセージを報告する

[迷惑メール] フォルダーで、次の手順を使用してスパム誤検知を報告します。

1. 1つ以上のメッセージを選択します。
2. 右上隅にある3つの垂直点をタップします。 [アクション] メニューが開きます。

   ![[アクション] メニューから迷惑メールではないことを報告する](../../media/Android-not-junk-email.png)

3. **迷惑メールではない**をタップします。

トースト通知は、電子メールが受信トレイに移動されたことを示します。 気が変わった場合は、トースト通知で [ **元に戻す** ] を選択します。 電子メールは、迷惑メールフォルダーに残ります。