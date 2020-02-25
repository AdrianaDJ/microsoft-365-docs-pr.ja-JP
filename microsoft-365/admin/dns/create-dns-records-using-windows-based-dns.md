---
title: Windows ベースの DNS を使用して Office 365 用の DNS レコードを作成する
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
ms.assetid: 9eec911d-5773-422c-9593-40e1147ffbde
description: Office 365 用の Windows ベースの DNS で、ドメインを確認し、電子メール、Skype for Business Online、およびその他のサービスの DNS レコードを設定する方法について説明します。
ms.openlocfilehash: ddea5cb95a7f2abef8b68b37de473f936ee08eb5
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249314"
---
# <a name="create-dns-records-for-office-365-using-windows-based-dns"></a>Windows ベースの DNS を使用して Office 365 用の DNS レコードを作成する

 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
   
Windows ベースの DNS を使用して独自の DNS レコードをホストする場合は、この記事の手順に従って、電子メール、Skype for Business Online などのレコードを設定します。
  
まず、 [dns レコードを Windows ベースの dns で検索して](#find-your-dns-records-in-windows-based-dns)更新できるようにする必要があります。 また、オンプレミスの Active Directory を Office 365 と同期することを計画している場合は、オンプレミスの[Active directory で UPN として使用されるルーティング可能でない電子メールアドレス](#non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory)を参照してください。
  
DNS レコードの追加後にメールフローなどに問題が発生した場合は、「[ドメイン名または dns レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="find-your-dns-records-in-windows-based-dns"></a>Windows ベース DNS 内の DNS レコードを検索する
<a name="BKMK_find_your_dns_1"></a>ドメインの DNS レコードがあるページに移動します。 Windows Server 2008 で作業している**場合は、** > [**実行**] を開きます。 Windows Server 2012 で作業している場合は、Windows キーと**r**キーを押します。 「 **Dnsmgmnt**」と入力し、[ **OK]** を選択します。 Dns マネージャーで、[ ** \<dns サーバー名\> \>前方参照ゾーン  **] を展開します。 ドメインを選択します。 これで、DNS レコードを作成する準備ができました。
   
## <a name="add-mx-record"></a>MX レコードの追加
<a name="BKMK_add_MX"> </a>

MX レコードを追加して、自分のドメインのメールを Office 365 で使えるようにします。
- 追加する MX レコードには、 **ポイント先のアドレス**を示す値が含まれており、\<MX token\>.mail.protection.outlook.com (\<MX token\> の値は MSxxxxxxx など) のような内容です。   
- Office 365 の [DNS レコードの追加] ページの [Exchange Online] セクションの [MX] 行で、[point to アドレス] の下に表示されている値をコピーします。 この値は、このタスクで作成しているレコードで使用します。 
- ドメインの [DNS マネージャー] ページで、[**アクション** > **メールエクスチェンジャー (MX)**] に移動します。 ドメインのこのページを見つけるには、「 [Windows ベースの dns で dns レコードを検索](#find-your-dns-records-in-windows-based-dns)する」を参照してください。  
- [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。 
    - ホスト名: 
    - @Address: Office 365 からコピーしたばかりのアドレス値をここに貼り付けます。  
    - Pref: 
- [ **Save Changes**] を選びます。
- 古い MX レコードをすべて削除します。 他の場所に電子メールをルーティングする、このドメインの古い MX レコードがある場合は、古いレコードの横にあるチェックボックスをオンにして、[**削除** > **OK]** を選択します。 
   
## <a name="add-cname-records"></a>CNAME レコードを追加する
<a name="BKMK_add_CNAME"> </a>

Office 365 に必要な CNAME レコードを追加します。 Office 365 にさらに CNAME レコードが一覧に含まれている場合は、これと同じ全般的な手順に従って追加します。
  
> [!IMPORTANT]
> Office 365 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. (MDM を持っていない場合は、この手順を省略できます)。 

- ドメインの [DNS マネージャー] ページで、[ **Action** > **CNAME (cname)**] に移動します。
- [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: 自動検出
    - 種類: 
    - CNAMEAddress: autodiscover.outlook.com
- [ **O**K] を選択します。

SIP CNAME レコードを追加します。 
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
- [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: sip
    - 型: CNAME
    - アドレス: sipdir.online.lync.com
- **[OK]** をクリックします。

Skype for Business Online の自動検出の CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: lyncdiscover
    - 型: CNAME
    - アドレス: webdir.online.lync.com
- **[OK]** をクリックします。
   
### <a name="add-two-cname-records-for-mobile-device-management-mdm-for-office-365"></a>Office 365 のモバイル デバイス管理 (MDM) 用として 2 つの CNAME レコードを追加する

> [!IMPORTANT]
> Office 365 用のモバイルデバイス管理 (MDM) を使用している場合は、2つの CNAME レコードを追加作成する必要があります。 Follow the procedure that you used for the other four CNAME records, but supply the values from the following table. > (MDM を使用していない場合は、この手順を省略できます)。 
  

MDM Enterpriseregistration CNAME レコードを追加します。  
- ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
- [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
- ホスト名: enterpriseregistration
- 型: CNAME
- アドレス: enterpriseregistration.windows.net
- **[OK]** をクリックします。 

MDM Enterpriseenrollment CNAME レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[ **Action** \> **CNAME (cname)**] に移動します。 
-  [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    - ホスト名: enterpriseenrollment
    - 型: CNAME
    - アドレス: enterpriseenrollment-s.manage.microsoft.com
- **[OK]** をクリックします。
   
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a>迷惑メールの防止に役立つ、SPF の TXT レコードを追加する
<a name="BKMK_add_TXT"> </a>

> [!IMPORTANT]
> You cannot have more than one TXT record for SPF for a domain. If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues. If you already have an SPF record for your domain, don't create a new one for Office 365. 代わりに、現在のレコードに Office 365 で必要になる値を追加して、元々の値と追加する値の組み合わせが  *1 つの*  SPF レコードになるようにします。 
  
自分のドメインの SPF TXT レコードを追加して、電子メールのスパム防止に役立てます。
  
- このレコード (マーケティング電子メールの文字列など) の TXT 値には、既に他の文字列が含まれている場合がありますが、これは問題ありません。 これらの文字列をそのまま残して、この文字列を追加し、各文字列を二重引用符で区切って配置します。 
- ドメインの [DNS マネージャー] ページで、[**アクション** \> **テキスト (TXT)**] に移動します。 
-  [**新しいリソースレコード**] ダイアログボックスで、フィールドが正確に次の値に設定されていることを確認します。 
 > [!IMPORTANT]
> Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。 このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。 

-  ホストの種類:@
-  レコードの種類: TXT
-  アドレス: v = spf1 には、以下のようにします。 
         
-  **[OK]** をクリックします。
   
## <a name="add-srv-records"></a>SRV レコードを追加する
<a name="BKMK_add_SRV"> </a>

Office 365 に必要な2つの SRV レコードを追加します。

Skype for Business Online web 会議の SIP SRV レコードを追加します。  <br/> 
-  ドメインの [DNS マネージャー] ページで、[**アクション** \> **その他の新しいレコード**] に移動します。 
-   [**リソースレコードの種類**] ウィンドウで、[**サービスロケーション (SRV)**] を選択し、[**レコードの作成**] を選択します。 
-   [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    -  サービス: _sip
    -  プロトコル: _tls
    -  優先度: 100
    -  重み: 1
    -  ポート: 443
    -  ターゲット (ホスト名): sipdir.online.lync.com
-  **[OK]** をクリックします。 


Skype for Business Online フェデレーションの SIP SRV レコードを追加します。  
-  ドメインの [DNS マネージャー] ページで、[**アクション** \> **その他の新しいレコード**] に移動します。  
-  [**リソースレコードの種類**] ウィンドウで、[**サービスロケーション (SRV)**] を選択し、[**レコードの作成**] を選択します。 
-   [**新しいリソースレコード**] ダイアログボックスで、フィールドに次の値が正確に設定されていることを確認します。  
    -  サービス: _sipfederationtls
    -  プロトコル: _tcp
    -  優先度: 100
    -  重み: 1
    -  ポート: 5061
    -  ターゲット (ホスト名): sipfed.online.lync.com
-  **[OK]** をクリックします。 
   
## <a name="add-a-record-to-verify-that-you-own-the-domain-if-you-havent-already"></a>ドメインを所有していることを確認するためにレコードを追加します (まだ登録していない場合)。
<a name="BKMK_verify"> </a>

Office 365 サービスをセットアップするために DNS レコードを追加する前に、Office 365 は、追加しているドメインを所有していることを確認する必要があります。 これを行うには、以下の手順に従ってレコードを追加します。
  
> [!NOTE]
> このレコードは、ドメインを所有していることを確認する場合にのみ使用します。その他には影響しません。 
  

1. Office 365 から情報を収集します。  <br/> 
2. 管理センターで、[**設定**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>] ページの順に移動します。 
3. [**ドメイン**] ページで、確認するドメインの [**操作**] 列で、[**セットアップの開始**] を選択します。 
4. [ **Office へのドメインの追加 365** ] ページで、[**ステップ1を開始**する] を選択します。 
5. [**自分のドメインを所有**していることを確認します] ページで、[**この手順を実行するための**手順を参照してください] ドロップダウンリストで、[**一般的な手順**] を選択します。 
6. テーブルから、移動先またはポイントを [Address value] にコピーします。 次の手順で必要になります。 この値をコピーして貼り付けることをお勧めします。これにより、すべてのスペースが正しく保たれるようになります。

TXT レコードを追加します。 
-  ドメインの [DNS マネージャー] ページで、[**アクション** \> **テキスト (TXT)**] に移動します。 
-   [**新しいリソースレコード**] ダイアログボックスで、[**編集**] を選択します。  
-  [**新しいリソースレコード**] ダイアログボックスの [**ユーザー設定のホスト名**] 領域で、フィールドが正確に次の値に設定されていることを確認します。 

> [!IMPORTANT] 
> Windows DNS マネージャーの一部のバージョンでは、ドメインがセットアップされていて、txt レコードの作成時にホーム名が既定で親ドメインになっている場合があります。 このような場合、TXT レコードを追加するときに、@ またはドメイン名に設定するのではなく、ホスト名を空白 (値なし) に設定します。 

- ホスト名:@
- 型: TXT
- 住所: Office 365 からコピーしたばかりのアドレス値をコピー先またはポイントに貼り付けます。  
- [ **OK** > **完了**] を選択します。

Office 365 でドメインを確認します。  
> [!IMPORTANT]
> この操作を行う前に15分ほど待ってから、作成したレコードがインターネットを介して更新できるようにします。       

- Office 365 に戻り、次の手順に従って確認を要求します。 このチェックボックスでは、前の手順で追加した TXT レコードを探します。 正しい TXT レコードが見つかった場合、ドメインは確認されます。  
1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">ドメイン</a>の**セットアップ** \> ] ページに移動します。
2. [**ドメイン**] ページで、確認するドメインの [**処理**] 列で、[**セットアップの開始**] を選択します。 
3. [**自分のドメインを所有**していることを確認してください] ページで、[**完了]、[今すぐ確認**] の順に選択し、確認のダイアログボックスで [**完了**] を選択します。 
   
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  
## <a name="non-routable-email-address-used-as-a-upn-in-your-on-prem-active-directory"></a>オンプレミスの Active Directory で UPN として使用される、ルーティング不可能な電子メールアドレス
<a name="BKMK_ADNote"> </a>

オンプレミスの Active Directory を Office 365 と同期することを計画している場合は、Active Directory ユーザープリンシパル名 (UPN) サフィックスが有効なドメインサフィックスであることを確認し、@contoso など、サポートされていないドメインサフィックスではないことを確認する必要があります。 UPN サフィックスを変更する必要がある場合は、「[ディレクトリ同期のためにルーティング不能なドメインを準備する方法](https://support.office.com/article/e7968303-c234-46c4-b8b0-b5c93c6d57a7)」を参照してください。
  
> [!NOTE]
>  通常、DNS の変更が有効になるのに 15 分ほどかかります。 ただし、インターネットの DNS システム全体を更新する変更の場合、さらに長くかかることもあります。 DNS レコードの追加でメール フローなどに問題が発生した場合は、「[ドメイン名または DNS レコードの変更後の問題に関するトラブルシューティング](../get-help-with-domains/find-and-fix-issues.md)」を参照してください。 
  