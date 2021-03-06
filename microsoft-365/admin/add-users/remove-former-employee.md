---
title: 元従業員を削除する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'このチェックリストに従って、Microsoft 365 およびセキュリティで保護されたデータから従業員を削除します。 '
ms.openlocfilehash: e8f0b61fae3656b7d700857e3cc7167cc121a77f
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445521"
---
# <a name="remove-or-delete-a-former-employee"></a>元従業員を削除または削除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end
  
## <a name="sign-out-now"></a>今すぐサインアウトする

::: moniker range="o365-worldwide"

従業員の削除に関する短いビデオを見ることができます。 <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

従業員がログインできないようにするには、次のようにします。

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
2. ユーザー名の横にあるボックスを選択し、[ **パスワードのリセット**] を選択します。
3. 新しいパスワードを入力し、[ **リセット**] を選択します。 (送信しないでください)。
4. ユーザーの名前を選択して [プロパティ] ウィンドウに移動し、[ **アカウント** ] タブで [ **サインアウトの開始**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ユーザーを選択し、[ **パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[ **リセット**] を選択します。 (送信しないでください)。

4. ユーザーの名前を選択して [プロパティ] ウィンドウに移動し、[ **アカウント** ] タブで [ **サインアウトの開始**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ユーザーを選択し、[ **パスワードのリセット**] を選択します。

3. 新しいパスワードを入力し、[ **リセット**] を選択します。 (送信しないでください)。

4. ユーザーの名前を選択して [プロパティ] ウィンドウに移動し、[ **アカウント** ] タブで [ **サインアウトの開始**] を選択します。

::: moniker-end

> [!NOTE]
> サインアウトを開始するには、全体管理者である必要があります。

1時間以内に、または現在の Microsoft 365 ページから出た後、もう一度サインインするように求めるメッセージが表示されます。 アクセストークンは1時間にとって適切なので、タイムラインはそのトークンの残り時間と、現在の web ページから移動するかどうかによって決まります。
  
> [!IMPORTANT]
> ユーザーが Outlook on the web で、メールボックス内をクリックしただけでは、すぐに退出できない場合があります。 OneDrive などの別のタイルを選択するか、ブラウザーを更新するとすぐに、サインアウトが開始されます。
  
PowerShell を使用してユーザーをすぐにサインアウトさせるには、[Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) コマンドレットを参照してください。
  
ユーザーのメールの使用を終了するのにどれくらいかかるかの詳細については、「[従業員のメール セッションの終了について知っておく必要があること](#what-you-need-to-know-about-terminating-an-employees-email-session)」を参照してください。
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>従業員の削除とデータの保護を行うすべての手順の概要

「従業員が組織を離れたときにデータを保護するにはどうすればよいですか?」という質問がよくあります。 この記事では、Microsoft 365 へのアクセスをブロックする方法と、データを保護するために実行する必要のある手順について説明します。
  
> [!NOTE]
> グローバル管理者の場合は、従業員を削除し、電子メールを転送して、新しいガイド付きの操作を使用して OneDrive コンテンツに対する処理を選択することができます。 詳細については、「 [グローバル管理者: ユーザーを削除する](remove-former-employee.md)」を参照してください。 ただし、従業員が会社のデータにアクセスできないようにするには、ここに記載されている追加の手順をすべて完了することをお勧めします。 
  
簡単な概要を示します。各手順については、この記事で詳しく説明します。
  
|||
|:-----|:-----|
|**手順** <br/> |**理由** <br/> |
|1. [元従業員のメールボックスの内容を保存する](#save-the-contents-of-a-former-employees-mailbox) <br/> |これは、従業員の仕事を引き継ぐユーザー、または訴訟がある場合に役立ちます。  <br/> |
|2. [元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |この操作を行うと、元従業員のメール アドレスはアクティブなままとなります。顧客やパートナーが元従業員のアドレスにメールを引き続き送信する場合は、この手順を行うと、仕事を引き継ぐユーザーに転送されます。  <br/> |
|3. [元従業員のモバイル デバイスをワイプし、ブロックする](#wipe-and-block-a-former-employees-mobile-device) <br/> |携帯電話またはタブレットからビジネス データを削除します。  <br/> |
|4. [以前の従業員の Microsoft 365 データへのアクセスをブロックする](#block-a-former-employees-access-to-microsoft-365-data)<br/> |これにより、ユーザーは古い Microsoft 365 メールボックスおよびデータにアクセスできなくなります。  <br/><br/> **ヒント**: ユーザーのアクセスをブロックすると、ライセンスの支払いが続行されます。 その支払いを中止するには、サブスクリプションからライセンスを削除します (手順 5)。  |
|5. [従業員の OneDrive のコンテンツを移動する](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |ユーザーのライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/><br/> アカウントを削除する前に、OneDrive のコンテンツをアクセスしやすい別の場所に移動する必要があります。従業員のアカウントを削除すると、OneDrive のコンテンツは **30** 日間保持されます。その 30 日間であれば、ユーザーのアカウントを復元し、OneDrive のコンテンツにアクセスすることができます。ユーザーのアカウントを復元した場合、30 日後でも OneDrive のコンテンツにアクセスできます。  <br/> |
|5a. ユーザーが個人のコンピューターを使用して OneDrive や SharePoint にアクセスした場合はどうなりますか?  <br/> |ユーザーが、会社が発行したコンピューターではなく、個人のコンピューターを使用して OneDrive や SharePoint からファイルをダウンロードした場合は、保存されたそれらのファイルを削除する方法はありません。  <br/><br/> ユーザーは、コンピューターに同期されているすべてのファイルに引き続きアクセスできます。  <br/> |
|6.[以前の従業員から Microsoft 365 ライセンスを削除して削除し](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)ます。<br/> |ライセンスを削除すると、別のユーザーに割り当てることができます。または、他のユーザーを採用するまで支払うことがないように、ライセンスを削除することもできます。  <br/><br/> ライセンスを削除すると、ユーザーの古いメール、連絡先、および予定表は **30 日間** 保持され、その後、完全に削除されます。 ライセンスのみを削除し、アカウントを削除しない場合、ユーザーの OneDrive のコンテンツには 30 日後でもアクセスできます。  <br/> |
|7. [元従業員のユーザー アカウントを削除する](#delete-a-former-employees-user-account)<br/> |これにより、管理センターからアカウントが削除されます。 これできれいになります。  <br/> |

## <a name="save-the-contents-of-a-former-employees-mailbox"></a>元従業員のメールボックスの内容を保存する

元従業員のメールボックスの内容を保存するには、2 つの方法があります。
  
1. 使用しているバージョンの Outlook 2013 または 2016 に元従業員のメール アドレスを追加し, .pst ファイルにデータをエクスポートします。必要に応じて、別のメール アカウントにデータをインポートすることができます。方法については、「[元ユーザーのデータにアクセスしてバックアップを作成する](get-access-to-and-back-up-a-former-user-s-data.md)」を参照してください。

    または

2. ユーザー アカウントを削除する前に、メールボックスに訴訟ホールドまたはインプレース ホールドを配置します。これは 1 つ目のオプションよりも複雑ですが、企業計画にアーカイブと訴訟ホールドが含まれている場合、訴訟の可能性がある場合、および技術力の高い IT 部門がある場合は、行う価値があります。

    メールボックスを "非アクティブなメールボックス" に変換した後、管理者、コンプライアンス責任者、またはレコード管理者は、Exchange Online の In-Place 電子情報開示ツールを使用して、コンテンツにアクセスして検索できます。

    非アクティブなメールボックスはメールを受信することができず、組織の共有アドレス帳にもその他のリストにも表示されません。

    メールボックスにホールドを設定する方法については、「 [Exchange Online の非アクティブなメールボックスを管理](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)する」を参照してください。

## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>元従業員のメールを別の従業員に転送するか、または元従業員のメールボックスを共有メールボックスに変換する

この手順で、他の従業員に元従業員のメール アドレスを割り当てるか、または作成した[共有メールボックスにユーザーのメールボックスを変換します](../email/convert-user-mailbox-to-shared-mailbox.md)。
  
- 共有メールボックスを作成すると、コストを低く抑えることができます。これは、 **メールボックスのサイズが 50 GB より小さい限り** 、ライセンスの料金を支払う必要がないからです。50 GB を超えると、メールボックスにライセンスを割り当てる必要があります。
- メールボックスを共有メールボックスに変換すると、以前のすべてのメールを入手できるようになります。この処理を行うと、占有する領域が大きくなる可能性があります。
- メールの転送を設定した場合、元従業員宛の *新しい*  メールのみが、現在の従業員に送信されるようになります。

 > [!IMPORTANT]
 > メール転送または共有メールボックスを設定している場合は、最後に、元従業員のアカウントを削除しないでください。 メール転送や共有メールボックスを固定するには、アカウントを残しておく必要があります。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
2. 禁止する従業員の名前を選択し、[ **メール** ] タブを選択します。
3. [ **電子メールの転送**] で、[ **メール転送の管理**] を選択します。
4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。 [ **転送先アドレス** ] ボックスに、電子メールを取得する現在の従業員の電子メールアドレスを入力します。
5. [**保存**] を選択します。
6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ブロックする従業員を選択し、[メールの **設定**] を展開します。

3. [ **電子メール転送**] の横にある [ **編集**] を選択します。

4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。[ **転送先アドレス** ] ボックスに、メールを受け取る現在の従業員 (または共有メールボックス) のメール アドレスを入力します。
  
5. [**保存**] を選択します。

6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. ブロックする従業員を選択し、[メールの **設定**] を展開します。

3. [ **電子メール転送**] の横にある [ **編集**] を選択します。

4. [ **このメールボックスに送信されたすべてのメールを転送する** ] をオンにします。[ **転送先アドレス** ] ボックスに、メールを受け取る現在の従業員 (または共有メールボックス) のメール アドレスを入力します。
  
5. [**保存**] を選択します。

6. 元従業員のアカウントを削除しないよう注意してください。

::: moniker-end

## <a name="wipe-and-block-a-former-employees-mobile-device"></a>元従業員のモバイル デバイスをワイプし、ブロックする

以前の従業員が組織の電話を使用していた場合は、Exchange 管理センターを使用してそのデバイスをワイプしてブロックすると、すべての組織データがデバイスから削除され、Office 365 に接続できなくなります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.
3. ユーザーを選択し、[ **モバイルデバイス**] で [ **詳細の表示**] を選択します。
4. [**モバイルデバイスの詳細**] ページの [**モバイルデバイス**] で、モバイルデバイスを選択し、[データワイプデバイスの**ワイプ**] を選択して、[ ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) **ブロック**] を選択します。
5. [**保存**] を選択します。
   > [!TIP]
   > オンプレミスの Blackberry Enterprise サービスからユーザーを削除または無効にしてください。 さらに、そのユーザーのすべての Blackberry デバイスを無効にする必要もあります。 ユーザーを無効にする具体的な手順については、「Blackberry Business Cloud Services Administration Guide」 (Blackberry Business Cloud Services 管理ガイド) を参照してください。

## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>以前の従業員の Microsoft 365 データへのアクセスをブロックする

 > [!IMPORTANT]
 > アカウントをブロックすると、有効になるまで最大24時間かかる場合があります。 ユーザーのサインインアクセスをすぐに阻止する必要がある場合は、 [パスワードをリセット](reset-passwords.md) してから、すべてのデバイスで Microsoft 365 セッションからサインアウトするワンタイムイベントを開始する必要があります。 「[今すぐサインアウトする](#sign-out-now)」を参照してください。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
2. 禁止する従業員の名前を選択し、ユーザーの名前の下で [ **このユーザーをブロック**する] の記号を選択します。
3. [ **ユーザーによるサインインをブロックする**] を選択し、[ **保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[ **サインインをブロック**する] を選択します。

3. [ **ユーザーによるサインインをブロックする**] を選択し、[ **保存**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[ **サインインをブロック**する] を選択します。

3. [ **ユーザーによるサインインをブロックする**] を選択し、[ **保存**] を選択します。

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>元従業員の電子メール (Exchange Online) へのアクセスをブロックする

Microsoft 365 サブスクリプションの一部として電子メールを所有している場合は、次の手順に従って Exchange 管理センターにサインインし、元の従業員が自分のメールにアクセスできないようにする必要があります。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。
2. In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.
3. ユーザーをダブルクリックして、[ **メールボックスの機能** ] ページに移動します。 [ **モバイルデバイス**] で、[ **Exchange ActiveSync を無効** にし、 **デバイス用 OWA を無効** にする] を選択し、メッセージが表示されたら両方に **[はい]** と答えます。
4. メッセージが表示されたら、[ **電子メール接続**] で [ **無効に** する **]** を選択します。

## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>以前の従業員から Microsoft 365 ライセンスを削除して削除する

そのため、ユーザーが組織を離れた後にライセンスの支払いを続行しない場合は、Microsoft 365 ライセンスを削除してから、サブスクリプションから削除する必要があります。 サブスクリプションからライセンスを削除しない場合、そのライセンスを他のユーザーに割り当てることができます。
  
ライセンスの削除後、そのユーザーのすべてのデータが 30 日間保持されます。 データに[アクセス](get-access-to-and-back-up-a-former-user-s-data.md)したり、ユーザーが復帰した場合にアカウントを[復元](restore-user.md)したりすることができます。 30日後、ユーザーのすべてのデータ (SharePoint Online に保存されているドキュメントを除く) は、Microsoft 365 から完全に削除され、回復することはできません。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
2. 禁止する従業員の名前を選択し、[ **ライセンスとアプリ** ] タブを選択します。
3. 削除するライセンスのチェックボックスをオフにし、[ **変更の保存**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[ **製品ライセンス**] の横にある [ **編集**] を選択します。

3. [ **製品ライセンス** ] ページで、削除するライセンスを切り替えて、[ **保存**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 禁止する従業員を選択し、[ **製品ライセンス**] の横にある [ **編集**] を選択します。

3. [ **製品ライセンス** ] ページで、削除するライセンスを切り替えて、[ **保存**] を選択します。

::: moniker-end

他のユーザーを採用するまで**に支払うライセンスの数を減らすに**は、次の手順を実行します。

::: moniker range="o365-worldwide"
1. 管理センターで、[ **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">製品の</a>請求] ページに移動し、[**製品**] タブを選択します。
2. ライセンスを削除するサブスクリプションを選択します。
3. [詳細] ページで、[ **ライセンスの削除**] を選択します。
4. [ **ライセンスの削除** ] ウィンドウの [新しい数量] の下にある [ **ライセンスの合計** 数] ボックスに、このサブスクリプションで使用するライセンスの総数を入力します。 たとえば、25個のライセンスがあり、そのうちの1つを削除する場合は、「24」と入力します。
5. [**保存**] を選択します。
::: moniker-end

::: moniker range="o365-germany"
1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">[サブスクリプション]</a> ページに移動します。
2. 他のユーザーを採用するまで支払いないように、[ **ライセンスの追加/削除** ] を選択してライセンスを削除します。
::: moniker-end

::: moniker range="o365-21vianet"
1. 管理センターの **[課金]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">[サブスクリプション]</a> ページに移動します。
2. 他のユーザーを採用するまで支払いないように、[ **ライセンスの追加/削除** ] を選択してライセンスを削除します。
::: moniker-end

別の [ユーザー](add-users.md) をビジネスに追加すると、1つの手順でライセンスを同時に購入するように求めるメッセージが表示されます。

Microsoft 365 for business のユーザーライセンスの管理の詳細については、「365 Microsoft の一般法人向け [ユーザーへのライセンスの割り当て](../manage/assign-licenses-to-users.md)」および「一般 [法人向け365ユーザーからのライセンス](../manage/remove-licenses-from-users.md)の割り当て解除」を参照してください。
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>削除した従業員のアカウントが Skype for Business に与える影響

Office 365 からユーザーのライセンスを削除すると、ユーザーに関連付けられている PSTN 通話番号が解放されます。この番号を別のユーザーに割り当てることができます。
  
ユーザーがキュー グループに属している場合、ユーザーは呼び出しキューのエージェントの実行可能な対象にならなくなります。そのため、呼び出しキューに関連付けられているグループからもユーザーを削除することをお勧めします。

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>組織内のユーザーへの着信転送をセットアップする

解雇された従業員の電話番号の着信転送を設定する必要がある場合は、通話ポリシーの [着信の転送] 設定を使用して、着信通話を他のユーザーに転送したり、他のユーザーを同時に呼び出したりすることができる転送をセットアップできます。 詳細については、「 [Microsoft Teams の通話ポリシー](https://docs.microsoft.com/microsoftteams/teams-calling-policy)」を参照してください。
  
## <a name="delete-a-former-employees-user-account"></a>元従業員のユーザー アカウントを削除する

元従業員のすべてのユーザー データにアクセスして保存したら、元従業員のアカウントを削除できます。
  
メールの転送を設定した場合や、アカウントを共有メールボックスに変換した場合、アカウントを削除しないでください。いずれの場合も、メール転送および共有メールボックスを固定するには、アカウントが必要です。

::: moniker range="o365-worldwide"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。
2. 削除する従業員の名前を選択します。
3. ユーザー名の下で、[ **ユーザーの削除**] の記号を選択します。 このユーザーに対して必要なオプションを選択し、[ **ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの **削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[ **ユーザーの削除**] を選択します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。

2. 削除する従業員の名前を選択します。

3. ページの上部で、[ユーザーの **削除**] を選択します。 このユーザーに対して必要なオプションを選択し、[ **ユーザーの削除**] を選択します。

::: moniker-end

ユーザーを削除するとき、約 30 日間アカウントが無効になります。30 日後に永久に削除されるまではアカウントを復元できます。
  
### <a name="does-your-organization-use-active-directory"></a>組織では Active Directory を使用していますか。

ローカル Active Directory 環境からユーザーアカウントを Microsoft 365 に同期させる場合は、ローカルの Active Directory サービスでユーザーアカウントを削除および復元する必要があります。 ユーザー アカウントを Office 365 で削除または復元することはできません。
  
Active Directory でユーザーアカウントを削除および復元する方法については、「 [ユーザーアカウントを削除](https://go.microsoft.com/fwlink/?linkid=841808)する」を参照してください。
  
Azure Active Directory を使用している場合は、 [Get-msoluser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell コマンドレットを参照してください。
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>従業員のメール セッションの終了について知っておく必要があること

ここでは、従業員のメールの使用を終了する方法について説明します (Exchange)。
  
|||
|:-----|:-----|
|**可能な操作** <br/> |**方法** <br/> |
|セッション (Outlook on the web、Outlook、Exchange Active Sync など) を終了し、新しいセッションを強制的に開く  <br/> |パスワードを再設定する  <br/> |
|(すべてのプロトコルの) セッションを終了し、今後のセッションに対するアクセスをブロックする  <br/> |アカウントを無効にする。 たとえば、(Exchange 管理センターまたは PowerShell を使用して) 次のように入力します。  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|特定のプロトコル (ActiveSync など) のセッションを終了する  <br/> |プロトコルを無効にする。 たとえば、(Exchange 管理センターまたは PowerShell を使用して) 次のように入力します。  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

上記の操作は、次の3つの場所で行うことができます。
  
|||
|:-----|:-----|
|**セッションを終了する場所** <br/> |**所要時間** <br/> |
|Exchange 管理センターまたは PowerShell を使用する場合  <br/> |予想される遅延が 30 分以内  <br/> |
|Azure Active Directory 管理センター  <br/> |予想される遅延が 60 分以内  <br/> |
|オンプレミス環境  <br/> |予想される遅延が 3 時間以上  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>アカウントの終了に対して最も迅速な応答を取得する方法

 **最も迅速な応答**: Exchange 管理センターを使用 (PowerShell を使用) するか、または Azure Active Directory 管理センターを使用します。オンプレミスの環境では、DirSync を介して変更を同期するのに数時間かかる場合があります。
  
 **オンプレミスおよび Exchange データ センターにプレゼンスがあるユーザーの場合、迅速な応答**: Azure Active Directory 管理センター/Exchange 管理センターを使用してセッションを終了し、オンプレミスの環境でも変更を加えます。そうしないと、Azure Active Directory 管理センター/Exchange 管理センターでの変更は、DirSync によって上書きされます。
  
## <a name="related-articles"></a>関連記事

[ユーザーを復元する](restore-user.md)
