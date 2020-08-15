---
title: Microsoft 365 のセッションタイムアウト
ms.author: tracyp
author: MSFTTracyP
manager: scotv
ms.date: 6/29/2018
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
ms.assetid: 37a5c116-5b07-4f70-8333-5b86fd2c3c40
ms.collection:
- M365-security-compliance
description: セッションタイムアウトを使用して、Microsoft 365 クライアントアプリでのセキュリティと容易なアクセスのバランスを取る方法を説明します。
ms.openlocfilehash: 8fbbb526fe4b0ac136f79acd564b268489841e0b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691681"
---
# <a name="session-timeouts-for-microsoft-365"></a><span data-ttu-id="4d931-103">Microsoft 365 のセッションタイムアウト</span><span class="sxs-lookup"><span data-stu-id="4d931-103">Session timeouts for Microsoft 365</span></span>

<span data-ttu-id="4d931-104">セッションの有効期限は、Microsoft 365 の認証の重要な部分であり、セキュリティのバランスの重要なコンポーネントであり、ユーザーが資格情報の入力を求められる回数です。</span><span class="sxs-lookup"><span data-stu-id="4d931-104">Session lifetimes are an important part of authentication for Microsoft 365 and are an important component in balancing security and the number of times users are prompted for their credentials.</span></span>
  
## <a name="session-times-for-microsoft-365-services"></a><span data-ttu-id="4d931-105">Microsoft 365 サービスのセッション時間</span><span class="sxs-lookup"><span data-stu-id="4d931-105">Session times for Microsoft 365 services</span></span>

<span data-ttu-id="4d931-106">ユーザーが Microsoft 365 web アプリまたはモバイルアプリのいずれかで認証を行うと、セッションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="4d931-106">When users authenticate in any of the Microsoft 365 web apps or mobile apps, a session is established.</span></span> <span data-ttu-id="4d931-107">セッションの期間中は、ユーザーを再認証する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4d931-107">For the duration of the session, users won't need to re-authenticate.</span></span> <span data-ttu-id="4d931-108">ユーザーがアクティブでないとき、ブラウザーまたはタブを閉じるとき、またはパスワードがリセットされたなどの理由で認証トークンの有効期限が切れたときに、セッションが期限切れになることがあります。</span><span class="sxs-lookup"><span data-stu-id="4d931-108">Sessions can expire when users are inactive, when they close the browser or tab, or when their authentication token expires for other reasons such as when their password has been reset.</span></span> <span data-ttu-id="4d931-109">Microsoft 365 サービスでは、各サービスの一般的な使用に対応するセッションタイムアウトが異なります。</span><span class="sxs-lookup"><span data-stu-id="4d931-109">The Microsoft 365 services have different session timeouts to correspond with the typical use of each service.</span></span>
  
<span data-ttu-id="4d931-110">次の表に、Microsoft 365 サービスのセッション有効期間を示します。</span><span class="sxs-lookup"><span data-stu-id="4d931-110">The following table lists the session lifetimes for Microsoft 365 services:</span></span>
  
|<span data-ttu-id="4d931-111">**Microsoft 365 サービス**</span><span class="sxs-lookup"><span data-stu-id="4d931-111">**Microsoft 365 service**</span></span>|<span data-ttu-id="4d931-112">**セッションのタイムアウト**</span><span class="sxs-lookup"><span data-stu-id="4d931-112">**Session timeout**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d931-113">Microsoft 365 管理センター</span><span class="sxs-lookup"><span data-stu-id="4d931-113">Microsoft 365 admin center</span></span>  <br/> |<span data-ttu-id="4d931-114">管理センターの資格情報を8時間ごとに提供するように求められます。</span><span class="sxs-lookup"><span data-stu-id="4d931-114">You are asked to provide credentials for the admin center every 8 hours.</span></span>  <br/> |
|<span data-ttu-id="4d931-115">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4d931-115">SharePoint Online</span></span>  <br/> |<span data-ttu-id="4d931-116">ユーザーが **[サインイン状態を保持**] を選択した場合に限り、5日間非アクティブです。</span><span class="sxs-lookup"><span data-stu-id="4d931-116">5 days of inactivity as long as the users chooses **Keep me signed in**.</span></span> <span data-ttu-id="4d931-117">以前のサインインから24時間以上経過した後に SharePoint Online にアクセスすると、タイムアウト値は5日にリセットされます。</span><span class="sxs-lookup"><span data-stu-id="4d931-117">If the user accesses SharePoint Online again after 24 or more hours have passed from the previous sign-in, the timeout value is reset to 5 days.</span></span>  <br/> |
|<span data-ttu-id="4d931-118">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="4d931-118">Outlook Web App</span></span>  <br/> |<span data-ttu-id="4d931-119">6時間。</span><span class="sxs-lookup"><span data-stu-id="4d931-119">6 hours.</span></span>  <br/> <span data-ttu-id="4d931-120">この値を変更するに[は、このコマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=615378)の_Activityの authenticationtimeoutinterval_パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="4d931-120">You can change this value by using the  _ActivityBasedAuthenticationTimeoutInterval_ parameter in the [Set-OrganizationConfig](https://go.microsoft.com/fwlink/p/?LinkId=615378) cmdlet.</span></span>  <br/> |
|<span data-ttu-id="4d931-121">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4d931-121">Azure Active Directory</span></span>  <br/> <span data-ttu-id="4d931-122">(モダン認証が有効になっている Office 2013 Windows クライアントによって使用されます)</span><span class="sxs-lookup"><span data-stu-id="4d931-122">(Used by Office 2013 Windows clients with modern authentication enabled)</span></span>  <br/> | <span data-ttu-id="4d931-123">モダン認証は、アクセストークンと更新トークンを使用して、Azure Active Directory を使用して Microsoft 365 リソースへのユーザーアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="4d931-123">Modern authentication uses access tokens and refresh tokens to grant user access to Microsoft 365 resources using Azure Active Directory.</span></span> <span data-ttu-id="4d931-124">アクセストークンは、認証が成功した後に提供される JSON Web トークンで、1時間有効です。</span><span class="sxs-lookup"><span data-stu-id="4d931-124">An access token is a JSON Web Token provided after a successful authentication and is valid for 1 hour.</span></span> <span data-ttu-id="4d931-125">有効期間の長い更新トークンも提供されます。</span><span class="sxs-lookup"><span data-stu-id="4d931-125">A refresh token with a longer lifetime is also provided.</span></span> <span data-ttu-id="4d931-126">アクセストークンが期限切れになると、Office クライアントは有効な更新トークンを使用して新しいアクセストークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4d931-126">When access tokens expire, Office clients use a valid refresh token to obtain a new access token.</span></span> <span data-ttu-id="4d931-127">この exchange は、ユーザーの初期認証がまだ有効である場合に成功します。</span><span class="sxs-lookup"><span data-stu-id="4d931-127">This exchange succeeds if the user's initial authentication is still valid.</span></span>  <br/>  <span data-ttu-id="4d931-128">更新トークンは90日に有効であり、継続的に使用することで、失効するまで有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d931-128">Refresh tokens are valid for 90 days, and with continuous use, they can be valid until revoked.</span></span>  <br/>  <span data-ttu-id="4d931-129">更新トークンは、次のようないくつかのイベントによって無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d931-129">Refresh tokens can be invalidated by several events such as :</span></span>  <br/>  <span data-ttu-id="4d931-130">更新トークンが発行されてから、ユーザーのパスワードが変更されました。</span><span class="sxs-lookup"><span data-stu-id="4d931-130">User's password has changed since the refresh token was issued.</span></span>  <br/>  <span data-ttu-id="4d931-131">管理者は、ユーザーがアクセスしようとしているリソースへのアクセスを制限する条件付きアクセスポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="4d931-131">An administrator can apply conditional access policies which restrict access to the resource the user is trying to access.</span></span>  <br/> |
|<span data-ttu-id="4d931-132">Android、iOS、Windows 10 用の SharePoint および OneDrive モバイルアプリ</span><span class="sxs-lookup"><span data-stu-id="4d931-132">SharePoint and OneDrive mobile apps for Android, iOS, and Windows 10</span></span>  <br/> |<span data-ttu-id="4d931-133">アクセストークンの既定の有効期間は1時間です。</span><span class="sxs-lookup"><span data-stu-id="4d931-133">The default lifetime for the access token is 1 hour.</span></span> <span data-ttu-id="4d931-134">更新トークンの既定の最大非アクティブ時間は90日です。</span><span class="sxs-lookup"><span data-stu-id="4d931-134">The default max inactive time of the refresh token is 90 days.</span></span>  <br/> [<span data-ttu-id="4d931-135">トークンの詳細とトークンの有効期間を構成する方法について</span><span class="sxs-lookup"><span data-stu-id="4d931-135">Learn more about tokens and how to configure token lifetimes</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes) <br/> <span data-ttu-id="4d931-136">更新トークンを取り消すには、ユーザーの Microsoft 365 パスワードをリセットします。</span><span class="sxs-lookup"><span data-stu-id="4d931-136">To revoke the refresh token, you can reset the user's Microsoft 365 password</span></span>  <br/> |
|<span data-ttu-id="4d931-137">Microsoft 365 サインインを使用した Yammer</span><span class="sxs-lookup"><span data-stu-id="4d931-137">Yammer with Microsoft 365 Sign-In</span></span>  <br/> |<span data-ttu-id="4d931-138">ブラウザーの有効期間。</span><span class="sxs-lookup"><span data-stu-id="4d931-138">Lifetime of the browser.</span></span> <span data-ttu-id="4d931-139">ユーザーが新しいブラウザーでブラウザーを閉じて Yammer にアクセスすると、Yammer は Microsoft 365 を使用して再認証します。</span><span class="sxs-lookup"><span data-stu-id="4d931-139">If users close the browser and access Yammer in a new browser, Yammer will re-authenticate them with Microsoft 365.</span></span> <span data-ttu-id="4d931-140">ユーザーが cookie をキャッシュするサードパーティ製ブラウザーを使用している場合は、ブラウザーを再度開いたときに再認証する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4d931-140">If users use third-party browsers that cache cookies, they may not need to re-authenticate when they reopen the browser.</span></span>  <br/> <span data-ttu-id="4d931-141">> [!NOTE]> Yammer の Microsoft 365 サインインを使用しているネットワークに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="4d931-141">> [!NOTE]> This is valid only for networks using Microsoft 365 Sign-In for Yammer.</span></span>           |
   
