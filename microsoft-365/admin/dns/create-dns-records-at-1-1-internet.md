---
title: Office 365 用の 1&1 IONOS で DNS レコードを作成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5762c3ca-1de2-4999-bfe5-4c5e25a8957e
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを 1&1 IONOS for Office 365 で設定する方法について説明します。
ms.openlocfilehash: 88a46fa51ac3e259d617d6d6e1a3dbb189c1ee6d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42243001"
---
# <a name="create-dns-records-at-11-ionos-for-office-365"></a><span data-ttu-id="36dc2-103">Office 365 用の 1&1 IONOS で DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="36dc2-103">Create DNS records at 1&1 IONOS for Office 365</span></span>

 <span data-ttu-id="36dc2-104">探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="36dc2-105">1&1 IONOS では、ドメインは MX レコードとトップレベル自動検出 CNAME レコードの両方を持つことはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-105">Note that 1&1 IONOS doesn't allow a domain to have both an MX record and a top-level Autodiscover CNAME record.</span></span> <span data-ttu-id="36dc2-106">これにより、Office 365 用に Exchange Online を構成する方法が制限されます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-106">This limits the ways in which you can configure Exchange Online for Office 365.</span></span> <span data-ttu-id="36dc2-107">回避策がありますが、1&1 IONOS でサブドメインを作成した経験がある場合に**のみ**、この方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-107">There is a workaround, but we recommend employing it **only** if you already have experience with creating subdomains at 1&1 IONOS.</span></span> <span data-ttu-id="36dc2-108">> このサービスの[制限](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx)にかかわらず、1&1 IONOS で独自の OFFICE 365 DNS レコードを管理することを選択する場合は、この記事の手順に従って、ドメインを確認し、電子メール、Skype For business Online などの dns レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-108">> If despite this [service limitation](https://support.office.com/article/7ae9a655-041d-4724-aa92-60392ee390c2.aspx) you choose to manage your own Office 365 DNS records at 1&1 IONOS, follow the steps in this article to verify your domain and to set up DNS records for email, Skype for Business Online, and so on.</span></span> 
  
<span data-ttu-id="36dc2-109">これらのレコードを 1&1 IONOS に追加すると、使用しているドメインが、Office 365 サービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-109">After you add these records at 1&1 IONOS, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="36dc2-110">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-110">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-p102">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p102">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="36dc2-114">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="36dc2-114">Add a TXT record for verification</span></span>

<span data-ttu-id="36dc2-p103">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p103">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-p104">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p104">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="36dc2-119">次の手順を実行するか、[ビデオ (0 分 42 秒から開始) をご覧ください](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="36dc2-119">Follow the steps below or [watch the video (start at 0:42)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
1. <span data-ttu-id="36dc2-120">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-120">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="36dc2-121">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="36dc2-121">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="36dc2-122">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-122">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="36dc2-123">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-123">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="36dc2-124">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-124">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="36dc2-125">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-125">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="36dc2-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="36dc2-126">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="36dc2-127">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-127">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="36dc2-128">**Type**</span><span class="sxs-lookup"><span data-stu-id="36dc2-128">**Type**</span></span> <br/> |<span data-ttu-id="36dc2-129">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="36dc2-129">**Prefix**</span></span> <br/> |<span data-ttu-id="36dc2-130">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="36dc2-130">**Name Value**</span></span> <br/> |
    |<span data-ttu-id="36dc2-131">TXT</span><span class="sxs-lookup"><span data-stu-id="36dc2-131">TXT</span></span>  <br/> |<span data-ttu-id="36dc2-132">(このフィールドは空白のままにしておきます)</span><span class="sxs-lookup"><span data-stu-id="36dc2-132">(Leave this field blank)</span></span>  <br/> |<span data-ttu-id="36dc2-133">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="36dc2-133">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="36dc2-134">注: これは例です。</span><span class="sxs-lookup"><span data-stu-id="36dc2-134">NOTE: This is an example.</span></span> <span data-ttu-id="36dc2-135">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-135">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="36dc2-136">確認する方法</span><span class="sxs-lookup"><span data-stu-id="36dc2-136">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
7. <span data-ttu-id="36dc2-137">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-137">Select **Save**.</span></span>
    
8. <span data-ttu-id="36dc2-138">[**保存**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-138">Select **Save** again.</span></span> 
    
9. <span data-ttu-id="36dc2-139">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-139">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="36dc2-140">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="36dc2-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="36dc2-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="36dc2-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="36dc2-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="36dc2-143">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="36dc2-144">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="36dc2-145">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-145">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="36dc2-146">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-146">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="36dc2-p107">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="36dc2-150">MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにする</span><span class="sxs-lookup"><span data-stu-id="36dc2-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="36dc2-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="36dc2-151"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="36dc2-152">次の手順を実行するか、[ビデオ (3 分 22 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-152">Follow the steps below or [watch the video (start at 3:22)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-153">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-153">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="36dc2-154">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-154">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="36dc2-155">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="36dc2-155">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="36dc2-156">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-156">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="36dc2-157">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-157">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="36dc2-158">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-158">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="36dc2-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span><span class="sxs-lookup"><span data-stu-id="36dc2-159">In the **MX Records** section, in the \*\* Mail Exchanger (MX Record) \*\* area, select **Other mail server**.</span></span><br/><span data-ttu-id="36dc2-160">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="36dc2-160">(You may have to scroll down.)</span></span><br/><span data-ttu-id="36dc2-161">![1&amp;1-BP-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-161">![1&amp;1-BP-Configure-2-1](../media/b0db72ae-9431-460f-ba7a-3268590b892e.png)</span></span> <br/>
  
6. <span data-ttu-id="36dc2-162">既に他の MX レコードがある場合は、それぞれのレコードを選び、キーボードの **Delete** キーを押して、レコードを削除します</span><span class="sxs-lookup"><span data-stu-id="36dc2-162">If there are any MX records already listed, delete each of them by selecting the record and then pressing the **Delete** key on your keyboard.</span></span><br/><span data-ttu-id="36dc2-163">(登録されている MX レコードがない場合は、次の手順に進みます)。</span><span class="sxs-lookup"><span data-stu-id="36dc2-163">(If there are no MX records already listed, continue to the next step.)</span></span><br/><span data-ttu-id="36dc2-164">![1&amp;1-BP-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-164">![1&amp;1-BP-Configure-2-2](../media/4a39bac7-7310-481d-bda4-1dd5c220c60f.png)</span></span><br/>
  
7. <span data-ttu-id="36dc2-165">[ **MX 1**] レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-165">In the boxes for the **MX 1** record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="36dc2-166">**MX 1**</span><span class="sxs-lookup"><span data-stu-id="36dc2-166">**MX 1**</span></span>|<span data-ttu-id="36dc2-167">**Priority**</span><span class="sxs-lookup"><span data-stu-id="36dc2-167">**Priority**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="36dc2-168">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/>  <span data-ttu-id="36dc2-169">注: Office 365 \<アカウントからドメイン\>キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-169">NOTE: Get your \<domain-key\> from your Office 365 account.</span></span> [<span data-ttu-id="36dc2-170">確認する方法</span><span class="sxs-lookup"><span data-stu-id="36dc2-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="36dc2-171">10 </span><span class="sxs-lookup"><span data-stu-id="36dc2-171">10</span></span>  <br/> <span data-ttu-id="36dc2-172">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-172">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | 
    
    ![1および 1-構成2および3](../media/3afb04d1-7bbf-4147-89ae-561e14ded26d.png)<br/>
  
8. <span data-ttu-id="36dc2-174">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-174">Select **Save**.</span></span><br/><span data-ttu-id="36dc2-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-175">(You may have to scroll down.)</span></span><br/><span data-ttu-id="36dc2-176">![1&amp;1-BP-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-176">![1&amp;1-BP-Configure-2-4](../media/355b3ba7-4d2b-45ed-aa17-ac4affb54fe3.png)</span></span>
  
9. <span data-ttu-id="36dc2-177">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-177">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="36dc2-178">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-178">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="36dc2-179">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="36dc2-179">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="36dc2-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="36dc2-180"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="36dc2-181">1&1 IONOS には、Office 365 電子メールサービスに必要な CNAME レコードと共に MX レコードを使用できるようにするための回避策が必要です。</span><span class="sxs-lookup"><span data-stu-id="36dc2-181">1&1 IONOS requires a workaround so that you can use an MX record together with the CNAME records that are required for Office 365 email services.</span></span> <span data-ttu-id="36dc2-182">この回避策では、1&1 IONOS にサブドメインのセットを作成し、それらを CNAME レコードに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="36dc2-182">This workaround requires you to create a set of subdomains at 1&1 IONOS, and to assign them to CNAME records.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="36dc2-183">この手順を開始する前に、利用可能なサブドメインが 2 つ以上あることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-183">Make sure that you have at least two available subdomains before starting this procedure.</span></span> <span data-ttu-id="36dc2-184">この解決策は、サブドメインの作成に IONOS 1&1 で既に経験している場合にのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-184">We recommend this solution only if you already have experience with creating subdomains at 1&1 IONOS.</span></span> 
  
### <a name="basic-cname-records"></a><span data-ttu-id="36dc2-185">基本的な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="36dc2-185">Basic CNAME records</span></span>

<span data-ttu-id="36dc2-186">次の手順を実行するか、[ビデオ (3 分 57 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-186">Follow the steps below or [watch the video (start at 3:57)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-187">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-187">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="36dc2-188">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-188">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="36dc2-189">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="36dc2-189">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="36dc2-190">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-190">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="36dc2-191">[**ドメインセンター** ] ページで、更新するドメインを見つけ、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-191">On the **Domain Center** page, find the domain that you want to update, and then select **Manage Subdomains**.</span></span><br/><span data-ttu-id="36dc2-192">![1&amp;1-BP-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-192">![1&amp;1-BP-Configure-3-0](../media/d570d03f-5c38-463d-809e-5bb9e4fb2777.png)</span></span> <br/><span data-ttu-id="36dc2-193">次に、2 つのサブドメインを作成して、それぞれの [ **Alias**] 値を設定します</span><span class="sxs-lookup"><span data-stu-id="36dc2-193">Now you'll create two subdomains and set an **Alias** value for each.</span></span><br/><span data-ttu-id="36dc2-194">(1&1 IONOS でサポートされる最上位の CNAME レコードは1つだけなので、このようにする必要がありますが、Office 365 にはいくつかの CNAME レコードが必要です。)</span><span class="sxs-lookup"><span data-stu-id="36dc2-194">(This is required because 1&1 IONOS supports only one top-level CNAME record, but Office 365 requires several CNAME records.)</span></span><br/><span data-ttu-id="36dc2-195">最初に、Autodiscover サブドメインを作成します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-195">First, you'll create the Autodiscover subdomain.</span></span>
    
4. <span data-ttu-id="36dc2-196">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-196">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
    ![1&amp;1-BP-Configure-3-1](../media/95c63639-eb80-443d-8951-98e8b6cdcc4f.png)
  
5. <span data-ttu-id="36dc2-p113">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p113">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span>

    |<span data-ttu-id="36dc2-200">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-200">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-201">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-201">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-202">autodiscover</span><span class="sxs-lookup"><span data-stu-id="36dc2-202">autodiscover</span></span>  <br/> |<span data-ttu-id="36dc2-203">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-203">autodiscover.outlook.com</span></span>   | 

    ![1&amp;1-BP-3-2](../media/9be45113-ebaf-48e6-983c-a7e6ff9eea45.png)
  
6. <span data-ttu-id="36dc2-205">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-205">Select **Create Subdomain**.</span></span><br/><span data-ttu-id="36dc2-206">![1&amp;1-BP-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-206">![1&amp;1-BP-Configure-3-3](../media/1e7bc874-f174-4597-8c08-df611d16a74d.png)</span></span>
  
7. <span data-ttu-id="36dc2-207">[**サブドメインの概要**] セクションで、作成したばかりの**自動検出**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-207">In the **Subdomain Overview** section, locate the **autodiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="36dc2-208">![1&amp;1-BP-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-208">![1&amp;1-BP-Configure-3-4](../media/10e2e446-3e54-4fb2-8a29-8c442536cc31.png)</span></span>
  
8. <span data-ttu-id="36dc2-209">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-209">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span> <br/><span data-ttu-id="36dc2-210">![1&amp;1-BP-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-210">![1&amp;1-BP-Configure-3-5](../media/5c602118-b89b-4897-9faf-0736be8a6a0d.png)</span></span>
  
9. <span data-ttu-id="36dc2-211">[ **A/AAAA レコード (Ip アドレス)** ] セクションの [ **Ip アドレス (A レコード)** ] 領域で、[ **CNAME**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-211">In the **A/AAAA Records (IP Addresses)** section, in the **IP address (A Record)** area, select **CNAME**.</span></span><br/><span data-ttu-id="36dc2-212">![1&amp;1-BP-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-212">![1&amp;1-BP-Configure-3-6](../media/7f57f468-fbee-4440-a53d-3e334d8e5b71.png)</span></span>
  
10. <span data-ttu-id="36dc2-213">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-213">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span><br/> 
    
    |<span data-ttu-id="36dc2-214">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-214">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-215">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-215">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-216">autodiscover</span><span class="sxs-lookup"><span data-stu-id="36dc2-216">autodiscover</span></span>  <br/> |<span data-ttu-id="36dc2-217">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-217">autodiscover.outlook.com</span></span>   |

    ![1&amp;1-BP-3-7](../media/afac3118-3337-4f99-98dd-a7ca930230ce.png)
  
11. <span data-ttu-id="36dc2-219">免責事項の [ **I am aware**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-219">Select the check box for the **I am aware** disclaimer.</span></span><br/><span data-ttu-id="36dc2-220">![1&amp;1-BP-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-220">![1&amp;1-BP-Configure-3-8-1](../media/6c4cac1a-23f2-4ff3-b2d1-3dca908638d2.png)</span></span>
  
12. <span data-ttu-id="36dc2-221">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-221">Select **Save**.</span></span><br/><span data-ttu-id="36dc2-222">![1&amp;1-BP-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-222">![1&amp;1-BP-Configure-3-8-2](../media/ea1dfc06-c175-4146-ab40-da4d162097e1.png)</span></span>
  
  
### <a name="additional-cname-records"></a><span data-ttu-id="36dc2-223">追加の CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="36dc2-223">Additional CNAME records</span></span>

<span data-ttu-id="36dc2-p114">以降の手順に従って追加の CNAME レコードを作成すると、Skype for Business Online サービスが有効になります。 手順は、前に 2 つの CNAME レコードを作成したときの手順と同じです。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p114">The additional CNAME records created in the following procedure enable Skype for Business Online services. You will employ the same steps that you used to create the two CNAME records you have already created.</span></span>
  
1. <span data-ttu-id="36dc2-226">3 つ目のサブドメイン (Lyncdiscover) を作成します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-226">Create the third subdomain (Lyncdiscover).</span></span><br/><span data-ttu-id="36dc2-227">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-227">On the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
2. <span data-ttu-id="36dc2-p115">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p115">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.)</span></span><br/> 
    
    |<span data-ttu-id="36dc2-230">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-230">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-231">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-231">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-232">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="36dc2-232">lyncdiscover</span></span>   |<span data-ttu-id="36dc2-233">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-233">webdir.online.lync.com</span></span>  |
   
3. <span data-ttu-id="36dc2-234">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-234">Select **Create Subdomain**.</span></span>
    
4. <span data-ttu-id="36dc2-235">[**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-235">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
5. <span data-ttu-id="36dc2-236">[**サブドメインの概要**] セクションで、作成したばかりの**lyncdiscover**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-236">In the **Subdomain Overview** section, find the **lyncdiscover** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="36dc2-237">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-237">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
6. <span data-ttu-id="36dc2-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="36dc2-238">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
7. <span data-ttu-id="36dc2-239">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-239">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> <br/>
    
    |<span data-ttu-id="36dc2-240">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-240">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-241">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-241">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-242">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="36dc2-242">lyncdiscover</span></span>  <br/> |<span data-ttu-id="36dc2-243">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-243">webdir.online.lync.com</span></span>  <br/> |
   
8. <span data-ttu-id="36dc2-244">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-244">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
9. <span data-ttu-id="36dc2-245">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-245">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
10. <span data-ttu-id="36dc2-246">4 つ目のサブドメイン (SIP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-246">Create the fourth subdomain (SIP):</span></span> <br/><span data-ttu-id="36dc2-247">[**サブドメインの概要**] セクションで、[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-247">In the **Subdomain Overview** section, select **Create Subdomain**.</span></span>
    
11. <span data-ttu-id="36dc2-p116">新しいサブドメインの [ **Create Subdomain**] ボックスに、次の表の **Create Subdomain** 値のみを入力するか、コピーして貼り付けます ( **Alias** 値は後の手順で追加します)。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p116">In the **Create Subdomain** box for the new subdomain, type or copy and paste only the **Create Subdomain** value from the following table. (You'll add the **Alias** value in a later step.) </span></span><br/>
    
    |<span data-ttu-id="36dc2-250">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-250">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-251">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-251">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-252">sip</span><span class="sxs-lookup"><span data-stu-id="36dc2-252">sip</span></span>  <br/> |<span data-ttu-id="36dc2-253">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-253">sipdir.online.lync.com</span></span>  <br/> |
   
12. <span data-ttu-id="36dc2-254">[**サブドメインの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-254">Select **Create Subdomain**.</span></span>
    
13. <span data-ttu-id="36dc2-255">[**ドメインセンター** ] ページで、[サブドメインの**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-255">On the **Domain Center** page, select **Manage Subdomains**.</span></span>
    
14. <span data-ttu-id="36dc2-256">[**サブドメインの概要**] セクションで、作成したばかりの**sip**サブドメインを見つけて、そのサブドメインの [ **Panel (v)** ] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-256">In the **Subdomain Overview** section, find the **sip** subdomain that you just created, and then select the **Panel (v)** control for that subdomain.</span></span> <br/><span data-ttu-id="36dc2-257">[**サブドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-257">In the **Subdomain Settings** area, select **Edit DNS Settings**.</span></span>
    
15. <span data-ttu-id="36dc2-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span><span class="sxs-lookup"><span data-stu-id="36dc2-258">In the **A/AAAA Records (IP Addresses)** section, in the \*\* IP address (A Record) \*\* area, select **CNAME**.</span></span>
    
16. <span data-ttu-id="36dc2-259">[ **Alias**] ボックスに、次の表の **Alias** 値のみを入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-259">In the **Alias:** box, type or copy and paste only the **Alias** value from the following table.</span></span> 
    
    |<span data-ttu-id="36dc2-260">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-260">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-261">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-261">**Alias**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="36dc2-262">sip</span><span class="sxs-lookup"><span data-stu-id="36dc2-262">sip</span></span>  <br/> |<span data-ttu-id="36dc2-263">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-263">sipdir.online.lync.com</span></span>  <br/> |
   
17. <span data-ttu-id="36dc2-264">[ **I am aware** ] 免責事項のチェックボックスをオンにして、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-264">Select the check box for the **I am aware** disclaimer, and then select **Save**.</span></span>
    
18. <span data-ttu-id="36dc2-265">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-265">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span>
    
### <a name="cname-records-needed-for-mdm"></a><span data-ttu-id="36dc2-266">MDM に必要な CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="36dc2-266">CNAME records needed for MDM</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36dc2-267">手順は、他の 4 個の CNAME レコードの場合と同じですが、次の表の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-267">Follow the procedure that you used for the other four CNAME records, but supply the values from the following table.</span></span> 
  
|<span data-ttu-id="36dc2-268">**Create Subdomain**</span><span class="sxs-lookup"><span data-stu-id="36dc2-268">**Create Subdomain**</span></span>|<span data-ttu-id="36dc2-269">**Alias**</span><span class="sxs-lookup"><span data-stu-id="36dc2-269">**Alias**</span></span>|
|:-----|:-----|
|<span data-ttu-id="36dc2-270">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="36dc2-270">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="36dc2-271">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="36dc2-271">enterpriseregistration.windows.net</span></span>  <br/> |
|<span data-ttu-id="36dc2-272">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="36dc2-272">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="36dc2-273">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-273">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="36dc2-274">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="36dc2-274">Add a TXT record for SPF to help prevent email spam</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36dc2-275">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="36dc2-275">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="36dc2-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="36dc2-276">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="36dc2-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="36dc2-277">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="36dc2-278">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-278">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="36dc2-279">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-279">Need examples?</span></span> <span data-ttu-id="36dc2-280">参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-280">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="36dc2-281">SPF レコードを検証するには、これらの[spf 検証ツール](../setup/domains-faq.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-281">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
<span data-ttu-id="36dc2-282">次の手順を実行するか、[ビデオ (5 分 9 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-282">Follow the steps below or [watch the video (start at 5:09)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-283">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-283">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="36dc2-284">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-284">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="36dc2-285">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="36dc2-285">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="36dc2-286">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-286">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="36dc2-287">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** (**v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-287">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** (**v**) control for that domain.</span></span>
    
4. <span data-ttu-id="36dc2-288">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-288">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="36dc2-289">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-289">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="36dc2-290">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-290">(You may have to scroll down.)</span></span>
    
6. <span data-ttu-id="36dc2-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="36dc2-291">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> <br/><span data-ttu-id="36dc2-292">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-292">(Choose the **Type** value from the drop-down list.)</span></span> <br/>
    
    |<span data-ttu-id="36dc2-293">**型**</span><span class="sxs-lookup"><span data-stu-id="36dc2-293">**Type**</span></span>|<span data-ttu-id="36dc2-294">**Prefix**</span><span class="sxs-lookup"><span data-stu-id="36dc2-294">**Prefix**</span></span>|<span data-ttu-id="36dc2-295">**Name Value**</span><span class="sxs-lookup"><span data-stu-id="36dc2-295">**Name Value**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="36dc2-296">TXT</span><span class="sxs-lookup"><span data-stu-id="36dc2-296">TXT</span></span>  <br/> |<span data-ttu-id="36dc2-297">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-297">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="36dc2-298">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="36dc2-298">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="36dc2-299">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-299">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           | 
    
    ![TXT レコード](../media/0b3ba3b4-64b9-4d68-9ee1-04eb3a17d4c5.png)
  
7. <span data-ttu-id="36dc2-301">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-301">Select **Save**.</span></span><br/><span data-ttu-id="36dc2-302">![レコードを追加する](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-302">![Add record](../media/0f222eb9-3bfd-4908-9a99-516cc6fb1d0e.png)</span></span>
  
8. <span data-ttu-id="36dc2-303">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-303">Select **Save**.</span></span><br/><span data-ttu-id="36dc2-304">![レコードを保存する](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-304">![Save record](../media/86ed1b59-31b2-4094-9cd4-32b94eb09e35.png)</span></span>
  
9. <span data-ttu-id="36dc2-305">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-305">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span><br/><span data-ttu-id="36dc2-306">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-306">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="36dc2-307">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="36dc2-307">Add the two SRV records that are required for Office 365</span></span>

<span data-ttu-id="36dc2-308">次の手順を実行するか、[ビデオ (5 分 51 秒から開始) を参照](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-308">Follow the steps below or [watch the video (start at 5:51)](https://support.office.com/article/Video-Create-DNS-records-at-1-1-Internet-for-Office-365-543fb112-ecf5-47ae-b096-07f3f942a089?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!NOTE]
> <span data-ttu-id="36dc2-309">1und1.de に登録した場合は、[ここにサインイン](https://go.microsoft.com/fwlink/?linkid=859152)してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-309">If you've registered with 1und1.de, [sign in here](https://go.microsoft.com/fwlink/?linkid=859152).</span></span> 
  
1. <span data-ttu-id="36dc2-310">まず、[このリンク](https://my.1and1.com/)を使用して 1&1 IONOS でドメインページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36dc2-310">To get started, go to your domains page at 1&1 IONOS by using [this link](https://my.1and1.com/).</span></span> <span data-ttu-id="36dc2-311">You'll be prompted to log in.</span><span class="sxs-lookup"><span data-stu-id="36dc2-311">You'll be prompted to log in.</span></span>
    
2. <span data-ttu-id="36dc2-312">[ **Manage domains**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-312">Select **Manage domains**.</span></span>
    
3. <span data-ttu-id="36dc2-313">[**ドメインセンター** ] ページで、更新するドメインを見つけて、そのドメインの [ **Panel** ( **v**)] コントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-313">On the **Domain Center** page, find the domain that you want to update, and then select the **Panel** ( **v**) control for that domain.</span></span>
    
4. <span data-ttu-id="36dc2-314">[**ドメインの設定**] 領域で、[ **DNS 設定の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-314">In the **Domain Settings** area, select **Edit DNS Settings**.</span></span>
    
5. <span data-ttu-id="36dc2-315">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-315">In the **TXT and SRV Records** section, select **Add Record**.</span></span>
    
6. <span data-ttu-id="36dc2-316">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-316">Add the first of the two SRV records.</span></span><br/><span data-ttu-id="36dc2-317">[ **Add Record**] 領域にある新規レコードのボックスに、次の表の最初の行の値を入力するか、コピーして貼り付けます</span><span class="sxs-lookup"><span data-stu-id="36dc2-317">In the **Add Record** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> <br/><span data-ttu-id="36dc2-318">(ドロップダウンリストから [ **Type** ] と [ **TTL** ] の値を選びます。)</span><span class="sxs-lookup"><span data-stu-id="36dc2-318">(Choose the **Type** and **TTL** values from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="36dc2-319">**Type**</span><span class="sxs-lookup"><span data-stu-id="36dc2-319">**Type**</span></span>|<span data-ttu-id="36dc2-320">**Service**</span><span class="sxs-lookup"><span data-stu-id="36dc2-320">**Service**</span></span>|<span data-ttu-id="36dc2-321">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="36dc2-321">**Protocol**</span></span>|<span data-ttu-id="36dc2-322">**Name**</span><span class="sxs-lookup"><span data-stu-id="36dc2-322">**Name**</span></span>|<span data-ttu-id="36dc2-323">**Host**</span><span class="sxs-lookup"><span data-stu-id="36dc2-323">**Host**</span></span>|<span data-ttu-id="36dc2-324">**優先度**</span><span class="sxs-lookup"><span data-stu-id="36dc2-324">**Priority**</span></span>|<span data-ttu-id="36dc2-325">**Weight**</span><span class="sxs-lookup"><span data-stu-id="36dc2-325">**Weight**</span></span>|<span data-ttu-id="36dc2-326">**Port**</span><span class="sxs-lookup"><span data-stu-id="36dc2-326">**Port**</span></span>|<span data-ttu-id="36dc2-327">**TTL**</span><span class="sxs-lookup"><span data-stu-id="36dc2-327">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="36dc2-328">SRV</span><span class="sxs-lookup"><span data-stu-id="36dc2-328">SRV</span></span>  <br/> |<span data-ttu-id="36dc2-329">sip</span><span class="sxs-lookup"><span data-stu-id="36dc2-329">sip</span></span>  <br/> |<span data-ttu-id="36dc2-330">tls</span><span class="sxs-lookup"><span data-stu-id="36dc2-330">tls</span></span>  <br/> |<span data-ttu-id="36dc2-331">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="36dc2-331">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="36dc2-332">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-332">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="36dc2-333">100</span><span class="sxs-lookup"><span data-stu-id="36dc2-333">100</span></span>  <br/> |<span data-ttu-id="36dc2-334">1-d</span><span class="sxs-lookup"><span data-stu-id="36dc2-334">1</span></span>  <br/> |<span data-ttu-id="36dc2-335">443</span><span class="sxs-lookup"><span data-stu-id="36dc2-335">443</span></span>  <br/> |<span data-ttu-id="36dc2-336">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="36dc2-336">3600 (1 h)</span></span>  <br/> |
    |<span data-ttu-id="36dc2-337">SRV</span><span class="sxs-lookup"><span data-stu-id="36dc2-337">SRV</span></span>  <br/> |<span data-ttu-id="36dc2-338">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="36dc2-338">sipfederationtls</span></span>  <br/> |<span data-ttu-id="36dc2-339">tcp</span><span class="sxs-lookup"><span data-stu-id="36dc2-339">tcp</span></span>  <br/> |<span data-ttu-id="36dc2-340">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="36dc2-340">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="36dc2-341">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="36dc2-341">sipfed.online.lync.com</span></span>  <br/> |<span data-ttu-id="36dc2-342">100</span><span class="sxs-lookup"><span data-stu-id="36dc2-342">100</span></span>  <br/> |<span data-ttu-id="36dc2-343">1-d</span><span class="sxs-lookup"><span data-stu-id="36dc2-343">1</span></span>  <br/> |<span data-ttu-id="36dc2-344">5061</span><span class="sxs-lookup"><span data-stu-id="36dc2-344">5061</span></span>  <br/> |<span data-ttu-id="36dc2-345">3600 (1 h)</span><span class="sxs-lookup"><span data-stu-id="36dc2-345">3600 (1 h)</span></span>  <br/> |  
    
    ![1&amp;1-BP-5-1](../media/087e337d-926b-42ff-b11d-b449cfaed76c.png)
  
7. <span data-ttu-id="36dc2-347">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-347">Select **Save**.</span></span> <br/><span data-ttu-id="36dc2-348">![1&amp;1-BP-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-348">![1&amp;1-BP-Configure-5-2](../media/aa5f803d-fb24-48e0-976a-6759c5fd252c.png)</span></span>
  
8. <span data-ttu-id="36dc2-349">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-349">Select **Save**.</span></span> <br/><span data-ttu-id="36dc2-350">![1&amp;1-BP-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-350">![1&amp;1-BP-Configure-5-3](../media/097e7e95-4899-4878-b6e7-c3abd8193c52.png)</span></span>
  
9. <span data-ttu-id="36dc2-351">[ **EDIT DNS Settings** ] ダイアログボックスで、[**はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-351">In the **Edit DNS Settings** dialog box, select **Yes**.</span></span> <br/><span data-ttu-id="36dc2-352">![[DNS 設定の編集] ダイアログボックスで [はい] を選択する](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span><span class="sxs-lookup"><span data-stu-id="36dc2-352">![Selecting Yes in the Edit DNS Settings dialog box](../media/920cc95f-fedf-4da2-94a4-9cb41ed49bcf.png)</span></span>
  
10. <span data-ttu-id="36dc2-353">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-353">Add the other SRV record.</span></span> <br/><span data-ttu-id="36dc2-354">[ **TXT および SRV Records** ] セクションで、[ **Add Record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36dc2-354">In the **TXT and SRV Records** section, select **Add Record**.</span></span> <br/><span data-ttu-id="36dc2-355">[ **Add Record** ] 領域で、表の他の行の値を使用してレコードを作成し、[**追加**]、[**保存**]、および **[はい]** を再度選択してレコードを完成させます。</span><span class="sxs-lookup"><span data-stu-id="36dc2-355">In the **Add Record** area, create a record using the values from the other row in the table, and then again select **Add**, **Save**, and **Yes** to complete the record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="36dc2-p120">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36dc2-p120">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  