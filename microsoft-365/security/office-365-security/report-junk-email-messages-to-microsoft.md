---
title: スパム、非スパム、フィッシングメッセージを Microsoft に報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: 管理者は、正常なメッセージと悪いメッセージおよびファイルを分析のために Microsoft に報告するさまざまな方法について説明します。
ms.openlocfilehash: df89e90998b5aa482dc1ea4003d53cf98b4b4d3f
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527783"
---
# <a name="report-messages-and-files-to-microsoft"></a>メッセージとファイルを Microsoft に報告する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange online メールボックスを使用していない場合、ユーザーと管理者の両方に、電子メールメッセージやファイルを Microsoft に報告するためのさまざまな方法が用意されています。365

****

|メソッド|説明|
|---|---|
|[管理者送信を使用して、疑いがあるスパム、フィッシング、URL、ファイルを Microsoft に提出する](admin-submission.md)|Exchange Online メールボックスを使用する組織での管理者に推奨される報告方法 (スタンドアロン EOP では利用できません)。|
|[レポート メッセージ アドインを有効にする](enable-the-report-message-add-in.md)|Outlook、Outlook for Mac、および web 上の Outlook (旧称 Outlook Web App) と共に動作し、推奨されるアドインです。 <p> サブスクリプションに応じて、ユーザーがアドインで報告したメッセージが、 [管理者提出ポータル](admin-submission.md)で利用できるようになります。また、自動化された [調査と応答 (航空) の結果](air-view-investigation-results.md)、 [ユーザーが報告したメッセージレポート](view-email-security-reports.md#user-reported-messages-report)、および [脅威エクスプローラー](threat-explorer-views.md#email--submissions)が使用できます。 <p> 指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。 詳細については、「 [ユーザーの送信ポリシー](user-submission.md)」を参照してください。|
|[Microsoft Outlook 用迷惑メール報告アドインをインストールして使用する](junk-email-reporting-add-in-for-microsoft-outlook.md)|Outlook でのみ動作します。|
|[Outlook on the web で迷惑メールとフィッシング詐欺メールを報告する](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Exchange Online のメールボックスを使用する組織では、web 上の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。 <p> ユーザーがレポートするメッセージは [、管理者提出ポータル](admin-submission.md)で利用できます。 <p> 指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。 詳細については、「 [ユーザーの送信ポリシー](user-submission.md)」を参照してください。|
|[IOS および Android 用の Outlook で迷惑メールとフィッシング詐欺メールを報告する](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Exchange Online メールボックスを使用する組織では、iOS および Android 用の Outlook の組み込み機能を使用します (スタンドアロン EOP では使用できません)。 <p> ユーザーがレポートするメッセージは [、管理者提出ポータル](admin-submission.md)で利用できます。 <p> 指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。 詳細については、「 [ユーザーの送信ポリシー](user-submission.md)」を参照してください。|
|[分析のためにメッセージを手動で Microsoft に送信する](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|スパムやフィッシングではなく、特定の Microsoft 電子メールアドレスに、添付されたメッセージを手動で送信します。|
|[メール フロー ルールを使用して、ユーザーが Microsoft に報告する内容を確認する](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|ユーザーが分析のためにメッセージを報告したときに通知するメールフロールール (トランスポートルールとも呼ばれます) を作成する方法について説明します。
|||
|[マルウェアおよびマルウェアでないものを分析のために Microsoft に提出する](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Microsoft セキュリティインテリジェンスサイトを使用して、添付ファイルやその他のファイルを送信します。|

スパムまたはフィッシングメッセージが配信されずに検疫された場合、ユーザーはセキュリティ & コンプライアンスセンターの検疫ポータルから Microsoft にメッセージを報告できます。 詳細については、「 [Microsoft 365 のユーザーとして、検疫済みメッセージを検索して解放する](find-and-release-quarantined-messages-as-a-user.md)」を参照してください。
