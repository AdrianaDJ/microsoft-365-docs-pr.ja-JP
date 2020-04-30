---
title: ユーザーがスパムおよびフィッシングメッセージを送信するためのメールボックスを指定する
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
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーによって報告されたスパムやフィッシング電子メールを収集するようにメールボックスを構成する方法について説明します。
ms.openlocfilehash: a3a175c3815c6750086526ec92d097fb7cbcefa3
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43922665"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a><span data-ttu-id="a86f7-103">Office 365 でスパムおよびフィッシングのメッセージをユーザーが送信するためのメールボックスを指定する</span><span class="sxs-lookup"><span data-stu-id="a86f7-103">Specify a mailbox for user submissions of spam and phishing messages in Office 365</span></span>

<span data-ttu-id="a86f7-104">Exchange Online メールボックスを使用する Office 365 組織では、ユーザーが悪意のあるメールや悪意のないメッセージを受信するメールボックスを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-104">In Office 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="a86f7-105">ユーザーがさまざまなレポートオプションを使用してメッセージを送信する場合、このメールボックスを使用して、メッセージを傍受する (カスタムメールボックスにのみ送信する) か、メッセージのコピーを受信する (カスタムメールボックスおよび Microsoft に送信) ことができます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="a86f7-106">この機能は、次のメッセージレポートオプションで機能します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="a86f7-107">レポートメッセージアドイン</span><span class="sxs-lookup"><span data-stu-id="a86f7-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="a86f7-108">[Web 上の outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (旧称 Outlook web App) での組み込みレポート</span><span class="sxs-lookup"><span data-stu-id="a86f7-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="a86f7-109">また、指定したメールボックスにメッセージを転送するように、サードパーティ製のメッセージレポートツールを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="a86f7-110">ユーザーが報告したメッセージを Microsoft に直接送信する代わりにカスタムメールボックスに配信することにより、管理者は、[管理者送信](admin-submission.md)を使用してメッセージを選択的に、手動で microsoft に報告できます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a86f7-111">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a86f7-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a86f7-112"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a86f7-113">[**ユーザーの送信**] ページに直接移動する<https://protection.office.com/userSubmissionsReportMessage>には、を使用します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="a86f7-114">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a86f7-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a86f7-115">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a86f7-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a86f7-116">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a86f7-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="a86f7-117">ユーザーが送信するメールボックスを構成するには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a86f7-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a86f7-118">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a86f7-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="a86f7-119">セキュリティ & コンプライアンスセンターを使用してユーザー送信メールボックスを構成する</span><span class="sxs-lookup"><span data-stu-id="a86f7-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="a86f7-120">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**ユーザーの送信**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="a86f7-121">表示される [**ユーザーの送信**] ページで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="a86f7-122">**Outlook のレポートメッセージ機能を有効にする (推奨)**: レポートメッセージアドインまたは outlook on the web の組み込みのレポートを使用して、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="a86f7-123">**エンドユーザーの確認メッセージをカスタマイズする**: このリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="a86f7-124">[**確認メッセージのカスタマイズ**] ポップアップが表示されたら、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="a86f7-125">**提出前**:**タイトル**と確認の**メッセージ**ボックスに、レポートメッセージアドインを使用してメッセージを報告する前にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a86f7-126">変数% 型% を使用して、送信の種類 (迷惑メール、迷惑メールではない、フィッシングなど) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="a86f7-127">前述のように、通知には次のテキストも追加されます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="a86f7-128">電子メールは、のように、分析のために Microsoft に提出されます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="a86f7-129">メールによっては個人情報や機密情報が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a86f7-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="a86f7-130">**送信後**: [ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="a86f7-131">[**タイトル**] および [**確認メッセージ**] ボックスに、レポートメッセージアドインを使用してメッセージを報告した後にユーザーに表示される説明テキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a86f7-132">変数% 型% を使用して、提出の種類を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a86f7-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="a86f7-133">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="a86f7-134">これらの値をクリアするには、[**ユーザーの送信**] ページの [元に**戻す**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="a86f7-135">**報告されたメッセージの送信先**: 次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="a86f7-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="a86f7-136">**Microsoft (推奨)**: ユーザーの送信メールボックスが使用されていません (報告されたすべてのメッセージが Microsoft に送られます)。</span><span class="sxs-lookup"><span data-stu-id="a86f7-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="a86f7-137">**Microsoft およびカスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     - <span data-ttu-id="a86f7-138">**カスタムメールボックス**: 表示されるボックスに、既存の Exchange Online メールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-138">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     <span data-ttu-id="a86f7-139">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-139">When you're finished, click **Confirm**.</span></span>

     ![報告されたメッセージを Microsoft およびカスタムメールボックスに送信する](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="a86f7-141">**Outlook のレポートメッセージ機能を無効に**する: レポートメッセージアドインまたは web 上の Outlook の組み込みレポートではなくサードパーティのレポートツールを使用し、次の設定を構成する場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-141">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="a86f7-142">[**このカスタムメールボックスを使用して、ユーザーが報告した送信を受信する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-142">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="a86f7-143">表示されるボックスに、既存のメールボックスの電子メールアドレス、または作成するメールボックスの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a86f7-143">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="a86f7-144">完了したら、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a86f7-144">When you're finished, click **Confirm**.</span></span>

     ![サードパーティ製のツールを使用して、レポートされたメッセージをカスタムメールボックスに送信する](../../media/user-submission-disable-outlook-report-message.png)