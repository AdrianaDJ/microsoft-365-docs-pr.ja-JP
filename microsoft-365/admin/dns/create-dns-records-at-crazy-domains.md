---
title: Crazy Domains で Office 365 用の DNS レコードを作成する
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
ms.assetid: 6386d63e-b78f-4736-90e7-b99a2c116a9f
description: ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスを使用している Office 365 のドメインの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 5b344ebdc4a4608c27c0a84299ea171391c09ba0
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248162"
---
# <a name="create-dns-records-at-crazy-domains-for-office-365"></a><span data-ttu-id="5a741-103">Crazy Domains で Office 365 用の DNS レコードを作成する</span><span class="sxs-lookup"><span data-stu-id="5a741-103">Create DNS records at Crazy Domains for Office 365</span></span>

 <span data-ttu-id="5a741-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5a741-105">使用している DNS ホスティング プロバイダーが Crazy Domains の場合は、この記事に示す手順に従い、ドメインを確認して、メールや Skype for Business Online などの DNS レコードを設定します。</span><span class="sxs-lookup"><span data-stu-id="5a741-105">If Crazy Domains is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5a741-106">これらのレコードを Crazy Domains で追加すると、使用しているドメインが、Office 365 のサービスで機能するように設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a741-106">After you add these records at Crazy Domains, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="5a741-107">Office 365 での Web サイト向け Web ホスティングと DNS の詳細については、「[Office 365 でのパブリック Web サイトの使用](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a741-p101">通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5a741-111">確認用に TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5a741-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5a741-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5a741-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5a741-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a741-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5a741-p104">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p104">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5a741-120">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-120">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5a741-122">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-122">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5a741-124">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-124">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5a741-126">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-126">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5a741-128">[ **Add Record**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-128">Choose **TXT Record** from the **Add Record** drop-down list.</span></span> 
    
    ![CrazyDomains-検証-1-1](../media/f0ffdefb-d7a5-47df-bb5e-bf8a3bcc9b01.png)
  
7. <span data-ttu-id="5a741-130">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-130">Select **Add**.</span></span>
    
    ![CrazyDomains-検証-1-2](../media/b0cd623a-67f7-4bae-a5b5-507f5a106123.png)
  
8. <span data-ttu-id="5a741-132">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a741-132">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5a741-133">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="5a741-133">**Sub Domain**</span></span>|<span data-ttu-id="5a741-134">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="5a741-134">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5a741-135">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5a741-135">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5a741-136">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5a741-136">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5a741-p105">**注:** これは例です。Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。           [情報の取得方法](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="5a741-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>          |
   
    ![CrazyDomains-検証-1-3](../media/3867de97-6a98-4475-9bda-470bac75d483.png)
  
9. <span data-ttu-id="5a741-141">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-141">Select **Update**.</span></span>
    
    ![CrazyDomains-検証-1-4](../media/0e416df6-b7a2-4dd7-971c-f1cc31df30da.png)
  
10. <span data-ttu-id="5a741-143">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="5a741-143">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5a741-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="5a741-144">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="5a741-145">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="5a741-145">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5a741-146">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="5a741-146">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5a741-147">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-147">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5a741-148">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-148">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5a741-149">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-149">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5a741-p106">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="5a741-153">MX レコードを追加して、自分のドメインのメールが Office 365 に届くようにする</span><span class="sxs-lookup"><span data-stu-id="5a741-153">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="5a741-154"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5a741-154"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5a741-p107">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p107">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5a741-158">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-158">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5a741-160">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-160">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5a741-162">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-162">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5a741-164">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-164">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5a741-166">[ **Add Record:**] ボックスの一覧から [ **MX Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-166">Choose **MX Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-2-1](../media/63f7ab77-e686-4e7b-a3a2-1ac28a02d5f3.png)
  
7. <span data-ttu-id="5a741-168">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-168">Select **Add**.</span></span>
    
    ![CrazyDomains-2-2](../media/a60680a1-2513-498c-b42f-8ffa575ee48e.png)
  
8. <span data-ttu-id="5a741-170">新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a741-170">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="5a741-171">(ドロップダウンリストから**優先度**の値を選択します。)</span><span class="sxs-lookup"><span data-stu-id="5a741-171">(Choose the **Priority** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="5a741-172">**メール送信先ゾーン**</span><span class="sxs-lookup"><span data-stu-id="5a741-172">**Mail For Zone**</span></span>|<span data-ttu-id="5a741-173">**優先度**</span><span class="sxs-lookup"><span data-stu-id="5a741-173">**Priority**</span></span>|<span data-ttu-id="5a741-174">**割り当て先サーバー**</span><span class="sxs-lookup"><span data-stu-id="5a741-174">**Assigned To Server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5a741-175">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="5a741-175">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5a741-176">1-d</span><span class="sxs-lookup"><span data-stu-id="5a741-176">1</span></span>  <br/> <span data-ttu-id="5a741-177">優先度の詳細については、「[MX 優先度とは何か](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5a741-178">*\<ドメインキー\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a741-178">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5a741-179">**注:** Office 365 アカウントから\* \<ドメイン\>キー\*を取得します。</span><span class="sxs-lookup"><span data-stu-id="5a741-179">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="5a741-180">確認する方法</span><span class="sxs-lookup"><span data-stu-id="5a741-180">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
   ![CrazyDomains-2-3](../media/e27df6a6-19a6-4e58-9716-a74be1c3f8da.png)
  
9. <span data-ttu-id="5a741-182">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-182">Select **Update**.</span></span>
    
    ![CrazyDomains-2-4](../media/ba25cdef-a436-48bf-b0e9-5dffd03234a4.png)
  
10. <span data-ttu-id="5a741-184">その他の MX レコードが [ **Mx Record** ] セクションに表示されている場合は、いずれかのレコードに対して [**変更**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-184">If there are any other MX records listed in the **MX Record** section, select **Modify** for one of those records.</span></span> 
    
    ![CrazyDomains-2-5](../media/9acdda39-33ec-4b24-ad83-91c26f9c599b.png)
  
11. <span data-ttu-id="5a741-186">**[削除]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-186">Select **Delete**.</span></span>
    
    ![CrazyDomains-2-6](../media/50b0e263-6f21-41b3-8fa0-7dd55dbe6c2e.png)
  
12. <span data-ttu-id="5a741-188">[**更新**] を選択して、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a741-188">Select **Update** to confirm the deletion.</span></span> 
    
    ![CrazyDomains-2-7](../media/db751bfe-31c2-4632-a491-6893eda38a51.png)
  
13. <span data-ttu-id="5a741-190">この手順の前半で追加した MX レコードだけを残し、同じ手順で、一覧に表示されているその他の MX レコードをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="5a741-190">Use the same process to remove any other MX records in the list, until only the one that you added earlier in this procedure remains.</span></span>
    
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="5a741-191">Office 365 に必要な 6 つの CNAME レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5a741-191">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="5a741-192"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5a741-192"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5a741-p109">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p109">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5a741-196">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-196">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5a741-198">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-198">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5a741-200">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-200">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5a741-202">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-202">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5a741-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5a741-204">Choose **CNAME Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-3-1](../media/2f02538b-fc79-46d2-a2b7-1022eaf0fb08.png)
  
7. <span data-ttu-id="5a741-206">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-206">Select **Add**.</span></span>
    
    ![CrazyDomains-3-2](../media/4c5929cf-1c21-4af9-899b-e36091f0f14d.png)
  
8. <span data-ttu-id="5a741-208">6 つの CNAME レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a741-208">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="5a741-209">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a741-209">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5a741-210">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="5a741-210">**Sub Domain**</span></span>|<span data-ttu-id="5a741-211">**エイリアス**</span><span class="sxs-lookup"><span data-stu-id="5a741-211">**Alias for**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5a741-212">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5a741-212">autodiscover</span></span>  <br/> |<span data-ttu-id="5a741-213">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5a741-213">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5a741-214">sip</span><span class="sxs-lookup"><span data-stu-id="5a741-214">sip</span></span>  <br/> |<span data-ttu-id="5a741-215">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a741-215">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5a741-216">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5a741-216">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5a741-217">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a741-217">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5a741-218">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5a741-218">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5a741-219">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5a741-219">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5a741-220">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5a741-220">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5a741-221">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5a741-221">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![CrazyDomains-3-3](../media/81a7b837-3f4d-4565-89a9-380e4d318acf.png)
  
9. <span data-ttu-id="5a741-223">[ **ADD CNAME Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-223">Select **Add CNAME Record**.</span></span>
    
    ![CrazyDomains-3-4](../media/9bcba729-7085-4ebc-8183-ecde82f5c364.png)
  
10. <span data-ttu-id="5a741-225">2 番目の CNAME レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a741-225">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="5a741-226">新規レコードのボックスに、表の次の行の値を使用し、[ **ADD CNAME record**] をもう一度選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-226">In the boxes for the new record, use the values from the next row in the table, and then again select **Add CNAME Record**.</span></span>
    
    <span data-ttu-id="5a741-227">6 つの CNAME レコードの作成がすべて完了するまで、このプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="5a741-227">Repeat this process until you have created all six CNAME records.</span></span>
    
11. <span data-ttu-id="5a741-228">[**更新**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a741-228">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-3-5](../media/dbe578f6-359c-428c-b296-ca624cecfc3c.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5a741-230">迷惑メールの防止に役立つ、SPF の TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5a741-230">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5a741-231"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5a741-231"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a741-232">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="5a741-232">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5a741-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="5a741-233">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5a741-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="5a741-234">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="5a741-235">代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。</span><span class="sxs-lookup"><span data-stu-id="5a741-235">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="5a741-p111">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p111">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5a741-239">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-239">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5a741-241">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-241">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5a741-243">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-243">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5a741-245">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-245">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5a741-247">[ **Add Record:**] ボックスの一覧から [ **TXT Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-247">Choose **TXT Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-4-1](../media/7f2461e2-0468-49bd-9eb0-981e9b2f72d6.png)
  
7. <span data-ttu-id="5a741-249">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-249">Select **Add**.</span></span>
    
    ![CrazyDomains-4-2](../media/64ef9e1f-676d-46e2-9253-a83d9bcd1c4e.png)
  
8. <span data-ttu-id="5a741-251">新規レコードのボックスに、次の表の値を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a741-251">In the boxes for the new record, type or paste the values from the following table.</span></span>
    
    |<span data-ttu-id="5a741-252">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="5a741-252">**Sub Domain**</span></span>|<span data-ttu-id="5a741-253">**テキスト レコード**</span><span class="sxs-lookup"><span data-stu-id="5a741-253">**Text Record**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="5a741-254">(このフィールドは空のままにします。)</span><span class="sxs-lookup"><span data-stu-id="5a741-254">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5a741-255">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5a741-255">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5a741-256">**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5a741-256">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![CrazyDomains-4-3](../media/e7fd524a-c94b-4cdd-b264-67abb532a71b.png)
  
9. <span data-ttu-id="5a741-258">**[更新]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-258">Select **Update**.</span></span>
    
    ![CrazyDomains-4-4](../media/d4f378ee-0f14-46ae-ba32-1596660ecf91.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="5a741-260">Office 365 に必要な 2 個の SRV レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="5a741-260">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="5a741-261"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5a741-261"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5a741-p112">まず、[このリンク](https://manage.crazydomains.com/members/domains/)を使って Crazy Domains でドメイン ページにアクセスします。最初にログインするように求められます。</span><span class="sxs-lookup"><span data-stu-id="5a741-p112">To get started, go to your domains page at Crazy Domains by using [this link](https://manage.crazydomains.com/members/domains/). You'll be prompted to log in first.</span></span>
    
    ![CrazyDomains-1-1](../media/40c5117c-acad-4fe5-bf0d-d3c362b08a16.png)
  
2. <span data-ttu-id="5a741-265">**[マイアカウント**] セクションで、[ **Domains**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-265">In the **My Account** section, select **Domains**.</span></span>
    
    ![CrazyDomains-1-2](../media/778576c3-560e-4ffb-b3b4-bd92fc6a6bd4.png)
  
3. <span data-ttu-id="5a741-267">[**ドメイン名**] ページの [**ドメイン**] セクションで、更新するドメインの名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-267">On the **Domain Names** page, in the **Domain** section, select the name of the domain that you are updating.</span></span> 
    
    ![CrazyDomains-1-3](../media/4dd7bb74-c8ed-4b4a-b4c1-d9538fc6bd9a.png)
  
4. <span data-ttu-id="5a741-269">[ **DNS 設定**] セクションで、ドロップダウンリストアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-269">In the **DNS Settings** section, select the drop-down list icon.</span></span> 
    
    ![CrazyDomains-1-4-1](../media/c7573fbf-467d-49c1-abb6-8c7b9b4af83d.png)
  
5. <span data-ttu-id="5a741-271">[ **Add Record** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-271">Select **Add Record**.</span></span>
    
    ![CrazyDomains-1-4-2](../media/7bef31f5-f180-4b61-a462-9326789e770f.png)
  
6. <span data-ttu-id="5a741-273">[ **Add Record:**] ボックスの一覧から [ **SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-273">Choose **SRV Record** from the **Add Record:** drop-down list.</span></span> 
    
    ![CrazyDomains-5-1](../media/156acebc-7f6d-4b5e-8493-6bc62ca0ee27.png)
  
7. <span data-ttu-id="5a741-275">[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a741-275">Select **Add**.</span></span>
    
    ![CrazyDomains-5-2](../media/6a711df7-4215-49b2-b58f-1cf1a242b383.png)
  
8. <span data-ttu-id="5a741-277">2 つの SRV レコードの最初のレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a741-277">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5a741-278">新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="5a741-278">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    |<span data-ttu-id="5a741-279">**レコードの種類**</span><span class="sxs-lookup"><span data-stu-id="5a741-279">**Record Type**</span></span>|<span data-ttu-id="5a741-280">**サブドメイン**</span><span class="sxs-lookup"><span data-stu-id="5a741-280">**Sub Domain**</span></span>|<span data-ttu-id="5a741-281">**優先度**</span><span class="sxs-lookup"><span data-stu-id="5a741-281">**Priority**</span></span>|<span data-ttu-id="5a741-282">**Weight**</span><span class="sxs-lookup"><span data-stu-id="5a741-282">**Weight**</span></span>|<span data-ttu-id="5a741-283">**Port**</span><span class="sxs-lookup"><span data-stu-id="5a741-283">**Port**</span></span>|<span data-ttu-id="5a741-284">**対象**</span><span class="sxs-lookup"><span data-stu-id="5a741-284">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5a741-285">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="5a741-285">SRV Record</span></span>  <br/> |<span data-ttu-id="5a741-286">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="5a741-286">_sip._tls</span></span>  <br/> |<span data-ttu-id="5a741-287">100</span><span class="sxs-lookup"><span data-stu-id="5a741-287">100</span></span>  <br/> |<span data-ttu-id="5a741-288">1-d</span><span class="sxs-lookup"><span data-stu-id="5a741-288">1</span></span>  <br/> |<span data-ttu-id="5a741-289">443</span><span class="sxs-lookup"><span data-stu-id="5a741-289">443</span></span>  <br/> |<span data-ttu-id="5a741-290">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a741-290">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5a741-291">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="5a741-291">SRV Record</span></span>  <br/> |<span data-ttu-id="5a741-292">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="5a741-292">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5a741-293">100</span><span class="sxs-lookup"><span data-stu-id="5a741-293">100</span></span>  <br/> |<span data-ttu-id="5a741-294">1-d</span><span class="sxs-lookup"><span data-stu-id="5a741-294">1</span></span>  <br/> |<span data-ttu-id="5a741-295">5061</span><span class="sxs-lookup"><span data-stu-id="5a741-295">5061</span></span>  <br/> |<span data-ttu-id="5a741-296">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5a741-296">sipfed.online.lync.com</span></span>  <br/> |
   
    ![CrazyDomains-5-3](../media/cc0ea6eb-7358-434e-bd1a-2737725c6d41.png)
  
9. <span data-ttu-id="5a741-298">[ **ADD SRV Record**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a741-298">Select **Add SRV Record**.</span></span>
    
    ![CrazyDomains-5-4](../media/de4ec312-6833-469a-b23a-f376140a35ca.png)
  
10. <span data-ttu-id="5a741-300">残りの SRV レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a741-300">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5a741-301">新規レコードのボックスで、次の表の 2 行目の値を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a741-301">In the boxes for the new record, use the values from the second row in the table.</span></span>
    
11. <span data-ttu-id="5a741-302">[**更新**] を選択して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="5a741-302">Select **Update** to save your changes.</span></span> 
    
    ![CrazyDomains-5-5](../media/f0bb1dd6-3772-4293-bf74-710f635e0658.png)
  
> [!NOTE]
> <span data-ttu-id="5a741-p113">通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a741-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  