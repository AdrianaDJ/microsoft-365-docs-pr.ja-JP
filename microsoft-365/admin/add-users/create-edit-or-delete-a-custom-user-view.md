---
title: Office 365 でカスタム ユーザー ビューを作成、編集、削除する
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: フィルターを使用して Office 365 のカスタムユーザービューを作成、編集、または削除する方法について説明します。
ms.openlocfilehash: ba03d3da3e8bfdc4f2a661d1dc59845a8a22609f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241643"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="7b5a0-103">Office 365 でカスタム ユーザー ビューを作成、編集、削除する</span><span class="sxs-lookup"><span data-stu-id="7b5a0-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="7b5a0-p101">Office 365 の全体管理者またはユーザー管理の管理者は、一部の特定のユーザーを表示するためのカスタム ユーザー ビューを作成できます。カスタム ユーザー ビューは、Office 365 に付属している標準ビューのセット以外の追加ビューです。カスタム ユーザー ビューは作成、編集、削除でき、ある管理者が作成したカスタム ビューはすべての管理者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="7b5a0-107">新しい Microsoft 365 管理センターを利用していない場合、[ホーム] ページの上部にある [**新しい管理センターをお試しください**] の切り替えを選択して有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="7b5a0-108">管理センターのカスタムユーザービュー</span><span class="sxs-lookup"><span data-stu-id="7b5a0-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="7b5a0-109">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が**フィルター**一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="7b5a0-110">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="7b5a0-111">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が [**ビュー** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="7b5a0-112">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="7b5a0-113">カスタムユーザービューを作成、編集、または削除すると、組織内のすべての管理者が [**ユーザー** ] ページに移動したときに、その変更内容が [**ビュー** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="7b5a0-114">最大で 50 個のカスタム ビューを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="7b5a0-115">標準ユーザービューは、既定では [**フィルター** ] ボックスの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="7b5a0-116">標準フィルターには、**すべてのユーザー**、**ライセンスユーザー**、**ゲストユーザー**、**サインインが許可さ**れた、**サインインがブロック**された、ライセンスのない**ユーザー**、**エラーのあるユーザー、エラーがあるユーザー**、管理**者、\*\*\*\*グローバル管理**者、**ヘルプ管理**者、**サービス**管理**者、ユーザー管理の管理者**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="7b5a0-117">標準ビューは編集または削除できません。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="7b5a0-118">標準ビューに関して次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="7b5a0-p106">一部の標準ビューでは、一覧のユーザー数が 2,000 を超えると、並べ替えられていない一覧が表示されます。このような一覧で特定のユーザーを探すには、検索ボックスを使います。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="7b5a0-p107">Microsoft から Office 365 を購入したのではない場合、標準ビュー一覧に [ **課金管理者**] は表示されません。詳細については、「[管理者ロールを割り当てる](assign-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-p107">If you didn't purchase Office 365 from Microsoft, **Billing admins** don't appear in the standard views list. For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="7b5a0-123">カスタム ユーザー ビューのフィルターを選択する</span><span class="sxs-lookup"><span data-stu-id="7b5a0-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="7b5a0-124">カスタム**フィルター**ウィンドウでカスタムビューを作成および編集できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="7b5a0-125">複数のフィルター オプションを選択した場合は、選択したすべての条件に一致するユーザーを含む結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="7b5a0-126">次の例では、カナダにいる特定のドメイン上のすべてのユーザーを示す "Canadian users" (カナダのユーザー) という名前のカスタム ビューを作成する方法について示します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="7b5a0-127">**A-ドメイン**組織に複数のドメインがある場合は、使用可能なドメインのドロップダウンリストから選択できます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="7b5a0-128">**B-サインイン状態**許可またはブロックされるユーザーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="7b5a0-129">**C-場所**国のドロップダウンリストから場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="7b5a0-130">**D で割り当てられた製品ライセンス**組織で利用できるライセンスのドロップダウンリストから選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="7b5a0-131">選択したライセンスが割り当てられているユーザーを表示するには、このフィルターを使います。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="7b5a0-132">ユーザーは追加のライセンスを持っている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="7b5a0-133">部門、市区町村、都道府県、国/地域、役職など、組織で使用される追加のユーザー プロファイルの詳細を使ってフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="7b5a0-134">**その他の条件:**</span><span class="sxs-lookup"><span data-stu-id="7b5a0-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="7b5a0-135">**同期済みユーザーのみ** アクティブ化されているかどうかにかかわらず、ローカルの Active Directory と同期されているすべてのユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="7b5a0-136">**エラーのあるユーザー** プロビジョニング エラーがある可能性のあるユーザーを表示するには、このボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="7b5a0-p110">**ライセンス未付与のユーザー** ライセンスが付与されていないすべてのユーザーを表示するには、このボックスをオンにします。このビューの結果には、Exchange メールボックスは持っていてもライセンスを持たないユーザーも含まれる場合があります。特にこのようなユーザーを追跡するには、[ **Exchange のメールボックスまたはアーカイブはあるがライセンスがないユーザー**] フィルターを使用します。このビューの結果には、Exchange アーカイブは持っていてもライセンスを持たないユーザーも含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="7b5a0-p111">**Exchange のメールボックスまたはアーカイブはあるがライセンスがないユーザー**Exchange Online で作成され、Exchange メールボックスはあるが、Office 365 ライセンスが割り当てられていないユーザー アカウントを表示するには、このボックスをオンにします。このフィルターの結果には、Exchange アーカイブが割り当てられたユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-p111">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Office 365 license. The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 
    
> [!TIP]
> <span data-ttu-id="7b5a0-143">2,000 を超えるユーザーを返すカスタム ビューを作成すると、結果のユーザー一覧は並べ替えられません。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="7b5a0-144">この場合は、検索ボックスを使用してユーザーを検索するか、カスタムビューを編集して検索を絞り込んでください。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="7b5a0-145">カスタムユーザービューを作成する</span><span class="sxs-lookup"><span data-stu-id="7b5a0-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b5a0-146">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="7b5a0-147">[**アクティブなユーザー** ] ページで、[**フィルター** ] を選択し、[**新しいフィルター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="7b5a0-148">[**カスタムフィルター** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="7b5a0-149">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b5a0-150">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-150">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="7b5a0-151">[**アクティブなユーザー** ] ページで、[**ビュー** ] を選択し、[**カスタムビューの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="7b5a0-152">[**カスタムビュー** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="7b5a0-153">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b5a0-154">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-154">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="7b5a0-155">[**アクティブなユーザー** ] ページで、[**ビュー** ] を選択し、[**カスタムビューの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="7b5a0-156">[**カスタムビュー** ] ページで、フィルターの名前を入力して、カスタムフィルターの条件を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="7b5a0-157">これで、カスタムビューがフィルターのドロップダウンリストに含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="7b5a0-158">カスタムユーザービューを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="7b5a0-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7b5a0-159">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="7b5a0-160">[**アクティブなユーザー** ] ページで、[**フィルター**] を選択し、変更するフィルターを選択して、[**フィルターの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7b5a0-161">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="7b5a0-162">[**カスタムフィルター** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="7b5a0-163">または、フィルターを削除するには、ページの下部にある [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="7b5a0-164">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="7b5a0-165">[**アクティブなユーザー** ] ページで、[**ビュー**] を選択し、変更するフィルターを選択してから、[**このビューの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7b5a0-166">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="7b5a0-167">[**カスタムビュー** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="7b5a0-168">または、フィルターを削除するには、ページの下部にある [**カスタムビューの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7b5a0-169">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="7b5a0-170">[**アクティブなユーザー** ] ページで、[**ビュー**] を選択し、変更するフィルターを選択してから、[**このビューの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="7b5a0-171">編集できるのはカスタム ビューだけです。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="7b5a0-172">[**カスタムビュー** ] ページで、必要に応じて情報を編集し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="7b5a0-173">または、フィルターを削除するには、ページの下部にある [**カスタムビューの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7b5a0-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     
