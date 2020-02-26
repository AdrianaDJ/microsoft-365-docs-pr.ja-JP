---
title: Office 365 でユーザーを復元する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: 削除された Office 365 ユーザーアカウントおよびすべての関連データを復元する方法について説明します。
ms.openlocfilehash: 385f7938f5e0ce1f3a580d40830124f77454f64d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241572"
---
# <a name="restore-a-user-in-office-365"></a><span data-ttu-id="f2759-103">Office 365 でユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="f2759-103">Restore a user in Office 365</span></span>
   
<span data-ttu-id="f2759-p101">ユーザー アカウントを削除してから 30 日以内に復元すると、そのアカウントと関連するすべてのデータが復元されます。ユーザーは同じ職場や学校のアカウントでサインインできます。ユーザーのメールボックスは完全に復元されます。特定のユーザー アカウントを復元できなくなるまでの残り時間を知るには、[サポートにお問い合わせください](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="f2759-p101">When you restore a user account within 30 days after deleting it, the account and all associated data are restored. The user can sign in with the same work or school account. Their mailbox will be fully restored. To find out how much time remains before a specific user account can no longer be restored, [contact us](../contact-support-for-business-products.md).</span></span>
  
<span data-ttu-id="f2759-108">いくつかのヒントをご紹介します。</span><span class="sxs-lookup"><span data-stu-id="f2759-108">Here are a couple of tips:</span></span>
  
- <span data-ttu-id="f2759-109">アカウントに割り当てる Office 365 ライセンスが利用できることをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="f2759-109">Make sure there are Office 365 licenses available that you can assign to the account.</span></span>
    
- <span data-ttu-id="f2759-110">Active Directory を使用している場合、ユーザー アカウントを復元する手順については、「[Office 365、Azure、Intune で削除済みのユーザー アカウントをトラブルシューティングする方法](https://support.microsoft.com/kb/2619308)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2759-110">If your business uses Active Directory, see [How to troubleshoot deleted user accounts in Office 365](https://support.microsoft.com/kb/2619308) for instructions on restoring a user account.</span></span> 
    
## <a name="restore-one-or-more-user-accounts"></a><span data-ttu-id="f2759-111">1 つ以上のユーザー アカウントを復元する</span><span class="sxs-lookup"><span data-stu-id="f2759-111">Restore one or more user accounts</span></span>

<span data-ttu-id="f2759-112">これらの手順を実行するには、Office 365 のグローバル管理者またはユーザー管理の管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2759-112">You must be a global admin or user management admin in Office 365 to do these steps.</span></span> 
  
 
::: moniker range="o365-worldwide"

1. <span data-ttu-id="f2759-113">管理センターで、[**ユーザー** \>の<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済み</a>ユーザー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f2759-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f2759-114">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=848041)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-114">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f2759-115">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=850627)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-115">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="f2759-116">[**削除済みのユーザー** ] ページで、復元するユーザーの名前を選択し、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-116">On the **Deleted users** page, select the names of the users who you want to restore, and then select **Restore**.</span></span>
    
 
3. <span data-ttu-id="f2759-117">画面の指示に従ってパスワードを設定し、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-117">Follow the prompts to set their password, and then select **Restore**.</span></span>
    
4. <span data-ttu-id="f2759-118">ユーザーが正常に復元された場合は、[**電子メールを送信して閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-118">If the user is successfully restored, select **Send email and close**.</span></span> <span data-ttu-id="f2759-119">名前の競合またはプロキシ アドレスの競合が発生した場合は、これらのアカウントの復元方法については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2759-119">If you encounter a name conflict or proxy address conflict, see the instructions below for how to restore those accounts.</span></span>
    
<span data-ttu-id="f2759-120">ユーザーを復元した後は、パスワードが変更されたことを確認してから、それに従って通知するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f2759-120">After you've restored a user, make sure you notify them that their password changed and you follow up with them.</span></span>
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a><span data-ttu-id="f2759-121">ユーザー名が競合するユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="f2759-121">Restore a user that has a user name conflict</span></span>
<span data-ttu-id="f2759-122"><a name="RestoreUserNameConflict"> </a></span><span class="sxs-lookup"><span data-stu-id="f2759-122"><a name="RestoreUserNameConflict"> </a></span></span>

<span data-ttu-id="f2759-123">ユーザー アカウントを削除し、同じユーザー名で (同じユーザーの、または名前が似ている別のユーザーの) ユーザー アカウントを新しく作成した後、削除したアカウントを復元しようとすると、ユーザー名の競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="f2759-123">A user name conflict occurs when you delete a user account, create a new user account with the same user name (either for the same user or another user with a similar name), and later try to restore the deleted account.</span></span>
  
<span data-ttu-id="f2759-p103">この問題を修正するには、アクティブなユーザー アカウントを復元しているアカウントに置き換えます。または、復元しているアカウントに別のユーザー名を割り当てて、同じユーザー名で複数のアカウントが存在しないようにします。次のように行います。</span><span class="sxs-lookup"><span data-stu-id="f2759-p103">To fix this, replace the active user account with the one that you are restoring. Or, assign a different user name to the account that you are restoring so that there aren't two accounts with the same user name. Here are the steps.</span></span>
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f2759-127">管理センターで、[**ユーザー** \>の<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済み</a>ユーザー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f2759-127">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="f2759-128">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=848041)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-128">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f2759-129">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=850627)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-129">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

  
2. <span data-ttu-id="f2759-130">[**削除済みのユーザー** ] ページで、復元するユーザーの名前を選択し、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-130">On the **Deleted users** page, select the names of the users that you want to restore, and then select **Restore**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f2759-p104">2 人以上のユーザーの復元が失敗した場合、エラー メッセージで一部のユーザーの復元操作が失敗したことが示されます。ログを見て復元されなかったユーザーを確認し、失敗したアカウントを 1 つずつ復元します。</span><span class="sxs-lookup"><span data-stu-id="f2759-p104">If two or more users fail to be restored, an error message advises you that the restore operation failed for some users. View the log to see which users were not restored, and then restore the failed accounts one at a time.</span></span> 
  
3. <span data-ttu-id="f2759-133">画面の指示に従ってパスワードを設定し、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-133">Follow the prompts to set the password and select **Restore**.</span></span>
    
4. <span data-ttu-id="f2759-p105">アカウントの復元に問題があったことを示すメッセージが表示されます。次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f2759-p105">A message pops up that says there was a problem restoring the account. Do one of the following:</span></span>
    
  - <span data-ttu-id="f2759-p106">復元をキャンセルし、現在のアクティブなユーザーの名前を変更します。もう一度復元を試みます。</span><span class="sxs-lookup"><span data-stu-id="f2759-p106">Cancel the restore and rename the current active user. Then attempt the restore again.</span></span>
    
  - <span data-ttu-id="f2759-138">または、ユーザーの新しいプライマリ電子メールアドレスを入力して、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-138">OR, type a new primary email address for the user and select **Restore**.</span></span>
    
5. <span data-ttu-id="f2759-139">結果を確認し、[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f2759-139">Review the results, and then select **Close**.</span></span>
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a><span data-ttu-id="f2759-140">プロキシ アドレスが競合するユーザーを復元する</span><span class="sxs-lookup"><span data-stu-id="f2759-140">Restore a user that has a proxy address conflict</span></span>

<span data-ttu-id="f2759-p107">プロキシ アドレスを含むユーザー アカウントを削除し、同じプロキシ アドレスを別のアカウントに割り当てた後、削除したアカウントを復元しようとすると、プロキシ アドレスの競合が発生します。この問題を解決するには、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="f2759-p107">A proxy address conflict occurs when you delete a user account that contains a proxy address, assign the same proxy address to another account, and then try to restore the deleted account. Follow the steps below to fix this issue.</span></span>
  
<span data-ttu-id="f2759-143">Office 365 でこれを行うには、[管理者権限](about-admin-roles.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2759-143">You must have [admin permissions](about-admin-roles.md) in Office 365 to do this.</span></span> 
  

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f2759-144">管理センターで、[**ユーザー** \>の<a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">削除済み</a>ユーザー] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="f2759-144">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">Deleted users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f2759-145">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=848041)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-145">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f2759-146">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=850627)に移動し、[**ユーザー** \>が**削除されました**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-146">Go to the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), and then select **Users** \> **Deleted users**.</span></span>

::: moniker-end

2. <span data-ttu-id="f2759-147">[ **削除済みのユーザー**] ページで、復元するユーザーを選択して、[ **復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-147">On the **Deleted users** page, select the user that you want to restore, and then select **Restore**.</span></span> 
    
3. <span data-ttu-id="f2759-148">[**復元**] ページで、指示に従ってパスワードを設定し、[**復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2759-148">On the **Restore** page, follow the instructions to set the password and select **Restore**.</span></span> <span data-ttu-id="f2759-149">競合しているプロキシ アドレスは、復元したユーザーから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="f2759-149">Any conflicting proxy addresses are automatically removed from the user you are restoring.</span></span>
    
4. <span data-ttu-id="f2759-150">結果を確認し、[ **閉じる**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="f2759-150">Review the results, and then select **Close**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f2759-151">関連記事</span><span class="sxs-lookup"><span data-stu-id="f2759-151">Related articles</span></span>

[<span data-ttu-id="f2759-152">ユーザーの削除</span><span class="sxs-lookup"><span data-stu-id="f2759-152">Delete a user</span></span>](delete-a-user.md)
  
