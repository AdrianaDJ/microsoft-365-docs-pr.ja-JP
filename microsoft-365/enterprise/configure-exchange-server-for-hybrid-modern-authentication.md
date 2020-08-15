---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッド先進認証 (HMA) を使用するように Exchange Server をオンプレミスで構成する方法について説明し、ユーザーの認証と承認をセキュリティで保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 291c7c220fb4ee56db2a42409d5b81724de5da32
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691585"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="765a3-103">Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには</span><span class="sxs-lookup"><span data-stu-id="765a3-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="765a3-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="765a3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="765a3-105">ハイブリッド先進認証 (HMA) は、よりセキュリティで保護されたユーザー認証と承認を提供する id 管理の方法で、Exchange server のオンプレミスハイブリッド展開で使用できます。</span><span class="sxs-lookup"><span data-stu-id="765a3-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>
  
## <a name="fyi"></a><span data-ttu-id="765a3-106">注意</span><span class="sxs-lookup"><span data-stu-id="765a3-106">FYI</span></span>

<span data-ttu-id="765a3-107">開始する前に、次のように呼び出します。</span><span class="sxs-lookup"><span data-stu-id="765a3-107">Before we begin, I call:</span></span>
  
- <span data-ttu-id="765a3-108">ハイブリッド先進認証の \> HMA</span><span class="sxs-lookup"><span data-stu-id="765a3-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="765a3-109">Exchange オンプレミスの \> EXCH</span><span class="sxs-lookup"><span data-stu-id="765a3-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="765a3-110">Exchange Online \> exo</span><span class="sxs-lookup"><span data-stu-id="765a3-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="765a3-111">また、 *この記事のグラフィックに ' グレイアウト ' または ' 淡色 ' のオブジェクトが含まれている場合、灰色の要素が HMA 固有の構成に含まれていない* ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="765a3-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration* .</span></span>
  
## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="765a3-112">ハイブリッド先進認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="765a3-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="765a3-113">HMA を有効にするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="765a3-113">Turning HMA on means:</span></span>
  
1. <span data-ttu-id="765a3-114">開始する前に、前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="765a3-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="765a3-115">多くの **前提条件** は、Skype for Business と exchange の両方に共通であるため、 [ハイブリッド先進認証の概要と、オンプレミスの Skype For business および exchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)です。</span><span class="sxs-lookup"><span data-stu-id="765a3-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="765a3-116">この手順を実行する前に、この記事の手順を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="765a3-117">Azure AD の **サービスプリンシパル名 (spn)** として、オンプレミスの Web サービス url を追加します。</span><span class="sxs-lookup"><span data-stu-id="765a3-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="765a3-118">すべての仮想ディレクトリで HMA が有効になっていることを確認する</span><span class="sxs-lookup"><span data-stu-id="765a3-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="765a3-119">EvoSTS 認証サーバーオブジェクトの確認</span><span class="sxs-lookup"><span data-stu-id="765a3-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="765a3-120">EXCH で HMA を有効にします。</span><span class="sxs-lookup"><span data-stu-id="765a3-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="765a3-121">**メモ** お使いのバージョンの Office は MA をサポートしていますか?</span><span class="sxs-lookup"><span data-stu-id="765a3-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="765a3-122">「 [Office 2013 および office 2016 クライアントアプリでの先進認証のしくみ」を](modern-auth-for-office-2013-and-2016.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="765a3-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>
  
## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="765a3-123">すべての前提条件を満たしていることを確認する</span><span class="sxs-lookup"><span data-stu-id="765a3-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="765a3-124">Skype for Business と Exchange の両方に共通の前提条件が多数存在するため、 [ハイブリッド先進認証の概要と、オンプレミスの Skype For business および exchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="765a3-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="765a3-125">この手順を実行する  *前*  に、この記事の手順を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-125">Do this  *before*  you begin any of the steps in this article.</span></span>
  
## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="765a3-126">オンプレミスの web サービス Url を Spn として Azure AD に追加する</span><span class="sxs-lookup"><span data-stu-id="765a3-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="765a3-127">オンプレミスの web サービス Url を Azure AD Spn として割り当てるコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="765a3-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="765a3-128">Spn は、認証と承認の際にクライアントコンピューターとデバイスによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="765a3-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="765a3-129">オンプレミスから Azure Active Directory (Azure AD) への接続に使用される可能性があるすべての Url は、Azure AD に登録する必要があります (内部と外部の両方の名前空間が含まれます)。</span><span class="sxs-lookup"><span data-stu-id="765a3-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>
  
<span data-ttu-id="765a3-130">最初に、AAD で追加する必要があるすべての Url を収集します。</span><span class="sxs-lookup"><span data-stu-id="765a3-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="765a3-131">オンプレミスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="765a3-131">Run these commands on-premises:</span></span>
  
```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```
    
<span data-ttu-id="765a3-132">AAD でクライアントが接続できる Url が HTTPS サービスプリンシパル名としてリストされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="765a3-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>
  
1. <span data-ttu-id="765a3-133">最初に、 [次の手順に従っ](connect-to-microsoft-365-powershell.md)て AAD に接続します。</span><span class="sxs-lookup"><span data-stu-id="765a3-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

 <span data-ttu-id="765a3-134">**メモ** このページの _connect-msolservice_ オプションを使用して、以下のコマンドを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="765a3-135">Exchange 関連の Url の場合は、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="765a3-135">For your Exchange related URLs, type the following command:</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
```

<span data-ttu-id="765a3-136">このコマンドの出力をメモします。このコマンドには、https://  *autodiscover.yourdomain.com*  および Https://  *mail.yourdomain.com* URL が含まれていますが、ほとんどの場合は、00000002-0000-0ff1-ce00-000000000000/から始まる spn から構成されます。</span><span class="sxs-lookup"><span data-stu-id="765a3-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="765a3-137">オンプレミスの https://Url が不足している場合は、それらのレコードをこのリストに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-137">If there are https:// URLs from your on-premises that are missing we will need to add those specific records to this list.</span></span>
  
3. <span data-ttu-id="765a3-138">内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出のレコードがこの一覧に表示されない場合は、次のコマンドを使用して追加する必要があります (Url の例は ' `mail.corp.contoso.com` ' と ' ' ですが、この `owa.contoso.com` **例の url は独自のものに置き換え** ます)。</span><span class="sxs-lookup"><span data-stu-id="765a3-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own** ):</span></span> <br/>
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
$x.ServicePrincipalnames.Add("https://owa.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="765a3-139">手順2で New-msolserviceprincipal コマンドを再度実行し、出力を調べて、新しいレコードが追加されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="765a3-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="765a3-140">リスト/スクリーンショットを以前から新しい Spn のリストに比較します (レコードの新しいリストのスクリーンショットを表示することもできます)。</span><span class="sxs-lookup"><span data-stu-id="765a3-140">Compare the list / screenshot from before to the new list of SPNs (you may also screenshot the new list for your records).</span></span> <span data-ttu-id="765a3-141">成功した場合は、2つの新しい Url が一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="765a3-141">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="765a3-142">この例では、Spn の一覧に特定の Url とが含まれるようになりました  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="765a3-142">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span> 
  
## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="765a3-143">仮想ディレクトリが正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="765a3-143">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="765a3-144">これで、次のコマンドを実行することによって、Outlook が使用するすべての仮想ディレクトリで OAuth が適切に有効になっていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="765a3-144">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth* 
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="765a3-145">出力をチェックして、これらの各 VDirs で **OAuth** が有効になっていることを確認してください。次のようになります (そして、ここで重要な点は ' OAuth ' です)。</span><span class="sxs-lookup"><span data-stu-id="765a3-145">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```
  
<span data-ttu-id="765a3-146">OAuth がサーバーと4つの仮想ディレクトリのいずれにも存在しない場合は、先に進む前に関連するコマンドを使用して追加する必要があります ([MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps)、 [set-webservicesvirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps)、 [set-oabvirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps)、および [new-autodiscovervirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps))。</span><span class="sxs-lookup"><span data-stu-id="765a3-146">If OAuth is missing from any server and any of the four virtual directories then you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-mapivirtualdirectory?view=exchange-ps), [Set-WebServicesVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-webservicesvirtualdirectory?view=exchange-ps), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/set-oabvirtualdirectory?view=exchange-ps), and [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/client-access-servers/set-autodiscovervirtualdirectory?view=exchange-ps)).</span></span>
  
## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="765a3-147">EvoSTS Auth サーバーオブジェクトが存在することを確認する</span><span class="sxs-lookup"><span data-stu-id="765a3-147">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="765a3-148">この最後のコマンドについては、オンプレミスの Exchange 管理シェルに戻ります。</span><span class="sxs-lookup"><span data-stu-id="765a3-148">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="765a3-149">これで、オンプレミスに evoSTS 認証プロバイダのエントリがあることを検証できます。</span><span class="sxs-lookup"><span data-stu-id="765a3-149">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>
  
```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="765a3-150">出力には、EvoSts という名前の AuthServer が表示され、' Enabled ' 状態が True である必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-150">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="765a3-151">これが表示されない場合は、ハイブリッド構成ウィザードの最新バージョンをダウンロードして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="765a3-151">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>
  
 <span data-ttu-id="765a3-152">**重要** ご使用の環境で Exchange 2010 を実行している場合は、EvoSTS 認証プロバイダーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="765a3-152">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span> 
  
## <a name="enable-hma"></a><span data-ttu-id="765a3-153">HMA を有効にする</span><span class="sxs-lookup"><span data-stu-id="765a3-153">Enable HMA</span></span>

<span data-ttu-id="765a3-154">Exchange 管理シェルで、オンプレミスの次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="765a3-154">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true  
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="765a3-155">ことを確認</span><span class="sxs-lookup"><span data-stu-id="765a3-155">Verify</span></span>

<span data-ttu-id="765a3-156">HMA を有効にすると、クライアントの次のログインは新しい認証フローを使用します。</span><span class="sxs-lookup"><span data-stu-id="765a3-156">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="765a3-157">HMA を有効にしても、クライアントに対しては再認証はトリガーされませんので注意してください。</span><span class="sxs-lookup"><span data-stu-id="765a3-157">Note that just turning on HMA won't trigger a re-authentication for any client.</span></span> <span data-ttu-id="765a3-158">クライアントは、認証トークンまたは証明書の有効期間に基づいて再認証を行います。</span><span class="sxs-lookup"><span data-stu-id="765a3-158">The clients re-authenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>
  
<span data-ttu-id="765a3-159">また、CTRL キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイにもあります) を右クリックし、[接続の状態] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="765a3-159">You should also hold down the CTRL key at the same time you right click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="765a3-160">OAuth で使用されるベアラートークンを表す ' 認証 ' の種類 ' ベアラー ' に対してクライアントの SMTP アドレスを検索し \* ます。</span><span class="sxs-lookup"><span data-stu-id="765a3-160">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>
  
 <span data-ttu-id="765a3-161">**メモ** HMA を使用して Skype for Business を構成する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="765a3-161">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="765a3-162">[サポートされているトポロジ](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)の一覧と、[構成方法](configure-skype-for-business-for-hybrid-modern-authentication.md)を示す2つの記事が必要になります。</span><span class="sxs-lookup"><span data-stu-id="765a3-162">You'll need two articles: One that lists [supported topologies](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>
 
## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="765a3-163">iOS および Android 用の Outlook でのハイブリッド先進認証の使用</span><span class="sxs-lookup"><span data-stu-id="765a3-163">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="765a3-164">TCP 443 で Exchange server を使用しているオンプレミスのお客様の場合は、次の IP 範囲をホワイトリストしてください。  </span><span class="sxs-lookup"><span data-stu-id="765a3-164">If you are an on-premises customer using Exchange server on TCP 443, please whitelist the following IP ranges:  </span></span><BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR>

## <a name="related-topics"></a><span data-ttu-id="765a3-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="765a3-165">Related topics</span></span>

[<span data-ttu-id="765a3-166">Office 365 専任/ITAR から vNext に移行するための先進認証構成要件</span><span class="sxs-lookup"><span data-stu-id="765a3-166">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)