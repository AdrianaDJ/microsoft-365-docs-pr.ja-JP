---
title: Microsoft クラウドの移行に関するその他の一般的な情報
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
description: '概要: 新しいドイツデータセンターリージョンの Microsoft Cloud ドイツ (Microsoft Cloud Deut上陸ランド) から Office 365 services に移行する際の、サービスに関するその他の一般的な情報。'
ms.openlocfilehash: 93692200f2519dbc647bb4e81b4bd8c646815858
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558432"
---
# <a name="additional-general-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="f850e-103">Microsoft クラウドの移行に関するその他の一般的な情報</span><span class="sxs-lookup"><span data-stu-id="f850e-103">Additional general information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="f850e-104">次のセクションでは、サービス、作業前の考慮事項、および顧客の操作に関する追加情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="f850e-104">The following sections provide additional information on services, pre-work considerations, and customer experience.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="f850e-105">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f850e-105">Azure Active Directory</span></span>

<span data-ttu-id="f850e-106">Azure ドイツ cloud から Azure パブリッククラウドへの移行を完了するには、アプリケーション用の認証エンドポイント、Azure Active Directory (Azure AD) グラフ、および MS Graph エンドポイントを、OpenID Connect (OIDC) エンドポイントの報告を開始する際に商用クラウドのエンドポイントに更新することをお勧め `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` します。</span><span class="sxs-lookup"><span data-stu-id="f850e-106">To complete the move from the Azure German cloud to the Azure public cloud we recommend that the authentication endpoint, Azure Active Directory (Azure AD) Graph, and MS Graph endpoints for your applications be updated to those of the commercial cloud when the OpenID Connect (OIDC) endpoint, `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration`, starts reporting commercial cloud endpoints.</span></span> 
 
<span data-ttu-id="f850e-107">**いつこの変更を行う必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="f850e-107">**When should I make this change?**</span></span>

<span data-ttu-id="f850e-108">テナントがドイツのクラウドから商用クラウドへの移行を完了すると、Azure/Office ポータルに通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-108">You'll receive a notification in Azure/Office portal when your tenant completes migration from German cloud to the commercial cloud.</span></span> <span data-ttu-id="f850e-109">この通知を受信してから30日以内であれば、アプリは Azure ドイツ cloud から Azure パブリッククラウドに移行されるテナントに対して引き続き作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f850e-109">You have 30 days after receiving this notification to complete these updates so that your app continues to work for tenants that are migrated from Azure Germany cloud to Azure Public cloud.</span></span>
 
<span data-ttu-id="f850e-110">サインイン権限を更新するには、次の3つの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-110">There are three preconditions to updating your sign-in authority:</span></span>

 - <span data-ttu-id="f850e-111">テナントの OIDC discovery エンドポイントは、 `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` AZURE AD パブリッククラウドエンドポイントを返します。</span><span class="sxs-lookup"><span data-stu-id="f850e-111">OIDC discovery endpoint for your tenant `https://login.microsoftonline.com/\<TenantIdOrDomain\>/.well-known/openid-configuration` returns Azure AD public cloud endpoints.</span></span>

 - <span data-ttu-id="f850e-112">テナントがフェデレーション用にセットアップされている場合、Active Directory フェデレーションサービス (AD FS) は Azure AD パブリックと同期するように更新されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-112">If your tenant is set up for federation, Active Directory Federation Services (AD FS) is updated to sync with Azure AD Public.</span></span> <span data-ttu-id="f850e-113">この変更を行うには、手順に従って Azure AD Connect 設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="f850e-113">You can follow instructions to update Azure AD Connect settings for making this change.</span></span>

 - <span data-ttu-id="f850e-114">アプリケーションによって使用されるリソースアプリケーションは、Azure AD ドイツと Azure AD パブリックの両方によって署名されたトークンを受け付けるように変更されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-114">Resource applications, if any, used by your applications are modified to accept tokens that are signed by both Azure AD Germany and Azure AD Public.</span></span>
 
<span data-ttu-id="f850e-115">**アプリケーションの種類**</span><span class="sxs-lookup"><span data-stu-id="f850e-115">**What kind of applications?**</span></span>

<span data-ttu-id="f850e-116">アプリケーションには、次のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f850e-116">An application could be any of the following:</span></span>

- [<span data-ttu-id="f850e-117">シングルページアプリ (SPA)</span><span class="sxs-lookup"><span data-stu-id="f850e-117">Single-page app (SPA)</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-spa-overview)
- [<span data-ttu-id="f850e-118">ユーザーにサインインする Web アプリ</span><span class="sxs-lookup"><span data-stu-id="f850e-118">Web app that signs in users</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-sign-user-overview)
- [<span data-ttu-id="f850e-119">Web Api を呼び出す web アプリ</span><span class="sxs-lookup"><span data-stu-id="f850e-119">Web app that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-app-call-api-overview)
- [<span data-ttu-id="f850e-120">保護された web API</span><span class="sxs-lookup"><span data-stu-id="f850e-120">Protected web API</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview)
- [<span data-ttu-id="f850e-121">Web api を呼び出す web API</span><span class="sxs-lookup"><span data-stu-id="f850e-121">Web API that calls web APIs</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-web-api-call-api-overview)
- [<span data-ttu-id="f850e-122">デスクトップ アプリ</span><span class="sxs-lookup"><span data-stu-id="f850e-122">Desktop app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-desktop-overview)
- [<span data-ttu-id="f850e-123">デーモンアプリ</span><span class="sxs-lookup"><span data-stu-id="f850e-123">Daemon app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-daemon-overview)
- [<span data-ttu-id="f850e-124">モバイル アプリ</span><span class="sxs-lookup"><span data-stu-id="f850e-124">Mobile app</span></span>](https://docs.microsoft.com/azure/active-directory/develop/scenario-mobile-overview)
 
> [!NOTE] 
> <span data-ttu-id="f850e-125">アプリケーションが権限としてを使用するように切り替えると `login.microsoftonline.com` 、この新しい権限によってトークンが署名されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-125">When an application switches to using `login.microsoftonline.com` as your authority, the tokens will be signed by this new authority.</span></span> <span data-ttu-id="f850e-126">他のアプリから呼び出されるリソースアプリケーションをホストしている場合は、有効なトークン検証を許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-126">If you host any resource applications that other apps call into, you will need to allow for lax token validation.</span></span> <span data-ttu-id="f850e-127">これは、アプリが Azure AD ドイツと Azure AD パブリッククラウドの両方によって署名されたトークンを許可する必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f850e-127">This means that your app needs to allow tokens that are signed by both the Azure AD Germany and Azure AD public clouds.</span></span> <span data-ttu-id="f850e-128">この柔軟なトークン検証は、サービスを呼び出すすべてのクライアントアプリケーションが Azure AD パブリッククラウドに完全に移行されるまで必要です。</span><span class="sxs-lookup"><span data-stu-id="f850e-128">This lax token validation is needed until all client applications that call your service are fully migrated to the Azure AD public cloud.</span></span> <span data-ttu-id="f850e-129">移行後、リソースアプリケーションは、Azure AD パブリッククラウドによって署名されたトークンのみを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-129">After migration, your resource application only needs to accept tokens signed by the Azure AD public cloud.</span></span>

<span data-ttu-id="f850e-130">**更新する必要があるもの**</span><span class="sxs-lookup"><span data-stu-id="f850e-130">**What do I need to update?**</span></span>

1. <span data-ttu-id="f850e-131">Azure ドイツユーザーまたは Office 365 ドイツユーザーの認証に使用される Azure ドイツのアプリケーションをホストしている場合は、 `https://login.microsoftonline.com` が認証コンテキストの権限として使用されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f850e-131">If you're hosting an application in Azure Germany that is used to authenticate Azure Germany or Office 365 Germany users, ensure that `https://login.microsoftonline.com` is used as the authority in the authentication context.</span></span>

    - <span data-ttu-id="f850e-132">「Azure AD 認証コンテキスト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f850e-132">See Azure AD authentication contexts.</span></span>
    - <span data-ttu-id="f850e-133">これは、アプリケーションに対する認証に加えて、アプリケーションが呼び出している Api (Microsoft Graph、Azure AD Graph、Azure Resource Manager) に対する認証にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-133">This applies both to authentication to your application as well as authentication to any APIs that your application may be calling (that is, Microsoft Graph, Azure AD Graph, Azure Resource Manager).</span></span>

2. <span data-ttu-id="f850e-134">Azure AD Graph エンドポイントをに更新 `https://graph.windows.net` します。</span><span class="sxs-lookup"><span data-stu-id="f850e-134">Update Azure AD Graph endpoint to be `https://graph.windows.net`.</span></span>

3. <span data-ttu-id="f850e-135">MS Graph エンドポイントをに更新 `https://graph.microsoft.com` します。</span><span class="sxs-lookup"><span data-stu-id="f850e-135">Update MS Graph endpoint to be `https://graph.microsoft.com`.</span></span>

4. <span data-ttu-id="f850e-136">アプリケーションによって使用されるドイツのクラウドエンドポイント (Exchange Online や SharePoint Online など) を、パブリッククラウドのものに更新します。</span><span class="sxs-lookup"><span data-stu-id="f850e-136">Update any German cloud endpoints (such as those for Exchange Online and SharePoint Online) that are used by your applications to be those of the public cloud.</span></span>

5. <span data-ttu-id="f850e-137">`AzurePublic` `AzureGermany` 次のための管理ツールおよびスクリプトで、環境パラメーター (ではなく) を更新します。</span><span class="sxs-lookup"><span data-stu-id="f850e-137">Update environment parameters to be `AzurePublic` (instead of `AzureGermany`) in administrative tools and scripts for:</span></span>

    - [<span data-ttu-id="f850e-138">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f850e-138">Azure PowerShell</span></span>](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.8.0&viewFallbackFrom=azurermps-5.6.0)
    - [<span data-ttu-id="f850e-139">Azure AD PowerShell (MSOnline)</span><span class="sxs-lookup"><span data-stu-id="f850e-139">Azure AD PowerShell (MSOnline)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)
    - [<span data-ttu-id="f850e-140">Azure AD PowerShell (AzureAD)</span><span class="sxs-lookup"><span data-stu-id="f850e-140">Azure AD PowerShell (AzureAD)</span></span>](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)
    - [<span data-ttu-id="f850e-141">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="f850e-141">Azure CLI</span></span>](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest)
 
<span data-ttu-id="f850e-142">**公開するアプリケーションについて**</span><span class="sxs-lookup"><span data-stu-id="f850e-142">**What about applications that I publish?**</span></span>

<span data-ttu-id="f850e-143">テナントの外部にいるユーザーが使用できるアプリケーションを公開する場合は、アプリケーションの登録を変更して継続性を確保する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-143">If you publish an application that is available to users who are outside of your tenant, you may need to change your application registration to ensure continuity.</span></span> <span data-ttu-id="f850e-144">アプリケーションを使用する他のテナントは、テナントとは別の時間に移動する場合があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-144">Other tenants that use your application may be moved at a different time than your tenant.</span></span> <span data-ttu-id="f850e-145">アプリケーションへのアクセスが失われないようにするには、Azure ドイツから Azure パブリックに同期するアプリに同意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-145">To ensure that they never lose access to your application, you'll need to consent to your app being synchronized from Azure Germany to Azure public.</span></span>

### <a name="additional-considerations"></a><span data-ttu-id="f850e-146">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="f850e-146">Additional considerations</span></span>

<span data-ttu-id="f850e-147">Azure AD に関するその他の考慮事項を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f850e-147">Here are some additional considerations for Azure AD:</span></span>

- <span data-ttu-id="f850e-148">フェデレーション認証の場合:</span><span class="sxs-lookup"><span data-stu-id="f850e-148">For federated authentication:</span></span>

  - <span data-ttu-id="f850e-149">テナント遷移の処理中は、フェデレーションドメインの作成、昇格、または降格は行わないでください。</span><span class="sxs-lookup"><span data-stu-id="f850e-149">You must not create, promote, or demote a federated domain while the tenant transition is in process.</span></span> <span data-ttu-id="f850e-150">Azure AD サービスへの移行が完了したら (テナントは完全に完了)、フェデレーションドメインの管理を再開できます。</span><span class="sxs-lookup"><span data-stu-id="f850e-150">After the migration to the Azure AD service is complete (the tenant is fully complete), you can resume managing federated domains.</span></span>

  - <span data-ttu-id="f850e-151">Active Directory フェデレーションサービス (AD FS) でフェデレーション認証を使用している場合は、移行中に社内の Active Directory ドメインサービス (AD DS) ですべての認証に使用される発行者 Uri を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="f850e-151">If you're using federated authentication with Active Directory Federation Services (AD FS), you shouldn't make changes to Issuer URIs used for all authentication with your on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="f850e-152">発行者 Uri を変更すると、ドメイン内のユーザーに対する認証エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f850e-152">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="f850e-153">発行者 Uri は、AD FS で直接変更することも、ドメインを管理対象からフェデレーションに変換したり、その逆に変換したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f850e-153">Issuer URIs can be changed directly in AD FS or when a domain is converted from managed to federated and vice versa.</span></span> <span data-ttu-id="f850e-154">Microsoft では、移行される Azure AD テナント内のフェデレーションドメインを追加、削除、または変換しないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f850e-154">Microsoft recommends customers don't add, remove, or convert a federated domain in the Azure AD tenant being migrated.</span></span> <span data-ttu-id="f850e-155">発行者 Uri は、移行が完全に完了した後で変更できます。</span><span class="sxs-lookup"><span data-stu-id="f850e-155">Issuer URIs can be changed after the migration is fully complete.</span></span>

- <span data-ttu-id="f850e-156">ネットワークの場合:</span><span class="sxs-lookup"><span data-stu-id="f850e-156">For networking:</span></span>

  - <span data-ttu-id="f850e-157">IPv6 という名前のネットワークの作成は、Azure portal では機能しません `http://portal.microsoftazure.de/` 。</span><span class="sxs-lookup"><span data-stu-id="f850e-157">Creating IPv6-named networks doesn't work in the Azure portal, `http://portal.microsoftazure.de/`.</span></span> <span data-ttu-id="f850e-158">Azure portal をで使用して、 `https://portal.azure.com` IPv6 という名前のネットワークを作成します。</span><span class="sxs-lookup"><span data-stu-id="f850e-158">Use the Azure portal at `https://portal.azure.com` to create IPv6-named networks.</span></span>
 
   - <span data-ttu-id="f850e-159">Azure 多要素認証 (MFA) サービス設定の信頼された IP アドレスの範囲は、Microsoft Cloud Deut/陸ポータルから作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f850e-159">You can't create trusted IP address ranges for Azure Multi-Factor Authentication (MFA) service settings from the Microsoft Cloud Deutschland portal.</span></span> <span data-ttu-id="f850e-160">Azure AD portal for Office 365 サービスを使用して、Azure MFA の信頼できる IP アドレスの範囲を作成します。</span><span class="sxs-lookup"><span data-stu-id="f850e-160">Use the Azure AD portal for Office 365 services to create Azure MFA trusted IP address ranges.</span></span>


- <span data-ttu-id="f850e-161">条件付きアクセスの場合:</span><span class="sxs-lookup"><span data-stu-id="f850e-161">For Conditional Access:</span></span> 

  - <span data-ttu-id="f850e-162">次の付与コントロールを持つ条件付きアクセスポリシーは、Office 365 サービスへの移行が完了するまでサポートされません ( [Finalize AZURE AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration フェーズの後)。</span><span class="sxs-lookup"><span data-stu-id="f850e-162">Conditional Access policies with the following grant controls aren't supported until migration to Office 365 services is complete (after the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase):</span></span>

    - <span data-ttu-id="f850e-163">準拠デバイスが必要</span><span class="sxs-lookup"><span data-stu-id="f850e-163">Require Compliant Device</span></span>
    - <span data-ttu-id="f850e-164">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="f850e-164">Require Approved App</span></span>
    - <span data-ttu-id="f850e-165">アプリ保護ポリシーが必要</span><span class="sxs-lookup"><span data-stu-id="f850e-165">Require App Protection Policy</span></span>
    
  - <span data-ttu-id="f850e-166">条件付きアクセスポリシーインターフェイスでは、テナントに対して有効になっているセキュリティの既定については、無効になっていても、テナントに対して既に条件付きアクセスポリシーが存在することについて警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-166">The Conditional Access policy interface gives a false warning about security defaults being enabled for the tenant even when it's disabled, and Conditional Access policies already exist for the tenant.</span></span> <span data-ttu-id="f850e-167">この警告を無視するか、Office 365 services ポータルを使用して条件付きアクセスポリシーを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-167">You should ignore the warning or use the Office 365 services portal to manage Conditional Access policies.</span></span> 

- <span data-ttu-id="f850e-168">Intune シナリオは、すべての office ワークロードの移行を含む、テナントの移行が完了した後の全世界のエンドポイントに対してのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f850e-168">Intune scenarios are supported only against worldwide endpoints after tenant migration is complete, including all office workloads migrations.</span></span>

- <span data-ttu-id="f850e-169">Microsoft Cloud Deutmfa 要求に対してモバイルアプリ通知方法を使用するユーザーには、Microsoft Authenticator アプリのユーザープリンシパル名 (UPN) ではなく、ユーザーの ObjectId (GUID) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-169">Microsoft Cloud Deutschland users who use the Mobile App Notification method for MFA requests see the user's ObjectId (a GUID) instead of the user principal name (UPN) in the Microsoft Authenticator app.</span></span> <span data-ttu-id="f850e-170">Azure AD テナントの移行が完了し、Office 365 サービスでホストされると、新しい Microsoft Authenticator ライセンス認証によってユーザーの Upn が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-170">After migration of the Azure AD tenant is complete and hosted in Office 365 services, new Microsoft Authenticator activations will display users' UPNs.</span></span> <span data-ttu-id="f850e-171">既存の Microsoft Authenticator アカウントでは、引き続き user ObjectId が表示されますが、モバイルアプリの通知には引き続き機能します。</span><span class="sxs-lookup"><span data-stu-id="f850e-171">Existing Microsoft Authenticator accounts will continue to display the user ObjectId, but they'll continue to work for mobile app notifications.</span></span> 

- <span data-ttu-id="f850e-172">2019年10月22日以降に作成されたテナントの場合、セキュリティの既定値は、Office 365 サービスに移行すると、テナントに対して自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="f850e-172">For tenants that are created after October 22, 2019, security defaults may be auto-enabled for the tenant when it's migrated to the Office 365 service.</span></span> <span data-ttu-id="f850e-173">テナント管理者は、セキュリティの既定値を有効のままにして MFA を登録することも、機能を無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f850e-173">Tenant admins can choose to leave security defaults enabled and register for MFA, or they can disable the feature.</span></span> <span data-ttu-id="f850e-174">詳細については、「 [セキュリティの既定値を無効](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f850e-174">For more information, see [Disabling security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults#disabling-security-defaults).</span></span> 

  > [!NOTE]
  > <span data-ttu-id="f850e-175">移行中に自動では有効になっていない組織は、Office 365 サービスでセキュリティの既定値を有効にする機能として今後自動的に登録されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f850e-175">Organizations that are not auto-enabled during migration may still be auto-enrolled in the future as the feature to enable security defaults is rolled out in the Office 365 service.</span></span> <span data-ttu-id="f850e-176">セキュリティの既定値を明示的に無効にするか有効にするかどうかを選択する管理者は、 **Azure Active Directory > のプロパティ** で機能を更新します。</span><span class="sxs-lookup"><span data-stu-id="f850e-176">Admins who choose to explicitly disable or enable security defaults may do so by updating the feature under **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="f850e-177">この機能が管理者によって明示的に有効にされた後は、自動では有効になりません。</span><span class="sxs-lookup"><span data-stu-id="f850e-177">After the feature is explicitly enabled by the admin, it will not be auto-enabled.</span></span>

- <span data-ttu-id="f850e-178">テナントが移行されると、office 365 ドイツポータルだけでなく、office 365 ポータルにも Azure AD Connect のバージョンに関する警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-178">There will be warning about the version of Azure AD Connect in the Office 365 Germany portal as well as in the Office 365 portal once the tenant is in migration.</span></span> <span data-ttu-id="f850e-179">バージョン警告で移行が完了した後に警告が表示されなくなった場合は、この設定を無視できます。</span><span class="sxs-lookup"><span data-stu-id="f850e-179">This can be ignored if the version warning is no longer showing the warning after the migration is complete.</span></span> <span data-ttu-id="f850e-180">移行前または移行後に警告が発生した場合は、どちらのポータルでも Azure AD Connect を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-180">If there's a warning, either before or after migration, in either portal, Azure AD Connect must be updated.</span></span> <span data-ttu-id="f850e-181">"古いディレクトリ同期ツールを使用しています" という警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-181">The warning message says: "We detected you're using an outdated directory sync tool.</span></span> <span data-ttu-id="f850e-182">最新バージョンの Azure AD Connect を入手するには、Microsoft ダウンロードセンターにアクセスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f850e-182">We recommend you go to the Microsoft Download Center to get the latest version of Azure AD Connect."</span></span>

## <a name="exchange-online"></a><span data-ttu-id="f850e-183">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f850e-183">Exchange Online</span></span> 

- <span data-ttu-id="f850e-184">`myaccount.msft.com` は、Office 365 をカットオーバーした後にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f850e-184">`myaccount.msft.com` will only work after the cutover of Office 365.</span></span> <span data-ttu-id="f850e-185">リンクによって "問題が発生しました" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-185">Links will produce "something went wrong" error messages until that time.</span></span>

- <span data-ttu-id="f850e-186">他の環境の共有メールボックスにアクセスする Outlook Web App のユーザー (たとえば、ドイツ環境のユーザーがグローバル環境の共有メールボックスにアクセスする)、2回目の認証を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-186">Users of Outlook Web App that access a shared mailbox in the other environment (for example, a user in the Germany environment accesses a shared mailbox in the global environment) will be prompted to authenticate a second time.</span></span> <span data-ttu-id="f850e-187">ユーザーは、で自分のメールボックスを認証してアクセスし、 `outlook.office.de` にある共有メールボックスを開く必要があり `outlook.office365.com` ます。</span><span class="sxs-lookup"><span data-stu-id="f850e-187">The user must first authenticate and access their mailbox in `outlook.office.de`, then open the shared mailbox that is in `outlook.office365.com`.</span></span> <span data-ttu-id="f850e-188">他のサービスでホストされている共有リソースにアクセスするときは、2回目の認証が必要になります。</span><span class="sxs-lookup"><span data-stu-id="f850e-188">They'll need to authenticate a second time when accessing the shared resources that are hosted in the other service.</span></span>

- <span data-ttu-id="f850e-189">既存の Microsoft Cloud Deut上陸お客様、または移行されたメールボックスの場合、[ファイル >] [Info] を使用して Outlook に共有メールボックスを追加すると **> アカウントの追加** は失敗する可能性があります (outlook クライアントが Rest API を使用しようとして `https://outlook.office.de/api/v2.0/Me/Calendars` います)。予定表のアクセス許可を表示するためのアカウントを追加する場合は、「 [Outlook で予定表を共有するためのユーザー操作の変更](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) 」で説明されているようにレジストリキーを追加して、この操作が正常に行われるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f850e-189">For existing Microsoft Cloud Deutschland customers or those in transition, when a shared mailbox is added to Outlook by using **File > Info > Add Account**, viewing calendar permissions may fail (the Outlook client attempts to use the Rest API `https://outlook.office.de/api/v2.0/Me/Calendars`.) Customers who want to add an account to view calendar permissions can add the registry key as described in [User experience changes for sharing a calendar in Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) to ensure this action will succeed.</span></span> <span data-ttu-id="f850e-190">このレジストリキーは、グループポリシーを使用して組織全体に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f850e-190">This registry key can be deployed organization-wide by using Group Policy.</span></span>

- <span data-ttu-id="f850e-191">移行フェーズでは、PowerShell コマンドレット **new-migrationendpoint**、 **New-migrationendpoint**、および **MigrationsServerAvailability** を使用すると、エラーが発生する場合があります (プロキシでのエラー)。</span><span class="sxs-lookup"><span data-stu-id="f850e-191">During the migration phase, using the PowerShell cmdlets **New-migrationEndpoint**, **Set-MigrationEndpoint**, and **Test-MigrationsServerAvailability** can result in errors (error on proxy).</span></span> <span data-ttu-id="f850e-192">これは、調停メールボックスが世界中に移行されたが、管理メールボックスが存在しないか逆の場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f850e-192">This happens when the arbitration mailbox has migrated to worldwide but the admin mailbox hasn't or vice-versa.</span></span> <span data-ttu-id="f850e-193">このエラーを解決するには、テナントの PowerShell セッションを作成している間に、 **Connectionuri** のルーティングヒントとして調停メールボックスを使用します。</span><span class="sxs-lookup"><span data-stu-id="f850e-193">To resolve this, while creating the tenant PowerShell session, use the arbitration mailbox as the routing hint in the **ConnectionUri**.</span></span> <span data-ttu-id="f850e-194">例: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span><span class="sxs-lookup"><span data-stu-id="f850e-194">For example: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`</span></span>

- <span data-ttu-id="f850e-195">Exchange Online ハイブリッドを使用している場合:</span><span class="sxs-lookup"><span data-stu-id="f850e-195">If you're using Exchange Online hybrid:</span></span>

    - <span data-ttu-id="f850e-196">ハイブリッド構成ウィザード (HCW) を再実行して、移行の前に Microsoft Cloud Deut上陸陸に対してオンプレミスの構成を更新し、Office 365 サービスに対してクリーンアップ時に HCW を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-196">You must rerun the Hybrid Configuration wizard (HCW) to update on-premises configuration against Microsoft Cloud Deutschland before the transition, and rerun the HCW upon cleanup against the Office 365 services.</span></span> <span data-ttu-id="f850e-197">カスタムドメインを使用する場合は、追加の DNS 更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="f850e-197">Additional DNS updates may be required if you use custom domains.</span></span>

<span data-ttu-id="f850e-198">このワークロードの移行フェーズ中に必要な操作、または管理または使用に対する影響の詳細については、「 [移行フェーズの操作と影響](ms-cloud-germany-transition-phases.md#exchange-online)」の「Exchange Online」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f850e-198">For more information about actions that are required during the migration phase of this workload or about the impact to administration or usage, review the Exchange Online section of [Migration phases actions and impacts](ms-cloud-germany-transition-phases.md#exchange-online).</span></span>

## <a name="office-services"></a><span data-ttu-id="f850e-199">Office サービス</span><span class="sxs-lookup"><span data-stu-id="f850e-199">Office Services</span></span>

<span data-ttu-id="f850e-200">Office の最近使用した (MRU) サービスは、ドイツサービスから Office 365 サービスへのカットオーバーであり、移行ではありません。</span><span class="sxs-lookup"><span data-stu-id="f850e-200">The most recently used (MRU) service in Office is a cutover from the Germany service to Office 365 services, not a migration.</span></span> <span data-ttu-id="f850e-201">Office.com ポータルから移行した後は、Office 365 services 側の MRU リンクのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-201">Only MRU links from the Office 365 services side will be visible after migration from the Office.com portal.</span></span> <span data-ttu-id="f850e-202">ドイツのサービスからの MRU リンクは、Office 365 サービスで MRU リンクとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="f850e-202">MRU links from the Germany service aren't visible as MRU links in Office 365 services.</span></span> <span data-ttu-id="f850e-203">Office 365 では、MRU リンクは、テナントの移行が完了した後にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f850e-203">In Office 365, MRU links are accessible only after the tenant migration is complete.</span></span>

## <a name="sharepoint-online-and-onedrive"></a><span data-ttu-id="f850e-204">SharePoint Online と OneDrive</span><span class="sxs-lookup"><span data-stu-id="f850e-204">SharePoint Online and OneDrive</span></span>

- <span data-ttu-id="f850e-205">ドイツ リージョンへの SharePoint Online の移行が完了すると、データ インデックスが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-205">Upon completion of the SharePoint Online migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="f850e-206">インデックスの再作成が完了している間は、検索インデックスに依存する機能が影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-206">Features that are dependent on search indexes may be affected while reindexing completes.</span></span>

- <span data-ttu-id="f850e-207">組織が SharePoint 2010 ワークフローを引き続き使用している場合は、2021年12月31日以降、機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="f850e-207">If your organization still uses SharePoint 2010 workflows, they'll no longer function after December 31, 2021.</span></span> <span data-ttu-id="f850e-208">SharePoint 2013 のワークフローは引き続きサポートされますが、既定では、2020年11月1日から始まる新しいテナントに対して無効になっています。</span><span class="sxs-lookup"><span data-stu-id="f850e-208">SharePoint 2013 workflows will remain supported, although turned off by default for new tenants starting on November 1, 2020.</span></span> <span data-ttu-id="f850e-209">SharePoint Online サービスへの移行が完了したら、パワー自動化または他のサポートされているソリューションに移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f850e-209">After migration to the SharePoint Online service is complete, we recommend that you to move to Power Automate or other supported solutions.</span></span>

- <span data-ttu-id="f850e-210">ドイツ地域への OneDrive の移行が完了したら、データインデックスが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="f850e-210">Upon completion of the OneDrive migration to the German region, data indexes are rebuilt.</span></span> <span data-ttu-id="f850e-211">インデックスの再作成が進行中の場合、検索インデックスに依存する機能が影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f850e-211">Features that depend on search indexes may be affected while reindexing is in progress.</span></span>


## <a name="more-information"></a><span data-ttu-id="f850e-212">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f850e-212">More information</span></span>

<span data-ttu-id="f850e-213">はじめに:</span><span class="sxs-lookup"><span data-stu-id="f850e-213">Getting started:</span></span>

- [<span data-ttu-id="f850e-214">新しいドイツ語のデータセンターリージョンの Microsoft Cloud Deutランドから Office 365 サービスへの移行</span><span class="sxs-lookup"><span data-stu-id="f850e-214">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="f850e-215">Microsoft Cloud Deutschland 移行アシスタント</span><span class="sxs-lookup"><span data-stu-id="f850e-215">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="f850e-216">移行のオプトイン方法</span><span class="sxs-lookup"><span data-stu-id="f850e-216">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="f850e-217">移行中の顧客の利便性</span><span class="sxs-lookup"><span data-stu-id="f850e-217">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="f850e-218">遷移を移動します。</span><span class="sxs-lookup"><span data-stu-id="f850e-218">Moving through the transition:</span></span>

- [<span data-ttu-id="f850e-219">移行フェーズのアクションと影響</span><span class="sxs-lookup"><span data-stu-id="f850e-219">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="f850e-220">その他の準備作業</span><span class="sxs-lookup"><span data-stu-id="f850e-220">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="f850e-221">[サービス](ms-cloud-germany-transition-add-general.md)、[デバイス](ms-cloud-germany-transition-add-devices.md)、[エクスペリエンス](ms-cloud-germany-transition-add-experience.md)、 [AD FS](ms-cloud-germany-transition-add-adfs.md)の追加情報。</span><span class="sxs-lookup"><span data-stu-id="f850e-221">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="f850e-222">クラウドアプリ:</span><span class="sxs-lookup"><span data-stu-id="f850e-222">Cloud apps:</span></span>

- [<span data-ttu-id="f850e-223">Dynamics 365 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="f850e-223">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="f850e-224">Power BI 移行プログラム情報</span><span class="sxs-lookup"><span data-stu-id="f850e-224">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="f850e-225">Microsoft Teams へのアップグレードを開始する</span><span class="sxs-lookup"><span data-stu-id="f850e-225">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)