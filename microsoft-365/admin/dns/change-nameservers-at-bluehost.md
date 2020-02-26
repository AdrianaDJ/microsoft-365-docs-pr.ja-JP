---
title: Bluehost で Office 365 をセットアップするためにネーム サーバーを変更する
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
ms.assetid: 7712b6af-329c-43a0-af7b-c4e4c1befb0e
description: 'Bluehost で DNS レコードを管理するために Office 365 をセットアップする方法について説明します。 '
ms.openlocfilehash: 27d73071a08477b0adc372d8a88db2c805fecacf
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241133"
---
# <a name="change-nameservers-to-set-up-office-365-with-bluehost"></a><span data-ttu-id="36adc-103">Bluehost で Office 365 をセットアップするためにネーム サーバーを変更する</span><span class="sxs-lookup"><span data-stu-id="36adc-103">Change nameservers to set up Office 365 with Bluehost</span></span>

 <span data-ttu-id="36adc-104">**探している内容が見つからない場合は、[ドメインに関する FAQ を確認](../setup/domains-faq.md)** してください。</span><span class="sxs-lookup"><span data-stu-id="36adc-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="36adc-p101">Office 365 で Office 365 DNS レコードを管理する場合は、以下の手順に従います ([Bluehost で Office 365 のすべての DNS レコードを管理することもできます](create-dns-records-at-bluehost.md))。</span><span class="sxs-lookup"><span data-stu-id="36adc-p101">Follow these instructions if you want Office 365 to manage your Office 365 DNS records for you. (If you prefer, you can [manage all your Office 365 DNS records at Bluehost](create-dns-records-at-bluehost.md).)</span></span>
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="36adc-107">確認のための TXT レコードを追加する</span><span class="sxs-lookup"><span data-stu-id="36adc-107">Add a TXT record for verification</span></span>

<span data-ttu-id="36adc-p102">Office 365 でドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Office 365 に対してドメインを所有していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="36adc-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36adc-p103">このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。</span><span class="sxs-lookup"><span data-stu-id="36adc-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="36adc-112">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36adc-112">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="36adc-113">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="36adc-113">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36adc-114">[ **domains**] ページにある [ **domain**] 領域で、変更するドメインの行を見つけ、そのドメインのチェックボックスを選びます。</span><span class="sxs-lookup"><span data-stu-id="36adc-114">On the **domains** page, in the **domain** area, find the row for the domain that you're changing, and then select the check box for that domain.</span></span> 
    
    <span data-ttu-id="36adc-115">(下へスクロールしなければならないことがあります。)</span><span class="sxs-lookup"><span data-stu-id="36adc-115">(You may have to scroll down.)</span></span> 
    
3. <span data-ttu-id="36adc-116">[ **Domain_name** ] 領域の**dns ゾーンエディタ**行で、[ **dns レコードの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-116">In the **domain_name** area, on the **DNS Zone Editor** row, select **Manage DNS records**.</span></span>
    
4. <span data-ttu-id="36adc-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="36adc-117">On the **DNS Zone Editor** page, in the Add DNS Record area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="36adc-118">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="36adc-118">(Choose the **Type** value from the drop-down list.)</span></span> 
    
|||||
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36adc-119">**Host Record**</span><span class="sxs-lookup"><span data-stu-id="36adc-119">**Host Record**</span></span> <br/> |<span data-ttu-id="36adc-120">**TTL**</span><span class="sxs-lookup"><span data-stu-id="36adc-120">**TTL**</span></span> <br/> |<span data-ttu-id="36adc-121">**Type**</span><span class="sxs-lookup"><span data-stu-id="36adc-121">**Type**</span></span> <br/> |<span data-ttu-id="36adc-122">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="36adc-122">**TXT Value**</span></span> <br/> |
|@  <br/> |<span data-ttu-id="36adc-123">14400</span><span class="sxs-lookup"><span data-stu-id="36adc-123">14400</span></span>  <br/> |<span data-ttu-id="36adc-124">TXT</span><span class="sxs-lookup"><span data-stu-id="36adc-124">TXT</span></span>  <br/> |<span data-ttu-id="36adc-125">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="36adc-125">MS=ms *XXXXXXXX*</span></span> <br/> <span data-ttu-id="36adc-126">**注:** これは例です。</span><span class="sxs-lookup"><span data-stu-id="36adc-126">**Note:** This is an example.</span></span> <span data-ttu-id="36adc-127">Office 365 の表から [ **宛先またはポイント先のアドレス** ] の値を指定してください。</span><span class="sxs-lookup"><span data-stu-id="36adc-127">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="36adc-128">確認する方法</span><span class="sxs-lookup"><span data-stu-id="36adc-128">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) <br/> |

   
5. <span data-ttu-id="36adc-129">[ **Add record**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-129">Select **add record**.</span></span>
    
6. <span data-ttu-id="36adc-130">数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。</span><span class="sxs-lookup"><span data-stu-id="36adc-130">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="36adc-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="36adc-131">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="36adc-132">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="36adc-132">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="36adc-133">管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。</span><span class="sxs-lookup"><span data-stu-id="36adc-133">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="36adc-134">[**ドメイン**] ページで、確認するドメインを選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-134">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="36adc-135">[**セットアップ**] ページで、[**セットアップの開始**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-135">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="36adc-136">[**ドメインの確認**] ページで、[**確認**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-136">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="36adc-p106">通常、DNS の変更が反映されるまでの時間は約 15 分です。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加後にメール フローなどに問題が発生した場合は、「[Office 365 でドメインまたは DNS レコードを追加後に問題を特定して解決する](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36adc-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="36adc-140">ドメインのネーム サーバー (NS) レコードを変更する</span><span class="sxs-lookup"><span data-stu-id="36adc-140">Change your domain's nameserver (NS) records</span></span>

<span data-ttu-id="36adc-p107">Office 365 でドメインをセットアップするには、Office 365 のプライマリ ネーム サーバーとセカンダリ ネーム サーバーを参照するように、ドメインの NS レコードをドメイン レジストラーで変更します。これで、ドメインの DNS レコードを更新するように Office 365 で設定されます。メール、Skype for Business Online、一般向け Web サイトをドメインで利用できるようにすべてのレコードを追加し、すべての設定を完了します。</span><span class="sxs-lookup"><span data-stu-id="36adc-p107">To complete setting up your domain with Office 365, you change your domain's NS records at your domain registrar to point to the Office 365 primary and secondary name servers. This sets up Office 365 to update the domain's DNS records for you. We'll add all records so that email, Skype for Business Online, and your public website work with your domain, and you'll be all set.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="36adc-p108">ドメインの NS レコードを Office 365 のネーム サーバーをポイントするように変更すると、現在ドメインに関連付けられているすべてのサービスが影響を受けます。たとえば、この変更後、ドメイン (rob@ *your_domain*  .com など) に送信されるすべてのメールは、Office 365 に送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="36adc-p108">When you change your domain's NS records to point to the Office 365 name servers, all the services that are currently associated with your domain are affected. For example, all email sent to your domain (like rob@ *your_domain*  .com) will start coming to Office 365 after you make this change.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="36adc-146">次の手順では、リストからその他の不要なネームサーバーを削除する方法と、正しいネームサーバーが表示されていない場合には追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36adc-146">The following procedure will show you how to delete any other, unwanted nameservers from the list, and also how to add the correct nameservers if they are not already listed.</span></span> <span data-ttu-id="36adc-147">> このセクションの手順を完了すると、次の4つのネームサーバーのみが表示されます。 > ns1.bdm.microsoftonline.com > ns2.bdm.microsoftonline.com > ns3.bdm.microsoftonline.com > ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-147">>  When you have completed the steps in this section, the only nameservers that should be listed are these four: >  ns1.bdm.microsoftonline.com >  ns2.bdm.microsoftonline.com >  ns3.bdm.microsoftonline.com >  ns4.bdm.microsoftonline.com</span></span> 
  
1. <span data-ttu-id="36adc-148">まず、[このリンク](https://my.bluehost.com/cgi/dm)を使って Bluehost でドメイン ページにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="36adc-148">To get started, go to your domains page at Bluehost by using [this link](https://my.bluehost.com/cgi/dm).</span></span> <span data-ttu-id="36adc-149">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="36adc-149">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="36adc-150">[**ドメイン**] ページの [ **domain_name** ] 領域で、ドメインのチェックボックスをオンにして、[**ネームサーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-150">On the **domains** page, in the **domain_name** area, select the checkbox for your domain, and then select **name servers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-1](../media/8f384386-197c-4272-9675-82037922dac4.png)
  
3. <span data-ttu-id="36adc-152">[ **Domain_name** ] 領域で、[**カスタムネームサーバーを使用する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-152">In the **domain_name** area, select **Use Custom Nameservers**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-2](../media/9fb47d21-c4ce-4eee-af90-c9569870a329.png)
  
4. <span data-ttu-id="36adc-154">現在表示されているページに既に一覧表示されているネームサーバーがあるかどうかに応じて、以下の 2 つの手順のいずれかに進みます。</span><span class="sxs-lookup"><span data-stu-id="36adc-154">Depending on whether or not there are already nameservers listed on the page that is displayed now, continue to one of the two following procedures:</span></span>
    
  - <span data-ttu-id="36adc-155">既に一覧表示されているネーム サーバーが **ない** 場合は、 [既に一覧表示されているネームサーバーがない場合](#if-there-are-no-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="36adc-155">If there are **NO** nameservers already listed, [If there are NO nameservers already listed](#if-there-are-no-nameservers-already-listed).</span></span>
    
  - <span data-ttu-id="36adc-156">既に一覧表示されているネーム サーバーが **ある** 場合は、 [既に一覧表示されているネームサーバーがある場合](#if-there-are-nameservers-already-listed)。</span><span class="sxs-lookup"><span data-stu-id="36adc-156">If there **ARE** nameservers already listed, [If there ARE nameservers already listed](#if-there-are-nameservers-already-listed).</span></span>
    
### <a name="if-there-are-no-nameservers-already-listed"></a><span data-ttu-id="36adc-157">既に一覧表示されているネームサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="36adc-157">If there are NO nameservers already listed</span></span>

1. <span data-ttu-id="36adc-158">[ **Use Custom Nameservers**] セクションで、次の表の値を入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36adc-158">In the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="36adc-159">**最初の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-159">**First empty row**</span></span> <br/> |<span data-ttu-id="36adc-160">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-160">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="36adc-161">**2 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-161">**Second empty row**</span></span> <br/> |<span data-ttu-id="36adc-162">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-162">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-1](../media/07b13d6d-a34e-45b5-afd5-48ebd4c1344f.png)
  
2. <span data-ttu-id="36adc-164">[**行の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-164">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
3. <span data-ttu-id="36adc-166">さらに [ **カスタム ネームサーバーの使用**] セクションで、次の表の最初の行の値を、新しい空の行に入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36adc-166">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="36adc-167">**3 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-167">**Third empty row**</span></span> <br/> |<span data-ttu-id="36adc-168">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-168">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="36adc-169">**4 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-169">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="36adc-170">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-170">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
    ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
4. <span data-ttu-id="36adc-171">4番目のネームサーバーレコードを追加するには、[**行の追加**] をもう一度選択し、上記の表の最後の行の値を使用してレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="36adc-171">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
5. <span data-ttu-id="36adc-172">[**ネームサーバー設定の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-172">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="36adc-p111">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36adc-p111">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
### <a name="if-there-are-nameservers-already-listed"></a><span data-ttu-id="36adc-176">既に一覧表示されているネームサーバーがある場合</span><span class="sxs-lookup"><span data-stu-id="36adc-176">If there ARE nameservers already listed</span></span>

> [!CAUTION]
> <span data-ttu-id="36adc-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span><span class="sxs-lookup"><span data-stu-id="36adc-177">Follow these steps only if you have existing nameservers other than the four correct nameservers.</span></span> <span data-ttu-id="36adc-178">(つまり、 **ns1.bdm.microsoftonline.com**、 **ns2.bdm.microsoftonline.com**、 **ns3.bdm.microsoftonline.com**、または**ns4.bdm.microsoftonline.com**という名前が付いて*いない*現在のネームサーバーのみを削除します)。</span><span class="sxs-lookup"><span data-stu-id="36adc-178">(That is, delete only any current nameservers that are  *not*  named **ns1.bdm.microsoftonline.com**, **ns2.bdm.microsoftonline.com**, **ns3.bdm.microsoftonline.com**, or **ns4.bdm.microsoftonline.com**.)</span></span> 
  
1. <span data-ttu-id="36adc-179">他のネーム サーバーが表示されている場合は、各ネーム サーバーを選び、キーボードの **Delete** キーを押して削除します。</span><span class="sxs-lookup"><span data-stu-id="36adc-179">If there are any other name servers listed, delete each of them by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![Bluehost-BP-Redelegate-1-5](../media/d1051c43-f8ff-46d7-af26-3975d3f0f621.png)
  
2. <span data-ttu-id="36adc-181">さらに [ **Use Custom Nameservers**] セクションで、次の表の値を入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36adc-181">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the following table.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="36adc-182">**最初の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-182">**First empty row**</span></span> <br/> |<span data-ttu-id="36adc-183">ns1.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-183">ns1.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="36adc-184">**2 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-184">**Second empty row**</span></span> <br/> |<span data-ttu-id="36adc-185">ns2.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-185">ns2.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3](../media/1523debf-5eb0-4765-8e05-bcd56e375c20.png)
  
3. <span data-ttu-id="36adc-187">[**行の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-187">Select **Add Row**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-3-2](../media/db34b632-1d10-44b7-aa1f-44bd27bf09e3.png)
  
4. <span data-ttu-id="36adc-189">さらに [ **カスタム ネームサーバーの使用**] セクションで、次の表の最初の行の値を、新しい空の行に入力またはコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="36adc-189">Still in the **Use Custom Nameservers** section, type or copy and paste the values from the first row of the following table into the new empty row.</span></span> 
    
|||
|:-----|:-----|
|<span data-ttu-id="36adc-190">**3 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-190">**Third empty row**</span></span> <br/> |<span data-ttu-id="36adc-191">ns3.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-191">ns3.bdm.microsoftonline.com</span></span>  <br/> |
|<span data-ttu-id="36adc-192">**4 つ目の空の行**</span><span class="sxs-lookup"><span data-stu-id="36adc-192">**Fourth empty row**</span></span> <br/> |<span data-ttu-id="36adc-193">ns4.bdm.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="36adc-193">ns4.bdm.microsoftonline.com</span></span>  <br/> |
   
   ![Bluehost-BP-Redelegate-1-3-3](../media/480b32bb-af27-40a5-90c5-5617ed02bb41.png)
  
5. <span data-ttu-id="36adc-195">4番目のネームサーバーレコードを追加するには、[**行の追加**] をもう一度選択し、上記の表の最後の行の値を使用してレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="36adc-195">To add the fourth Nameserver record, select **Add Row** again, and create a record using the values from the last row of the above table.</span></span> 
    
6. <span data-ttu-id="36adc-196">[**ネームサーバー設定の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="36adc-196">Select **save nameserver settings**.</span></span>
    
    ![Bluehost-BP-Redelegate-1-4](../media/b24a4cfd-924b-4b6d-ad3d-2dea148fc77f.png)
  
> [!NOTE]
> <span data-ttu-id="36adc-p113">ネーム サーバー レコードの更新がインターネットの DNS システム全体に反映されるまでに、最大で数時間かかる場合があります。Office 365 のメールと他のサービスの準備が完了し、ドメインで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="36adc-p113">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  