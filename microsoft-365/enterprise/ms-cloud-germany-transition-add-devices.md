---
title: Microsoft クラウドの移行に関するその他のデバイス情報
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '概要: 新しいドイツデータセンターリージョンの Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 services に移行する場合の、サービスに関する追加のデバイス情報。'
ms.openlocfilehash: 941b836871f4ffb7f39f6e144675e9ee15510270
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560861"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="55b0c-103">Microsoft クラウドの移行に関するその他のデバイス情報</span><span class="sxs-lookup"><span data-stu-id="55b0c-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="55b0c-104">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="55b0c-104">Frequently asked questions</span></span>

<span data-ttu-id="55b0c-105">**組織に影響があるかどうかを確認するには、どうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="55b0c-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="55b0c-106">管理者は、 `https://portal.microsoftazure.de` 登録済みデバイスがあるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="55b0c-107">組織にデバイスが登録されている場合は、影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="55b0c-108">**ユーザーにどのような影響があるか。**</span><span class="sxs-lookup"><span data-stu-id="55b0c-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="55b0c-109">登録済みデバイスのユーザーは、移行後に [AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) 移行フェーズを終了した後、サインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="55b0c-110">組織が Microsoft Cloud Deut上陸陸から切断される前に、すべてのデバイスがワールドワイドエンドポイントに登録されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="55b0c-111">**ユーザーが自分のデバイスを再登録するのはいつですか。**</span><span class="sxs-lookup"><span data-stu-id="55b0c-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="55b0c-112">[Microsoft Cloud Deut/陸](ms-cloud-germany-transition.md#how-is-the-migration-organized)の移行フェーズとは別に、デバイスの登録を解除して再登録することは、成功にとって不可欠です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="55b0c-113">**移行後にデバイスの状態を復元するにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="55b0c-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="55b0c-114">Azure AD に登録されているハイブリッド Azure AD –参加済みおよび会社所有の Windows デバイスでは、管理者は、古いデバイス状態の登録を解除するリモートでトリガーされたワークフローを使用してこれらのデバイスの移行を管理できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="55b0c-115">他のすべてのデバイス (Azure AD に登録されている個人の Windows デバイスを含む) については、エンドユーザーはこれらの手順を手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="55b0c-116">Azure AD と参加しているデバイスの場合、ユーザーはローカル管理者アカウントを持っている必要があります。デバイスの登録を解除してから登録し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="55b0c-117">Microsoft は、デバイス状態を正常に復元する方法についての指示を公開します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="55b0c-118">**パブリッククラウドにすべてのデバイスが登録されていることを確認するには、どうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="55b0c-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="55b0c-119">デバイスがパブリッククラウドに登録されているかどうかを確認するには、Azure AD ポータルから Excel スプレッドシートにデバイスの一覧をエクスポートしてダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="55b0c-120">その後、 [Microsoft Cloud Deut上陸土地](ms-cloud-germany-transition.md#how-is-the-migration-organized)移行フェーズとは別に、登録されているデバイス ( _registeredtime_ 列を使用) にフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="55b0c-121">テナントの移行後はデバイスの登録が非アクティブになり、有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="55b0c-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="55b0c-122">Intune を使用しない場合は、サブスクリプションにサインインして、次のコマンドを実行してオプションを再度アクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="55b0c-123">Windows ハイブリッド Azure AD join</span><span class="sxs-lookup"><span data-stu-id="55b0c-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="55b0c-124">Windows ダウンレベル</span><span class="sxs-lookup"><span data-stu-id="55b0c-124">Windows down-level</span></span>

<span data-ttu-id="55b0c-125">_Windows ダウンレベルデバイス_ は、以前のバージョンの Windows (windows 8.1 や windows 7 など) を現在実行している windows デバイス、または2019および2016より前のバージョンの windows Server を実行している windows デバイスです。</span><span class="sxs-lookup"><span data-stu-id="55b0c-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="55b0c-126">そのようなデバイスが以前に登録されていた場合は、それらのデバイスの登録を解除してから登録し直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="55b0c-127">Windows のダウンレベルデバイスが以前 Azure AD に参加していたかどうかを確認するには、デバイス上で次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="55b0c-128">デバイスが以前 Azure AD に参加していて、デバイスがグローバルな Azure AD エンドポイントにネットワーク接続されている場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="55b0c-129">影響を受けるデバイスの "デバイス状態" に "Unknown" という値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="55b0c-130">出力が "デバイスが参加していません" または "Device state" の値が "Ok" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="55b0c-131">デバイスが (deviceId、拇印などを使用して) 結合されていて、"Device state" 値が "Unknown" であることを示すデバイスに対してのみ、次のコマンドを実行する必要があります。このようなダウンレベルデバイスでは、ドメインユーザーがサインインしています。</span><span class="sxs-lookup"><span data-stu-id="55b0c-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="55b0c-132">上記のコマンドは、Windows ダウンレベルデバイスでサインインしたドメインユーザーごとに1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="55b0c-133">このコマンドは、サインインしているドメインユーザーのコンテキストで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="55b0c-134">ユーザーが後でサインインしたときに、このコマンドを実行しないように十分な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="55b0c-135">上記のコマンドを実行すると、サインインしたユーザーについて、ローカルハイブリッド Azure AD に参加しているコンピューターの参加状態がクリアされます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="55b0c-136">また、コンピューターが依然としてハイブリッド Azure AD として構成されている場合は、テナントに参加すると、ユーザーが再度サインインするときに参加が試みられます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="55b0c-137">現在の Windows</span><span class="sxs-lookup"><span data-stu-id="55b0c-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="55b0c-138">切断</span><span class="sxs-lookup"><span data-stu-id="55b0c-138">Unjoin</span></span>

<span data-ttu-id="55b0c-139">以前に Windows 10 デバイスが Azure AD に参加していたかどうかを確認するには、デバイス上で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="55b0c-140">デバイスがハイブリッド Azure AD に参加している場合は、管理者に次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="55b0c-141">出力が "AzureAdJoined: No" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="55b0c-142">デバイスが Azure AD に参加していることを示すデバイスに対してのみ、次のコマンドを管理者として実行して、デバイスの結合状態を削除します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="55b0c-143">上記のコマンドは、Windows デバイスの管理コンテキストで1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="55b0c-144">ハイブリッド AD Join\ 再登録</span><span class="sxs-lookup"><span data-stu-id="55b0c-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="55b0c-145">デバイスがグローバルな Azure AD エンドポイントにネットワーク接続されている限り、ユーザーまたは管理者の介入なしに、デバイスは自動的に Azure AD に参加します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="55b0c-146">Windows Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="55b0c-146">Windows Azure AD Join</span></span>

<span data-ttu-id="55b0c-147">**重要:** Intune サービスプリンシパルは、commerce 移行後に有効になります。これは、Azure AD Device Registration のアクティブ化を意味します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="55b0c-148">移行の前に Azure AD Device Registration をブロックした場合は、PowerShell を使用して Intune サービスプリンシパルを無効にし、azure ad ポータルとの azure ad Device 登録を再度無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="55b0c-149">[Azure Active Directory PowerShell for Graph] モジュールで、このコマンドを使用して Intune サービスプリンシパルを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="55b0c-150">切断</span><span class="sxs-lookup"><span data-stu-id="55b0c-150">Unjoin</span></span>

<span data-ttu-id="55b0c-151">Windows 10 デバイスが以前 Azure AD に参加していたかどうかを確認するには、ユーザーまたは管理者がデバイス上で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="55b0c-152">デバイスが Azure AD に参加している場合、ユーザーまたは管理者には次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="55b0c-153">出力が "AzureAdJoined: NO" の場合は、次のガイダンスは無視してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="55b0c-154">ユーザー: デバイスが Azure AD に参加している場合、ユーザーはそのデバイスを設定から離すことができます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="55b0c-155">Azure AD からデバイスを unjoining する前に、デバイスのローカル管理者アカウントが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="55b0c-156">ローカル管理者アカウントは、デバイスにサインインし直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="55b0c-157">管理者: 組織の管理者が Azure AD に参加しているユーザーのデバイスを離れる場合は、グループポリシーなどのメカニズムを使用して、各デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="55b0c-158">管理者は、Azure AD からデバイスを unjoining する前に、デバイスにローカル管理者アカウントがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="55b0c-159">ローカル管理者アカウントは、デバイスにサインインし直すために必要です。</span><span class="sxs-lookup"><span data-stu-id="55b0c-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="55b0c-160">上記のコマンドは、Windows デバイスの管理コンテキストで1回だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="55b0c-161">Azure AD 参加/再登録</span><span class="sxs-lookup"><span data-stu-id="55b0c-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="55b0c-162">ユーザーは、Windows の設定から Azure AD にデバイスを参加させることができます。 **設定 > アカウント > Access の職場または学校 > Connect**。</span><span class="sxs-lookup"><span data-stu-id="55b0c-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="55b0c-163">登録されている Windows Azure AD (会社の所有)</span><span class="sxs-lookup"><span data-stu-id="55b0c-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="55b0c-164">Windows 10 デバイスが Azure AD に登録されているかどうかを確認するには、デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="55b0c-165">デバイスが Azure AD に登録されている場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="55b0c-166">デバイス上の既存の Azure AD 登録アカウントを削除するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="55b0c-167">デバイス上の Azure AD に登録されているアカウントを削除するには、次の場所からダウンロードできる CleanupWPJ を使用します。 [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)。</span><span class="sxs-lookup"><span data-stu-id="55b0c-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="55b0c-168">ZIP ファイルを展開して、 **Wpjcleanup コマンド** を実行します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="55b0c-169">このツールは、デバイス上の Windows のバージョンに基づいて、適切な実行可能ファイルを起動します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="55b0c-170">グループポリシーなどのメカニズムを使用すると、管理者はデバイス上でサインインしているユーザーのコンテキストで、デバイス上でコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="55b0c-171">Azure AD にデバイスを登録するために Web アカウントマネージャーの音声ガイダンスを無効にするには、次のレジストリ値を追加します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="55b0c-172">場所: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="55b0c-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="55b0c-173">型: DWORD (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="55b0c-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="55b0c-174">名前: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="55b0c-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="55b0c-175">値のデータ: 1</span><span class="sxs-lookup"><span data-stu-id="55b0c-175">Value data: 1</span></span>

<span data-ttu-id="55b0c-176">このレジストリ値が存在すると、workplace join がブロックされ、ユーザーがデバイスに参加するように求めるメッセージを表示できなくなります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="55b0c-177">Android</span><span class="sxs-lookup"><span data-stu-id="55b0c-177">Android</span></span>

<span data-ttu-id="55b0c-178">Android の場合、ユーザーはデバイスの登録を解除して、再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="55b0c-179">これは、Microsoft Authenticator アプリまたはポータルサイトアプリを使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="55b0c-180">Microsoft Authenticator アプリから、ユーザーは [ **設定 > デバイス登録**] に移動できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="55b0c-181">この場合、ユーザーは自分のデバイスの登録を解除して再登録することができます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="55b0c-182">ポータルサイトから、ユーザーは [ **デバイス** ] タブに移動してデバイスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="55b0c-183">その後、会社のポータルを使用してデバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="55b0c-184">ユーザーは、[アカウント設定] ページからアカウントを削除してから、もう一度作業アカウントを追加することによって、登録を解除して再登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="55b0c-185">Microsoft Authenticator アプリを使用して Android でデバイスの登録を解除して再登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="55b0c-186">Microsoft Authenticator アプリを開いて [ **設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="55b0c-187">[ **デバイス登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="55b0c-188">[ **登録解除**] を選択してデバイスの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="55b0c-189">[ **デバイスの登録**] で、電子メールアドレスを入力してデバイスを再登録し、[ **登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="55b0c-190">Android の設定ページを使用して Android デバイスの登録を解除して再登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="55b0c-191">[ **デバイスの設定** ] を開いて、[ **アカウント**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="55b0c-192">再登録するワークアカウントを選択し、[ **アカウントの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="55b0c-193">アカウントが削除されたら、[ **アカウント** ] ページで、[ **アカウントの追加 > 作業アカウント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="55b0c-194">**Workplace Join** の場合は、電子メールアドレスを入力し、[**参加**] を選択してデバイスの登録を完了します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="55b0c-195">ポータルサイトから Android でデバイスの登録を解除して再登録するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="55b0c-196">ポータルサイトを起動して、[ **デバイス** ] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="55b0c-197">デバイスを選択して、デバイスの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="55b0c-198">省略記号 (3 つのドット) メニューから、[ **デバイスの削除**] を選択し、ダイアログで確認して削除を完了します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="55b0c-199">これで、ポータルサイトアプリからログアウトできるようになります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="55b0c-200">[ **サインイン** ] を選択して、デバイスを再登録します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="55b0c-201">このワークロードの移行フェーズ中に必要なすべての操作、または管理または使用に対する影響の詳細については、 [Microsoft Cloud Deut上陸陸からの移行に関するその他の一般的な情報](ms-cloud-germany-transition-add-general.md#azure-active-directory)について、Azure Active Directory に関する情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55b0c-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="55b0c-202">iOS</span><span class="sxs-lookup"><span data-stu-id="55b0c-202">iOS</span></span>

<span data-ttu-id="55b0c-203">IOS デバイスでは、ユーザーはキャッシュされたアカウントを Microsoft Authenticator から手動で削除し、デバイスの登録を解除して、デバイス上の任意のネイティブアプリからサインアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="55b0c-204">手順 1: 存在する場合は、Microsoft Authenticator アプリからアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="55b0c-205">Microsoft Authenticator アプリでアカウントをタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="55b0c-206">右上隅の [ **設定** ] アイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="55b0c-207">[ **設定** ] アイコンが表示されない場合は、最新バージョンの Microsoft Authenticator を使用していない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="55b0c-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="55b0c-208">[ **アカウントの削除** ] ボタンをタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="55b0c-209">**このデバイス上のすべてのアプリを** タップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="55b0c-210">手順 2: Microsoft Authenticator アプリからデバイスの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="55b0c-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="55b0c-211">右上隅にあるメニューアイコンをタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="55b0c-212">[ **設定** ]、[ **デバイス登録**] の順にタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="55b0c-213">アカウントが表示されている場合は、[ **デバイスの登録を解除** して **続行** する] をタップします。</span><span class="sxs-lookup"><span data-stu-id="55b0c-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="55b0c-214">その後、アカウントは何も表示されません。</span><span class="sxs-lookup"><span data-stu-id="55b0c-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="55b0c-215">手順 3: 必要に応じて個々のアプリからサインアウトする</span><span class="sxs-lookup"><span data-stu-id="55b0c-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="55b0c-216">ユーザーは、Outlook、Teams、OneDrive などの個別のアプリに移動したり、それらのアプリからアカウントを削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="55b0c-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="55b0c-217">詳細情報</span><span class="sxs-lookup"><span data-stu-id="55b0c-217">More information</span></span>

<span data-ttu-id="55b0c-218">はじめに:</span><span class="sxs-lookup"><span data-stu-id="55b0c-218">Getting started:</span></span>

- [<span data-ttu-id="55b0c-219">新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="55b0c-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="55b0c-220">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="55b0c-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="55b0c-221">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="55b0c-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="55b0c-222">移行中の顧客の利便性</span><span class="sxs-lookup"><span data-stu-id="55b0c-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="55b0c-223">遷移を移動します。</span><span class="sxs-lookup"><span data-stu-id="55b0c-223">Moving through the transition:</span></span>

- [<span data-ttu-id="55b0c-224">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="55b0c-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="55b0c-225">その他の準備作業</span><span class="sxs-lookup"><span data-stu-id="55b0c-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="55b0c-226">[サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。</span><span class="sxs-lookup"><span data-stu-id="55b0c-226">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="55b0c-227">クラウドアプリ:</span><span class="sxs-lookup"><span data-stu-id="55b0c-227">Cloud apps:</span></span>

- [<span data-ttu-id="55b0c-228">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="55b0c-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="55b0c-229">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="55b0c-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="55b0c-230">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="55b0c-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)