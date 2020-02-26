---
title: Office 365 グループを作成できるユーザーを管理する
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: Office 365 グループを作成できるユーザーを制御する方法について説明します。
ms.openlocfilehash: a211cb3b69348a4d4a401a3c318fe019d8fd257f
ms.sourcegitcommit: 109b44aa71bb8453d0a602663df0fcf7ed7dfdbe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "42277194"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="185ff-103">Office 365 グループを作成できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="185ff-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="185ff-104">Office 365 グループは簡単に作成できるため、ユーザーが他のユーザーの代理でグループの作成を依頼されることはあまりありません。</span><span class="sxs-lookup"><span data-stu-id="185ff-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="185ff-105">ただし、業務によっては、グループを作成できるユーザーを制御したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="185ff-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="185ff-106">この記事では、次に示す、**グループを使用するすべての Office 365 サービスで**グループを作成できないようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="185ff-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="185ff-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="185ff-107">Outlook</span></span>
    
- <span data-ttu-id="185ff-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="185ff-108">SharePoint</span></span>
    
- <span data-ttu-id="185ff-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="185ff-109">Yammer</span></span>
    
- <span data-ttu-id="185ff-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="185ff-110">Microsoft Teams</span></span>

- <span data-ttu-id="185ff-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="185ff-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="185ff-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="185ff-112">StaffHub</span></span>
    
- <span data-ttu-id="185ff-113">Planner</span><span class="sxs-lookup"><span data-stu-id="185ff-113">Planner</span></span>
    
- <span data-ttu-id="185ff-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="185ff-114">PowerBI</span></span>

- <span data-ttu-id="185ff-115">ロードマップ</span><span class="sxs-lookup"><span data-stu-id="185ff-115">Roadmap</span></span>
    
<span data-ttu-id="185ff-116">Office 365 グループの作成を特定のセキュリティグループのメンバーに制限することができます。</span><span class="sxs-lookup"><span data-stu-id="185ff-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="185ff-117">制限するには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="185ff-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="185ff-118">この記事では、必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="185ff-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="185ff-119">この記事の手順を実行しても、特定の役割のメンバーがグループを作成できなくなることはありません。</span><span class="sxs-lookup"><span data-stu-id="185ff-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="185ff-120">Office 365 のグローバル管理者は、Microsoft 365 管理センター、Planner、Teams、Exchange、SharePoint Online などの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="185ff-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="185ff-121">他の役割は、以下のような制限付きの方法でグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="185ff-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="185ff-122">Exchange 管理者: Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="185ff-123">パートナー レベル 1 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="185ff-124">パートナー レベル 2 のサポート: Microsoft 365 管理センター、Exchange 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="185ff-125">ディレクトリ製作者: Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="185ff-126">SharePoint 管理者: SharePoint 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="185ff-127">Teams サービス管理者: Teams 管理センター、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="185ff-128">ユーザー管理の管理者: Microsoft 365 管理センター、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="185ff-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="185ff-129">これらの役割のいずれかのメンバーである場合は、制限付きユーザーに対して Office 365 グループを作成し、ユーザーをグループの所有者として割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="185ff-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="185ff-130">この役割を持つユーザーは、作成を妨げる可能性のある PowerShell 設定に関係なく、Yammer で接続済みグループを作成できます。</span><span class="sxs-lookup"><span data-stu-id="185ff-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="185ff-131">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="185ff-131">Licensing requirements</span></span>

<span data-ttu-id="185ff-132">グループを作成するユーザーを管理するには、以下のユーザーが Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="185ff-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="185ff-133">これらのグループ作成の設定を管理している管理者</span><span class="sxs-lookup"><span data-stu-id="185ff-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="185ff-134">グループの作成が許可されているセキュリティグループのメンバー</span><span class="sxs-lookup"><span data-stu-id="185ff-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="185ff-135">以下のユーザーは Azure AD Premium ライセンスまたは Azure AD Basic EDU のライセンスが割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="185ff-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="185ff-136">Office 365 グループのメンバーであり、他のグループを作成できないユーザー。</span><span class="sxs-lookup"><span data-stu-id="185ff-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="185ff-137">手順 1: Office 365 グループを作成する必要があるユーザーのセキュリティ グループを作成する</span><span class="sxs-lookup"><span data-stu-id="185ff-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="185ff-138">グループを作成できるユーザーを制御するために使用できる組織内のセキュリティ グループは 1 つです。</span><span class="sxs-lookup"><span data-stu-id="185ff-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="185ff-139">ただし、このグループのメンバーとして、他のセキュリティ グループをネストすることができます。</span><span class="sxs-lookup"><span data-stu-id="185ff-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="185ff-140">たとえば、Allow Group Creation という名前のグループが指定されたセキュリティ グループで、Microsoft Planner Users and Exchange Online Users という名前のグループがそのグループのメンバーであるとします。</span><span class="sxs-lookup"><span data-stu-id="185ff-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="185ff-141">上記の役割の管理者は、このグループのメンバーである必要はなく、グループを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="185ff-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="185ff-142">グループを作成できるユーザーを制限するには、必ず **セキュリティー グループ** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="185ff-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="185ff-143">Office 365 グループを使用しようとすると、SharePoint がセキュリティ グループをチェックするため、メンバーは SharePoint からグループを作成することができません。</span><span class="sxs-lookup"><span data-stu-id="185ff-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="185ff-144">管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="185ff-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="185ff-145">[**グループの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="185ff-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="185ff-146">グループの種類として [**セキュリティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="185ff-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="185ff-147">グループの名前は覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="185ff-147">Remember the name of the group!</span></span> <span data-ttu-id="185ff-148">後で必要になります。</span><span class="sxs-lookup"><span data-stu-id="185ff-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="185ff-149">セキュリティ グループの設定を完了し、組織内でのグループの作成を許可するユーザーまたは他のセキュリティ グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="185ff-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="185ff-150">詳細については、「[Microsoft 365 管理センターでのセキュリティ グループの作成、編集、または削除](../email/create-edit-or-delete-a-security-group.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="185ff-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="185ff-151">手順 2: Graph 用 Azure Active Directory PowerShell のプレビュー バージョンをインストールする</span><span class="sxs-lookup"><span data-stu-id="185ff-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="185ff-152">ここでは、Graph 用 Azure Active Directory PowerShell のプレビュー バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="185ff-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="185ff-153">GA バージョンでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="185ff-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="185ff-154">同じコンピューターにプレビュー バージョンと GA バージョンの両方を同時にインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="185ff-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="185ff-155">このモジュールは、windows 10、Windows Server 2016 にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="185ff-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="185ff-156">最適な対応方法として、 *常に*  最新のバージョンにしておくことをお勧めします。古い AzureADPreview バージョンまたは古い AzureAD バージョンをアンインストールして、最新のバージョンを取得してください。</span><span class="sxs-lookup"><span data-stu-id="185ff-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="185ff-157">検索バーに「Windows PowerShell」と入力します。</span><span class="sxs-lookup"><span data-stu-id="185ff-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="185ff-158">**[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="185ff-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![[管理者として実行] で PowerShell を開く。](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
    
3. <span data-ttu-id="185ff-160">ポリシーを RemoteSigned に設定するには、 [ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)を使用します。</span><span class="sxs-lookup"><span data-stu-id="185ff-160">Set the policy to RemoteSigned by using [Set-ExecutionPolicy](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy).</span></span>
    
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
  
4. <span data-ttu-id="185ff-161">インストール済みモジュールを確認します。</span><span class="sxs-lookup"><span data-stu-id="185ff-161">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

5. <span data-ttu-id="185ff-162">AzureADPreview または AzureAD の以前のバージョンをアンインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="185ff-162">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="185ff-163">または</span><span class="sxs-lookup"><span data-stu-id="185ff-163">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

6. <span data-ttu-id="185ff-164">AzureADPreview の最新のバージョンをインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="185ff-164">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="185ff-165">信頼されていないリポジトリに関するメッセージに対して「**Y**」と入力します。新しいモジュールのインストールには 1 分ほどかかります。</span><span class="sxs-lookup"><span data-stu-id="185ff-165">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="185ff-166">下の手順 3 のために、PowerShell ウィンドウを開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="185ff-166">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="185ff-167">手順 3: PowerShell コマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="185ff-167">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="185ff-168">下のスクリプトを、Notepad などのテキスト エディターまたは [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise) にコピーます。</span><span class="sxs-lookup"><span data-stu-id="185ff-168">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="185ff-169">*\<SecurityGroupName\>* を、作成したセキュリティグループの名前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="185ff-169">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="185ff-170">例:</span><span class="sxs-lookup"><span data-stu-id="185ff-170">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="185ff-171">GroupCreators.ps1 としてファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="185ff-171">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="185ff-172">PowerShell ウィンドウで、ファイルを保存した場所に移動 します ("CD <FileLocation>" と入力)。</span><span class="sxs-lookup"><span data-stu-id="185ff-172">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="185ff-173">次のように入力してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="185ff-173">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="185ff-174">サインインを求められたら、[管理者アカウントでサインイン](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)します。</span><span class="sxs-lookup"><span data-stu-id="185ff-174">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="185ff-175">スクリプトの最後の行に、更新された設定が表示されます。</span><span class="sxs-lookup"><span data-stu-id="185ff-175">The last line of the script will display the updated settings:</span></span>

![完了すると、設定は次のように表示されます。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="185ff-177">使用するセキュリティグループを変更する場合は、新しいセキュリティグループの名前でスクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="185ff-177">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="185ff-178">グループ作成の制限をオフにして、もう一度すべてのユーザーがグループを作成できるようにするには、$GroupName を "" に、$AllowGroupCreation を "True" に設定して、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="185ff-178">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="185ff-179">手順 4: 動作することを確認する</span><span class="sxs-lookup"><span data-stu-id="185ff-179">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="185ff-180">グループを作成できないユーザーのアカウントで Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="185ff-180">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="185ff-181">作成したセキュリティ グループのメンバーまたは管理者ではないユーザーのアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="185ff-181">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="185ff-182">[**Planner**] タイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="185ff-182">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="185ff-183">Planner では、左側のナビゲーションで **[新しいプラン]** を選択してプランを作成します。</span><span class="sxs-lookup"><span data-stu-id="185ff-183">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="185ff-184">プランとグループの作成が無効になっていることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="185ff-184">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="185ff-185">セキュリティグループのメンバーと同じ手順をもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="185ff-185">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="185ff-186">セキュリティグループのメンバーがグループを作成できない場合は、そのグループが [OWA メールボックス ポリシー](https://go.microsoft.com/fwlink/?linkid=852135) によってブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="185ff-186">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="185ff-187">関連記事</span><span class="sxs-lookup"><span data-stu-id="185ff-187">Related articles</span></span>

[<span data-ttu-id="185ff-188">Office 365 PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="185ff-188">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="185ff-189">セルフサービス グループ管理に必要な Azure Active Directory の設定</span><span class="sxs-lookup"><span data-stu-id="185ff-189">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="185ff-190">ExecutionPolicy の設定</span><span class="sxs-lookup"><span data-stu-id="185ff-190">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="185ff-191">グループ設定を構成するための Azure Active Directory コマンドレット</span><span class="sxs-lookup"><span data-stu-id="185ff-191">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)