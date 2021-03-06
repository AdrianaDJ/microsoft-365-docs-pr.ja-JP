---
title: Microsoft の Freenom で DNS レコードを作成する
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: d8ff45a2-19e3-413d-aa64-a9982bd6633c
description: ドメインを確認し、電子メール、Skype for Business Online、および Microsoft の Freenom の他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: 2fc2407193d41d6e0526aacad0b2b558f1b21bdb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646189"
---
# <a name="create-dns-records-at-freenom-for-microsoft"></a>Microsoft の Freenom で DNS レコードを作成する

探している内容が見つからない場合は、[ドメインに関する FAQ](../setup/domains-faq.md) を確認してください。 
  
> [!CAUTION]
> Freenom web サイトは、SRV レコードをサポートしていません。つまり、いくつかの Skype for Business Online および Outlook Web App の機能が動作しないことを意味します。 どの Microsoft プランを使用する場合でも、サービスには重要な制限があり、別の DNS ホスティングプロバイダーに切り替えることが必要になる場合があります。 
  
サービスの制限にかかわらず、Microsoft DNS レコードを Freenom で管理することを選択した場合は、この記事の手順に従って、ドメインを確認し、電子メールやその他のサービスの DNS レコードを設定します。
  
  
> [!NOTE]
> 通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-a-txt-record-for-verification"></a>確認のための TXT レコードを追加する
<a name="bkmk_txt"> </a>

Microsoft のドメインを使うには、ドメインを所有していることを確認する必要があります。自分のドメイン レジストラーで自分のアカウントにログインし、DNS レコードを作成することができれば、Microsoft に対してドメインを所有していることを確認することができます。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認するためだけに使用されます。その他には影響しません。 必要に応じて、後で削除することができます。 
  
1. まず、 [このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [ **サービス**] を選択し、[ **マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの **管理**] を選択します。
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom Manage Freenom DNS](../../media/9854a511-27e3-4658-8903-34b3d425096d.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。 
    
    ![Freenom Add Record type TXT](../../media/7f0e85e7-844f-4962-815e-5d80d9e6efa0.png)
  
6. 新規レコードのボックスに、次の表の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**Type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |TXT  <br/> |3600 (秒)  <br/> |MS = msXXXXXXXX  <br/> **注:** これは例です。 この表から **[宛先またはポイント先のアドレス]** の値を指定してください。           [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Freenom TXT values for verification](../../media/650098df-b3aa-47e5-9763-7fde24e34c3f.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom TXT record Save Changes](../../media/b1a63f9a-4578-491a-9554-c40f73b37e09.png)
  
8. 数分待つと、続行できます。この間、作成したレコードがインターネット全体で更新されます。
    
これで、ドメイン レジストラーのサイトでレコードが追加されました。Microsoft に戻り、レコードをリクエストします。
  
Microsoft で正しい TXT レコードが見つかった場合、ドメインは確認済みとなります。
  
1. Microsoft 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

    
2. **[ドメイン]** ページで、確認するドメインを選択します。 
    
    
  
3. **[セットアップ]** ページで、**[セットアップの開始]** を選択します。
    
    
  
4. **[ドメインの確認]** ページで、**[確認]** を選択します。
    
    
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>MX レコードを追加して、自分のドメインのメールが Microsoft に届くようにする
<a name="bkmk_mx"> </a>

1. まず、 [このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [ **サービス**] を選択し、[ **マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの **管理**] を選択します。
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. ドメインの名前機能を既定の Freenom ネームサーバーに設定します。 [ **管理ツール**] を選択し、[ **ネーム**サーバー] を選択します。
    
    ![Freenom Nameservers setting](../../media/a6ae877a-c248-42b9-bae9-210a80cd01e7.png)
  
5. [既定のネームサーバーを **使用する** ] が選択されていることを確認し、[ネームサーバーの **変更**] を選択します
    
    ![Freenom Change Nameservers](../../media/0ef90d84-c0a0-4ef9-9e4c-43ef0aac3a2e.png)
  
6. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../../media/f55a8053-2411-45da-a357-776c6699f721.png)
  
7. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **MX** ] を選びます。 
    
    ![Freenom Add Record type MX](../../media/c728c6ee-786c-4f6a-8ad5-1d9914a5bfcf.png)
  
8. 新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**名前**|**Type**|**TTL**|**Target**|**Priority**|
    |:-----|:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |MX (Mail Exchanger)  <br/> |3600 (秒)  <br/> |\<domain-key\>. mail.protection.outlook.com  <br/> **注:***\<domain-key\>* Microsoft アカウントからを取得します。   [確認する方法](../get-help-with-domains/information-for-dns-records.md)          |10    <br/> 優先度の詳細については、「[What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)」を参照してください。 <br/> |
   
   ![Freenom MX record](../../media/8896c4a9-b3dd-45ed-9916-f7da2715ba8c.png)
  
9. [ **Save Changes**] を選びます。
    
    ![Freenom MX record Save Changes](../../media/7aa0a464-d136-417f-be40-48d3f728eeb7.png)
  
10. その他の MX レコードがある場合は、すべてを削除します。 レコードごとに [ **削除**] を選択します。 メッセージを **本当に削除したい場合は** 、[ **OK**] を選択します。
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a>Microsoft に必要な CNAME レコードを追加する
<a name="bkmk_cname"> </a>

1. まず、 [このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [ **サービス**] を選択し、[ **マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの **管理**] を選択します。
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../../media/5e7bc3a7-0d5e-431b-bb27-da3b0f316d01.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **CNAME** ] を選びます。 
    
    ![Freenom Add Record type CNAME](../../media/9b204755-ca2a-46d2-bce2-030d82fd1f9e.png)
  
6. 最初の CNAME レコードを作成します。新規レコードのボックスに、次の表の 1 行目の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Record type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |autodiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |autodiscover.outlook.com  <br/> |
    |sip  <br/> |CNAME  <br/> |3600 (秒)  <br/> |sipdir.online.lync.com  <br/> |
    |lyncdiscover  <br/> |CNAME  <br/> |3600 (秒)  <br/> |webdir.online.lync.com  <br/> |
    |enterpriseregistration  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseregistration.windows.net  <br/> |
    |enterpriseenrollment  <br/> |CNAME  <br/> |3600 (秒)  <br/> |enterpriseenrollment-s.manage.microsoft.com  <br/> |
   
    ![Freenom CNAME values](../../media/752fc682-e3f2-4b9c-9253-bf1ba2d414e9.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom CNAME Save Changes](../../media/68103fd2-0f5f-4aac-a875-25157c6bbdd2.png)
  
8. 前の手順を繰り返し、他の 5 つの CNAME レコードを作成します。 
    
    レコードごとに、上のテーブルの次の行の値をそのレコードのボックスに入力するか、コピーして貼り付けます。
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="bkmk_spf"> </a>

> [!IMPORTANT]
> 1 つのドメインで、SPF に複数の TXT レコードを設定することはできません。 1 つのドメインに複数の SPF レコードがあると、メール、配信の分類、迷惑メールの分類で問題が発生することがあります。 使用しているドメインに既に SPF レコードがある場合は、Microsoft 用に新しいレコードを作成しないでください。 代わりに、値のセットを含む  *1 つ*  の SPF レコードがあるように、現在のレコードに必要な Microsoft の値を追加します。 

1. まず、 [このリンク](https://my.freenom.com/)を使って Freenom のドメインページにアクセスします。 ログインするように求められます。
    
    ![Freenom login](../../media/90a32855-bfdd-4dfe-881c-b9a36b2f0582.png)
  
2. [ **サービス**] を選択し、[ **マイドメイン**] を選択します。
    
    ![Freenom select Services and My Domains](../../media/1917ced2-e254-4aec-9096-46d339b84d9a.png)
  
3. 編集するドメインの場合は、[ドメインの **管理**] を選択します。
    
    ![Freenom select Manage Domain](../../media/67737b71-8b1b-42a6-abaf-62d776d3eb87.png)
  
4. [ **Manage Freenom DNS**] を選択します。
    
    ![Freenom select Freenom DNS の管理](../../media/94809955-0315-409c-a15d-703a2fe4c4ed.png)
  
5. [ **Add Record** ] の [ **Type** ] 列でメニューから [ **TXT** ] を選びます。 
    
    ![Freenom Add Record type TXT](../../media/d8854285-c4ae-416c-a072-72a11ba1cd9a.png)
  
6. 新規レコードのボックスに次の値を入力するか、コピーして貼り付けます。 
    
    |**Name**|**Record type**|**TTL**|**Target**|
    |:-----|:-----|:-----|:-----|
    |(空白のまま)  <br/> |TXT  <br/> |3600 (秒)  <br/> |v=spf1 include:spf.protection.outlook.com -all  <br/>**注:** スペースも正しく入力されるように、この値をコピーして貼り付けることをお勧めします。           |
   
    ![Freenom TXT values for SPF](../../media/1b3b1199-9104-4ca1-acdb-786d139c21ac.png)
  
7. [ **Save Changes**] を選びます。
    
    ![Freenom TXT record for SPF Save Changes](../../media/e2fc52b1-0dcb-4595-9a4c-fca5e2ef9f97.png)
  

