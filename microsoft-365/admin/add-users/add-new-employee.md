---
title: Office 365 に新しい従業員を追加する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
- MET150
- MOE150
ms.assetid: 9cdfa29d-7681-4af2-a79d-3e72e7ab9778
description: 電子メール、Skype、Office アプリ用に Office 365 for business に新しい従業員を追加します。
ms.openlocfilehash: d77c62898fc238b3c321e61b6a867092442baa07
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241691"
---
# <a name="add-a-new-employee-to-office-365"></a><span data-ttu-id="137b7-103">Office 365 に新しい従業員を追加する</span><span class="sxs-lookup"><span data-stu-id="137b7-103">Add a new employee to Office 365</span></span>

<span data-ttu-id="137b7-104">この記事は、新しい従業員を Office 365 for business にオンボードするために役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="137b7-104">This article helps you onboard a new employee to Office 365 for business.</span></span> <span data-ttu-id="137b7-105">管理者として、既に[Office 365 のセットアップを完了](../setup/setup.md)していることを前提としています。これで、新しいユーザーが会社に参加することができました。</span><span class="sxs-lookup"><span data-stu-id="137b7-105">We assume you're an Admin and you've already [completed Office 365 set up](../setup/setup.md), and now you have someone new joining your company.</span></span>
  
<span data-ttu-id="137b7-106">新しい従業員が Office 365 を必要としていて、Word や Excel などの office アプリをコンピューターにインストールできる[office 365 プラン](https://products.office.com/business/compare-office-365-for-business-plans)を使用している場合は、適切な場所にいます。</span><span class="sxs-lookup"><span data-stu-id="137b7-106">You're in the right place if your new employee needs Office 365, and you're using an [Office 365 plan](https://products.office.com/business/compare-office-365-for-business-plans) that lets you install Office apps like Word and Excel on a computer.</span></span> 
  
 <span data-ttu-id="137b7-107">**管理者ではない場合**:</span><span class="sxs-lookup"><span data-stu-id="137b7-107">**Not an admin?**</span></span> <span data-ttu-id="137b7-108">[Office 365 の方法について説明](https://support.office.com/article/9b7306d3-8d61-4794-bb6f-6520f65956d9.aspx)します。 office 365 を使用した企業およびホームユーザーの設定をサポートします。</span><span class="sxs-lookup"><span data-stu-id="137b7-108">[Learn your way around Office 365](https://support.office.com/article/9b7306d3-8d61-4794-bb6f-6520f65956d9.aspx) helps business and home users with Office 365 set up.</span></span> 
  
 <span data-ttu-id="137b7-109">**プランに Office アプリはありませんか?**</span><span class="sxs-lookup"><span data-stu-id="137b7-109">**No Office apps in your plan?**</span></span> <span data-ttu-id="137b7-110">次の手順に従います。ただし、「アプリのインストール」のセクションは省略してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-110">Follow the steps below, but skip the sections for installing apps.</span></span> <span data-ttu-id="137b7-111">代わりに、 [Office のオンラインバージョン](https://support.office.com/article/91a4ec74-67fe-4a84-a268-f6bdf3da1804.aspx)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-111">Use the [Online versions of Office](https://support.office.com/article/91a4ec74-67fe-4a84-a268-f6bdf3da1804.aspx) instead.</span></span> 
  
<span data-ttu-id="137b7-112">簡単な概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="137b7-112">Here's a quick overview:</span></span> 
  
|<span data-ttu-id="137b7-113">**手順**</span><span class="sxs-lookup"><span data-stu-id="137b7-113">**Step**</span></span>|<span data-ttu-id="137b7-114">**理由**</span><span class="sxs-lookup"><span data-stu-id="137b7-114">**Why do this?**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="137b7-115">手順 1: 従業員の Office 365 アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="137b7-115">Step 1: Create an Office 365 account for the employee</span></span>](#step-1-create-an-office-365-account-for-the-employee) <br/> |<span data-ttu-id="137b7-116">新しい従業員が勤務先を参加させるたびに、Office 365 の使用を開始できるようにアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="137b7-116">Each time a new employee joins your business, create an account for them so they can start using Office 365.</span></span>  <br/> |
|[<span data-ttu-id="137b7-117">手順 2: 従業員にユーザー ID とパスワードを付与する</span><span class="sxs-lookup"><span data-stu-id="137b7-117">Step 2: Give the employee their user ID and password</span></span>](#step-2-give-the-employee-their-user-id-and-password) <br/> |<span data-ttu-id="137b7-118">アカウントを作成すると、ユーザーがサインインできるように、ID とパスワードが表示され、従業員に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="137b7-118">When you create an account, you'll get an ID and password that you can pass to your employee so they can sign in.</span></span>  <br/> |
|[<span data-ttu-id="137b7-119">手順 3: サインインする場所を説明する</span><span class="sxs-lookup"><span data-stu-id="137b7-119">Step 3: Explain where to sign in</span></span>](#step-3-explain-where-to-sign-in) <br/> |<span data-ttu-id="137b7-120">サインインの場所は[https://www.office.com](https://www.office.com)</span><span class="sxs-lookup"><span data-stu-id="137b7-120">The sign in location is [https://www.office.com](https://www.office.com)</span></span> <br/> |
|[<span data-ttu-id="137b7-121">手順 4: 従業員の作業の開始を支援する</span><span class="sxs-lookup"><span data-stu-id="137b7-121">Step 4: Help your employee get started</span></span>](#step-4-help-your-employee-get-started) <br/> |<span data-ttu-id="137b7-122">従業員に、組織内の OneDrive または任意のチームサイトの使用方法を知らせます。</span><span class="sxs-lookup"><span data-stu-id="137b7-122">Let your employee know how to use OneDrive or any team sites in your organization.</span></span>  <br/> |
   
## <a name="step-1-create-an-office-365-account-for-the-employee"></a><span data-ttu-id="137b7-123">手順 1: 従業員の Office 365 アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="137b7-123">Step 1: Create an Office 365 account for the employee</span></span>


<span data-ttu-id="137b7-124">手順について[は、「ユーザーを個別に追加する」または「一括で Office 365-管理者向けヘルプ」を](add-users.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-124">For instructions, see [Add users individually or in bulk to Office 365 - Admin Help](add-users.md).</span></span> <span data-ttu-id="137b7-125">新しい従業員を設定するときは、従業員の個人アカウントにログインの詳細を送信することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="137b7-125">When you set up your new employee, you can choose to send log-in details to the employee's personal account.</span></span> <span data-ttu-id="137b7-126">このようにすると、Microsoft Online Service チームから、Office 365 へのログイン方法を知らせる電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="137b7-126">This way, they'll receive an email from Microsoft Online Service Team that tells them how to log in to Office 365.</span></span>
  
## <a name="step-2-give-the-employee-their-user-id-and-password"></a><span data-ttu-id="137b7-127">手順 2: 従業員にユーザー ID とパスワードを付与する</span><span class="sxs-lookup"><span data-stu-id="137b7-127">Step 2: Give the employee their user ID and password</span></span>


<span data-ttu-id="137b7-128">個人の電子メールアドレスに送信していない場合は、従業員の Office 365 サインイン名とパスワードを印刷して、それに渡します。</span><span class="sxs-lookup"><span data-stu-id="137b7-128">Unless you sent it to their personal email address, print out the employee's Office 365 sign in name and password, and hand it to them.</span></span> <span data-ttu-id="137b7-129">または、電話で情報を伝えます。</span><span class="sxs-lookup"><span data-stu-id="137b7-129">Or tell them the information over the phone.</span></span>
  
<span data-ttu-id="137b7-130">まだ Office 365 メールにアクセスできないため、その電子メールアドレスに情報を送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="137b7-130">Because they won't yet have access to their Office 365 email, don't send the information to that email address.</span></span>
  
## <a name="step-3-explain-where-to-sign-in"></a><span data-ttu-id="137b7-131">手順 3: サインインする場所を説明する</span><span class="sxs-lookup"><span data-stu-id="137b7-131">Step 3: Explain where to sign in</span></span> 


<span data-ttu-id="137b7-132">Facebook、Amazon、Gmail と同様に、従業員は Office 365 を使用するためにサインインします。</span><span class="sxs-lookup"><span data-stu-id="137b7-132">Just like Facebook, Amazon, or Gmail, your employee signs in to use Office 365.</span></span> <span data-ttu-id="137b7-133">ユーザーに次のサインイン情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="137b7-133">Give them the following sign in information:</span></span>
  
- <span data-ttu-id="137b7-134">にサインイン[https://www.office.com](https://www.office.com)します。</span><span class="sxs-lookup"><span data-stu-id="137b7-134">Sign in at [https://www.office.com](https://www.office.com).</span></span>
    
- <span data-ttu-id="137b7-135">[**サインイン**] を選択し、ユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="137b7-135">Select **Sign in**, then type the user ID and password.</span></span>
    
## <a name="step-4-help-your-employee-get-started"></a><span data-ttu-id="137b7-136">手順 4: 従業員の作業の開始を支援する</span><span class="sxs-lookup"><span data-stu-id="137b7-136">Step 4: Help your employee get started</span></span>


<span data-ttu-id="137b7-137">[Office 365 の従業員クイックセットアップ](https://support.office.com/article/69cd80a8-56b8-436f-aa1f-2d2a3cc51060)がサインインして、ソフトウェアをインストールし、メールをセットアップするなど、ユーザーと共有します。</span><span class="sxs-lookup"><span data-stu-id="137b7-137">Share with them the [Employee quick setup for Office 365](https://support.office.com/article/69cd80a8-56b8-436f-aa1f-2d2a3cc51060) to sign in, install software, set up email, and more.</span></span> 
  
<span data-ttu-id="137b7-138">次に、これらを開始するためのクイックリファレンスを示します。</span><span class="sxs-lookup"><span data-stu-id="137b7-138">And here's a quick reference to help get them started:</span></span>
  
|<span data-ttu-id="137b7-139">**タスク**</span><span class="sxs-lookup"><span data-stu-id="137b7-139">**Task**</span></span>|<span data-ttu-id="137b7-140">**詳細を検索する**</span><span class="sxs-lookup"><span data-stu-id="137b7-140">**Find the details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="137b7-141">Office へのサインイン</span><span class="sxs-lookup"><span data-stu-id="137b7-141">Sign in to Office</span></span>  <br/> |<span data-ttu-id="137b7-142">に[https://www.office.com](https://www.office.com)移動し、[**サインイン**] を選択して、OFFICE 365 のユーザー ID とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="137b7-142">Go to [https://www.office.com](https://www.office.com), select **Sign in**, and then enter your Office 365 user ID and password.</span></span>  <br/> |
|<span data-ttu-id="137b7-143">Office アプリをコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="137b7-143">Install Office apps onto your computer.</span></span>  <br/><br/> |<span data-ttu-id="137b7-144">サインインすると、ホームページに Word や Outlook などのアプリをダウンロードしてインストールするためのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="137b7-144">When you sign in, the home page has a link to download and install apps like Word and Outlook.</span></span>  <span data-ttu-id="137b7-145">[**Office のインストール**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="137b7-145">Select **Install Office**.</span></span>         <span data-ttu-id="137b7-146">手順については、「 [Office をインストールする方法](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-146">For instructions, see [How to install Office](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).</span></span>  <br/> |
|<span data-ttu-id="137b7-147">Outlook 2016 で電子メールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="137b7-147">Set up your email in Outlook 2016 .</span></span>  <br/> |<span data-ttu-id="137b7-148">Office アプリをコンピューターにインストールしたら、電子メールをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="137b7-148">Once Office apps are installed on your computer, set up your email.</span></span> <span data-ttu-id="137b7-149">手順については、「 [Outlook をセットアップする方法](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-149">For instructions, see [How to setup Outlook](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx).</span></span>  <br/> |
|<span data-ttu-id="137b7-150">Skype for Business をセットアップして、会社や世界中の同僚やビジネスパートナーと接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="137b7-150">Set up Skype for Business so you can connect with co-workers or business partners in your company or around the world.</span></span> <span data-ttu-id="137b7-151">IM、音声、またはビデオ通話で会話を開始できます。</span><span class="sxs-lookup"><span data-stu-id="137b7-151">You can start conversations with IM, voice, or video calls.</span></span>  <br/> |<span data-ttu-id="137b7-152">[コンピューターに Skype For business をインストール](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="137b7-152">[Install Skype for Business on your computer](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb.aspx).</span></span>  <br/> <br/><span data-ttu-id="137b7-153">Skype for Business の使用方法について[は、ビデオをご覧ください。](https://support.office.com/article/3a21eca4-434d-41f1-ab06-3d4a268573b7.aspx)</span><span class="sxs-lookup"><span data-stu-id="137b7-153">To learn how to use Skype for Business, [watch a video.](https://support.office.com/article/3a21eca4-434d-41f1-ab06-3d4a268573b7.aspx)</span></span> <br/> <br/><span data-ttu-id="137b7-154">Skype for business をセットアップして、従業員が無料の Skype アプリを使用している会社の外部のユーザーに連絡できるようにしますか。</span><span class="sxs-lookup"><span data-stu-id="137b7-154">Have you set up Skype for Business so your employees can contact people external to your business who are using the free Skype app?</span></span> <span data-ttu-id="137b7-155">そうでない場合は、Skype for Business を使用するときに予想されることがわかるように、新しい従業員に通知します。</span><span class="sxs-lookup"><span data-stu-id="137b7-155">If not, tell your new employee so they know what to expect when using Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="137b7-156">電話で電子メールを受信するか、Skype for Business を使用する場合は、モバイルデバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="137b7-156">Install apps on your mobile device if you want to get email or use Skype for Business on your phone.</span></span>  <br/> |<span data-ttu-id="137b7-157">Outlook mobile アプリを設定して、電話で電子メールを取得できるようにする場合。</span><span class="sxs-lookup"><span data-stu-id="137b7-157">If you want to set up the Outlook mobile app so you can get email via your phone.</span></span> <span data-ttu-id="137b7-158">手順については、「 [iOS](https://support.office.com/article/b2de2161-cc1d-49ef-9ef9-81acd1c8e234.aspx)、 [Android](https://support.office.com/article/886db551-8dfa-4fd5-b835-f8e532091872.aspx)、 [Windows Phone](https://support.office.com/article/181a112a-be92-49ca-ade5-399264b3d417.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-158">For instructions, see [iOS](https://support.office.com/article/b2de2161-cc1d-49ef-9ef9-81acd1c8e234.aspx), [Android](https://support.office.com/article/886db551-8dfa-4fd5-b835-f8e532091872.aspx), [Windows Phone](https://support.office.com/article/181a112a-be92-49ca-ade5-399264b3d417.aspx)</span></span> <br/> <br/><span data-ttu-id="137b7-159">モバイルデバイスで Skype for Business を使用する場合は、モバイルアプリをダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="137b7-159">If you want to use Skype for Business on your mobile device, download and install the mobile app.</span></span> <span data-ttu-id="137b7-160">手順については、「 [iOS](https://support.office.com/article/3239c8a3-cf55-4ff0-a967-5de51911c049.aspx)、 [Android](https://support.office.com/article/95be9226-2d72-4e94-8a17-bc3c9edf445b.aspx)、 [Windows Phone](https://support.office.com/article/52d8008e-ebf0-4b2a-afd9-f05614c8e9d7.aspx) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="137b7-160">For instructions, see [iOS](https://support.office.com/article/3239c8a3-cf55-4ff0-a967-5de51911c049.aspx), [Android](https://support.office.com/article/95be9226-2d72-4e94-8a17-bc3c9edf445b.aspx), [Windows Phone](https://support.office.com/article/52d8008e-ebf0-4b2a-afd9-f05614c8e9d7.aspx)</span></span> <br/> |
|<span data-ttu-id="137b7-161">OneDrive for Business のトレーニングを完了すると、ドキュメント、プレゼンテーション、およびスプレッドシートをクラウドに保存して整理する方法を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="137b7-161">Complete the OneDrive for Business training to help you learn how to store and organize your documents, presentations, and spreadsheets in the cloud.</span></span>  <br/> |<span data-ttu-id="137b7-162">OneDrive for Business を使用して、クラウド内のビジネス関連ドキュメントを保持します。</span><span class="sxs-lookup"><span data-stu-id="137b7-162">Keep your business-related documents in the cloud by using OneDrive for Business.</span></span> <span data-ttu-id="137b7-163">別のコンピューターで Office 365 にサインインしている場合でも、常にコンテンツにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="137b7-163">You can always get to your content, even if you're signed in to Office 365 on a different computer.</span></span> [<span data-ttu-id="137b7-164">OneDrive for business の使用方法についてのビデオを見る</span><span class="sxs-lookup"><span data-stu-id="137b7-164">Watch a video to learn how to use your OneDrive for Business</span></span>](https://support.office.com/article/b30da4eb-ddd2-44b6-943b-e6fbfc6b8dde.aspx) <br/><br/> <span data-ttu-id="137b7-165">**トレーニング:** [onedrive for business のトレーニング](https://support.office.com/article/1f608184-b7e6-43ca-8753-2ff679203132.aspx)(onedrive for business の選択)。</span><span class="sxs-lookup"><span data-stu-id="137b7-165">**Training:** [OneDrive for Business training](https://support.office.com/article/1f608184-b7e6-43ca-8753-2ff679203132.aspx) (Select OneDrive for Business).</span></span>  <br/> |
|<span data-ttu-id="137b7-166">SharePoint Online トレーニングを完了して、同僚との共同作業やコンテンツの共有に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="137b7-166">Complete the SharePoint Online training to help you collaborate with coworkers and share content.</span></span>  <br/> |<span data-ttu-id="137b7-167">同僚がアクセスするドキュメントを SharePoint Online に保持するための最善の場所です。</span><span class="sxs-lookup"><span data-stu-id="137b7-167">The best place to keep documents that your coworkers will also access is in SharePoint Online.</span></span>  <br/> <br/><span data-ttu-id="137b7-168">**トレーニング:** [ビデオ: SharePoint Online を使用してチームコンテンツを共同作業する](https://support.office.com/article/2dd9aeff-7749-4b78-9696-eb0f6267f1f5.aspx)</span><span class="sxs-lookup"><span data-stu-id="137b7-168">**Training:** [Video: Collaborate with team content using SharePoint Online](https://support.office.com/article/2dd9aeff-7749-4b78-9696-eb0f6267f1f5.aspx)</span></span> <br/><br/> <span data-ttu-id="137b7-169">**以下を参照してください。** 組織は SharePoint Online をどのように使用していますか。どのような種類のドキュメントがそこに保存されますか。</span><span class="sxs-lookup"><span data-stu-id="137b7-169">**Find out:** How is your organization using SharePoint Online, and what type of documents get stored there.</span></span> <span data-ttu-id="137b7-170">また、OneDrive for Business に保存されているドキュメントもあります。</span><span class="sxs-lookup"><span data-stu-id="137b7-170">Also, which documents are stored in OneDrive for Business.</span></span>  <br/> |

   
## <a name="related-articles"></a><span data-ttu-id="137b7-171">関連記事</span><span class="sxs-lookup"><span data-stu-id="137b7-171">Related articles</span></span>


[<span data-ttu-id="137b7-172">Office 365 から元従業員を削除する</span><span class="sxs-lookup"><span data-stu-id="137b7-172">Remove a former employee from Office 365</span></span>](remove-former-employee.md)
  
[<span data-ttu-id="137b7-173">Office 365 にユーザーを個別に、またはまとめて追加する</span><span class="sxs-lookup"><span data-stu-id="137b7-173">Add users individually or in bulk to Office 365</span></span>](add-users.md)
  
