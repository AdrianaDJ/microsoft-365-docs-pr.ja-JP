---
title: Insider リスク管理の通知テンプレート (プレビュー)
description: Microsoft 365 の insider リスク管理の通知テンプレートについて説明します。
keywords: Microsoft 365、insider リスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5b05eb190621dd0829c992cf5b47e8fbe8bcf99a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590628"
---
# <a name="insider-risk-management-notice-templates-preview"></a><span data-ttu-id="7968a-104">Insider リスク管理の通知テンプレート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7968a-104">Insider risk management notice templates (preview)</span></span>

<span data-ttu-id="7968a-105">Insider リスク管理の通知テンプレートを使用すると、アクティビティがポリシーの一致と通知を生成するときに、従業員に電子メールメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-105">Insider risk management notice templates allow you to send email messages to employees when their activities generate a policy match and alert.</span></span> <span data-ttu-id="7968a-106">ほとんどの場合、通知を生成する従業員のアクションは、誤ったミスまたは不注意なアクティビティの結果として、意図したとおりにはなりません。</span><span class="sxs-lookup"><span data-stu-id="7968a-106">In most cases, employee actions that generate alerts are the result of mistakes or inadvertent activities without ill intent.</span></span> <span data-ttu-id="7968a-107">通知は、従業員に対して、より慎重に、またはリフレッシャートレーニングや企業ポリシーリソースのリンクや情報を提供するための簡単な通知として機能します。</span><span class="sxs-lookup"><span data-stu-id="7968a-107">Notices serve as simple reminders to employees to be more careful or to provide links or information for refresher training or corporate policy resources.</span></span> <span data-ttu-id="7968a-108">通知は、内部のコンプライアンストレーニングプログラムの重要な部分になる可能性があり、定期的なリスクアクティビティを持つ従業員に関する文書化された監査証跡を作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7968a-108">Notices can be an important part of your internal compliance training program and can help create a documented audit trail for employees with recurring risk activities.</span></span>

<span data-ttu-id="7968a-109">問題解決プロセスの一環として、ポリシーの一致に関する電子メール通知通知をユーザーに送信する場合は、通知テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="7968a-109">Create notice templates if you want to send users an email reminder notice for policy matches as part of the issue resolution process.</span></span> <span data-ttu-id="7968a-110">通知は、確認されている特定の通知に関連付けられた従業員の電子メールアドレスにのみ送信できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-110">Notices can only be sent to the employee email address associated with the specific alert being reviewed.</span></span> <span data-ttu-id="7968a-111">ポリシー一致に適用する通知テンプレートを選択するときは、テンプレートで定義されているフィールド値を受け入れるか、必要に応じてフィールドを上書きするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-111">When selecting a notice template to apply to a policy match, you can choose to accept the field values defined in the template or overwrite the fields as needed.</span></span>

## <a name="notice-templates-dashboard"></a><span data-ttu-id="7968a-112">通知テンプレートダッシュボード</span><span class="sxs-lookup"><span data-stu-id="7968a-112">Notice templates dashboard</span></span>

<span data-ttu-id="7968a-113">**通知テンプレートダッシュボード**には、構成された通知テンプレートの一覧が表示され、新しい通知テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-113">The **Notices templates dashboard** displays a list of configured notice templates and allows you to create new notice templates.</span></span> <span data-ttu-id="7968a-114">メモテンプレートは、最新の通知テンプレートが最初に表示された順序で、逆の順序で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7968a-114">The notice templates are listed in reverse date order with the most recent notice template listed first.</span></span>

![Insider リスク管理の通知テンプレートダッシュボード](media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a><span data-ttu-id="7968a-116">通知用の HTML</span><span class="sxs-lookup"><span data-stu-id="7968a-116">HTML for notices</span></span>

<span data-ttu-id="7968a-117">通知用の単純なテキストベースの電子メールメッセージを作成する場合は、通知テンプレートの [メッセージ本文] フィールドで HTML を使用して、より詳細なメッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-117">If you'd like to create more than a simple text-based email message for notifications, you can create a more detailed message by using HTML in the message body field of a notice template.</span></span> <span data-ttu-id="7968a-118">次の例では、基本的な HTML ベースの電子メール通知テンプレートのメッセージ本文の形式を示します。</span><span class="sxs-lookup"><span data-stu-id="7968a-118">The following example provides the message body format for a basic HTML-based email notification template:</span></span>

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> <span data-ttu-id="7968a-119">Insider リスク管理の通知テンプレートの HTML href 属性の実装では、現在、URL 参照の二重引用符の代わりに単一引用符のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7968a-119">HTML href attribute implementation in the insider risk management notice templates currently support only single quotation marks instead of double quotation marks for URL references.</span></span>

## <a name="create-a-new-notice-template"></a><span data-ttu-id="7968a-120">新しい通知テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="7968a-120">Create a new notice template</span></span>

<span data-ttu-id="7968a-121">新しい insider リスク管理の通知テンプレートを作成するには、Microsoft 365 コンプライアンスセンターで、 **insider リスク管理**ソリューションの通知ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="7968a-121">To create a new insider risk management notice template, you'll use the notice wizard in **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="7968a-122">新しい insider リスク管理通知テンプレートを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7968a-122">Complete the following steps to create a new insider risk management notice template:</span></span>

1. <span data-ttu-id="7968a-123">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-123">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7968a-124">[**通知テンプレートの作成**] を選択して、通知ウィザードを開きます。</span><span class="sxs-lookup"><span data-stu-id="7968a-124">Select **Create notice template** to open the notice wizard.</span></span>
3. <span data-ttu-id="7968a-125">[**新しい通知テンプレートの作成**] ページで、以下のフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="7968a-125">On the **Create a new notice template** page, complete the following fields:</span></span>
    - <span data-ttu-id="7968a-126">**テンプレート名**: 通知のフレンドリ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="7968a-126">**Template name**: Enter a friendly name for the notice.</span></span> <span data-ttu-id="7968a-127">この名前は、ケースから通知を送信するときに、通知ダッシュボードと通知選択リストに通知の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7968a-127">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="7968a-128">**送信元**: 通知の送信者の電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="7968a-128">**Send from**: Enter the sender email address for the notice.</span></span> <span data-ttu-id="7968a-129">このアドレスは、ケースから通知を送信するときに変更しない限り、[**差出人:** ] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7968a-129">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="7968a-130">**Cc および Bcc**フィールド: サブスクリプションの Active Directory から選択された、ポリシーの一致の通知対象となるオプションのユーザーまたはグループ。</span><span class="sxs-lookup"><span data-stu-id="7968a-130">**Cc and Bcc** fields: Optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="7968a-131">**件名**: メッセージの件名行に表示される情報。テキスト文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7968a-131">**Subject**: Information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="7968a-132">**メッセージ本文**: メッセージ本文に表示される情報は、テキストまたは HTML 値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7968a-132">**Message body**: Information that appears in the message body, supports text or HTML values.</span></span>
4. <span data-ttu-id="7968a-133">[**作成**] を選択して通知テンプレートを作成および保存するか、[**キャンセル**] を選択して通知テンプレートを保存せずに閉じます。</span><span class="sxs-lookup"><span data-stu-id="7968a-133">Select **Create** to create and save the notice template or select **Cancel** to close without saving the notice template.</span></span>

## <a name="update-a-notice-template"></a><span data-ttu-id="7968a-134">通知テンプレートを更新する</span><span class="sxs-lookup"><span data-stu-id="7968a-134">Update a notice template</span></span>

<span data-ttu-id="7968a-135">既存の insider リスク管理の通知テンプレートを更新するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7968a-135">To update an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="7968a-136">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-136">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7968a-137">通知ダッシュボードで、管理する通知テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-137">On the notice dashboard, select the notice template you want to manage.</span></span>
3. <span data-ttu-id="7968a-138">[通知の詳細] ページで、[**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-138">On the notice details page, select **Edit**</span></span>
4. <span data-ttu-id="7968a-139">**編集**ページでは、次のフィールドを編集できます。</span><span class="sxs-lookup"><span data-stu-id="7968a-139">On the **Edit** page, you can edit the following fields:</span></span>
    - <span data-ttu-id="7968a-140">[**テンプレート名**: 新しいわかりやすい名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="7968a-140">**Template name**: Enter a new friendly name for the notice.</span></span> <span data-ttu-id="7968a-141">この名前は、ケースから通知を送信するときに、通知ダッシュボードと通知選択リストに通知の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7968a-141">This name appears on the list of notices on the notice dashboard and in the notice selection list when sending notices from a case.</span></span>
    - <span data-ttu-id="7968a-142">**送信元**: 通知の送信者の電子メールアドレスを更新します。</span><span class="sxs-lookup"><span data-stu-id="7968a-142">**Send from**: Update the sender email address for the notice.</span></span> <span data-ttu-id="7968a-143">このアドレスは、ケースから通知を送信するときに変更しない限り、[**差出人:** ] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7968a-143">This address will appear in the **From:** field in all notices sent to employees unless changed when sending a notice from a case.</span></span>
    - <span data-ttu-id="7968a-144">**Cc および Bcc**フィールド: サブスクリプションの Active Directory から選択されたポリシーの一致を通知するオプションのユーザーまたはグループを更新します。</span><span class="sxs-lookup"><span data-stu-id="7968a-144">**Cc and Bcc** fields: Update optional users or groups to be notified of the policy match, selected from the Active Directory for your subscription.</span></span>
    - <span data-ttu-id="7968a-145">**件名**: メッセージの件名行に表示される更新情報。テキスト文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7968a-145">**Subject**: Update information that appears in the subject line of the message, supports text characters.</span></span>
    - <span data-ttu-id="7968a-146">**メッセージ本文**: メッセージ本文に表示される更新情報。テキストまたは HTML 値をサポートします。</span><span class="sxs-lookup"><span data-stu-id="7968a-146">**Message body**: Update information that appears in the message body, supports text or HTML values.</span></span>
5. <span data-ttu-id="7968a-147">[**保存**] を選択して通知を更新して保存するか、[**キャンセル**] を選択して通知テンプレートを保存せずに閉じます。</span><span class="sxs-lookup"><span data-stu-id="7968a-147">Select **Save** to update and save the notice or select **Cancel** to close without saving the notice template.</span></span>

## <a name="delete-a-notice-template"></a><span data-ttu-id="7968a-148">通知テンプレートを削除する</span><span class="sxs-lookup"><span data-stu-id="7968a-148">Delete a notice template</span></span>

<span data-ttu-id="7968a-149">既存の insider リスク管理の通知テンプレートを削除するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7968a-149">To delete an existing insider risk management notice template, complete the following steps:</span></span>

1. <span data-ttu-id="7968a-150">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-150">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Notice templates** tab.</span></span>
2. <span data-ttu-id="7968a-151">通知ダッシュボードで、削除する通知テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-151">On the notice dashboard, select the notice template you want to delete.</span></span>
3. <span data-ttu-id="7968a-152">ツールバーの [**削除**] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-152">Select the **Delete** icon on the toolbar.</span></span>
4. <span data-ttu-id="7968a-153">通知テンプレートを削除するには、[削除] ダイアログで [**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-153">To delete the notice template, select **Yes** in the delete dialog.</span></span> <span data-ttu-id="7968a-154">削除を取り消すには、[**キャンセル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7968a-154">To cancel the deletion, select **Cancel**.</span></span>