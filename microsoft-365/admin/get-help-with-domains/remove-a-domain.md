---
title: ドメインを削除する
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
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Microsoft 365 から古いドメインを削除し、ユーザーとグループを別のドメインに移動する方法について説明します。
ms.openlocfilehash: 4eb44914daf500ac48f140bd999a2cf783a9bf83
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645289"
---
# <a name="remove-a-domain"></a>ドメインを削除する

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end
  
 探している内容が見つからない場合は、**[ドメインに関する FAQ を確認Q](../setup/domains-faq.md)** を参照してください。 
  
別の Microsoft 365 サブスクリプションプランに追加する必要があるため、ドメインを削除していますか? それとも、サブスクリプションをキャンセルするためですか? [プランやサブスクリプションを変更する](../../commerce/subscriptions/switch-to-a-different-plan.md)ことも、[サブスクリプションをキャンセル](../../commerce/subscriptions/cancel-your-subscription.md)することもできます。
  
### <a name="step-1-move-users-to-another-domain"></a>手順 1: ユーザーを別のドメインに移動する

#### <a name="move-users"></a>ユーザーを移動する

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理センター</a>にアクセスします。

2. [ **ユーザー** > の **アクティブなユーザー**] を選択します。

3. 移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。

4. ページの上部にある [ **その他のオプション** (**...**)] を選択し、[ **ドメインの変更**] を選択します。

5. [ **ドメインの変更** ] ウィンドウで、別のドメインを選択します。

削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>にアクセスします。  

2. [ **ユーザー** > の **アクティブなユーザー**] を選択します。

3. 移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。

4. ページの上部で、[**その他**のドメインの編集] を選択し > **Edit domains**ます。

5. [ **ドメインの編集** ] ウィンドウで、別のドメインを選択します。
  
削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。  

2. [ **ユーザー** > の **アクティブなユーザー**] を選択します。

3. 移動するすべてのユーザーの名前の横にあるチェックボックスをオンにします。

4. ページの上部で、[**その他**のドメインの編集] を選択し > **Edit domains**ます。

5. [ **ドメインの編集** ] ウィンドウで、別のドメインを選択します。
  
削除するドメインを自分も使っている場合は、自分自身についてもこの操作を行う必要があります。自分のアカウントのドメインを編集する場合は、いったんログアウトし、選んだ新しいドメインでログインし直して、続ける必要があります。

::: moniker-end

#### <a name="move-yourself"></a>自分を移動する

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>にアクセスします。

2. [ **ユーザー** \> の **アクティブなユーザー**] に移動し、一覧から自分のアカウントを選択します。

3. [ **アカウント** ] タブで、[ **ユーザー名の管理**] を選択し、別のドメインを選択します。
  
4. 上部で、自分のアカウント名を選択し、[ **サインアウト**] を選択します。

5. 新しいドメインと同じパスワードを使用してサインインします。

また、PowerShell を使用してユーザーを別のドメインに移動することもできます。 詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。 既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。

::: moniker-end

::: moniker range="o365-germany"

1. [ **ユーザー** \> の **アクティブなユーザー**] に移動し、リストで自分の名前を選択します。

2. [ **ユーザー名/電子メール** ] セクションで、[ **編集**] を選択し、別のドメインを選択します。

3. [**プライマリの保存として設定**] を選択し > **Save** > **Close**ます。
  
4. 上部で、自分のアカウント名を選択し、[ **サインアウト**] を選択します。

5. 新しいドメインと同じパスワードを使用してサインインします。

また、PowerShell を使用してユーザーを別のドメインに移動することもできます。 詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。 既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。

::: moniker-end

::: moniker range="o365-21vianet"

1. [ **ユーザー** \> の **アクティブなユーザー**] に移動し、リストで自分の名前を選択します。

2. [ **ユーザー名/電子メール** ] セクションで、[ **編集**] を選択し、別のドメインを選択します。

3. [**プライマリの保存として設定**] を選択し > **Save** > **Close**ます。
  
4. 上部で、自分のアカウント名を選択し、[ **サインアウト**] を選択します。

5. 新しいドメインと同じパスワードを使用してサインインします。

また、PowerShell を使用してユーザーを別のドメインに移動することもできます。 詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。 既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>手順 2: グループを別のドメインに移動する

::: moniker range="o365-worldwide"

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。
  
2. グループ名を選択し、[**電子メールアドレス, プライマリ**] の [**全般**] タブで [**編集**] を選択します。

3. ドロップダウンリストを使用して、別のドメインを選択します。

4. [**保存**]、[**閉じる**] の順に選びます。 削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。

2. グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。

3. ドロップダウンリストを使用して、別のドメインを選択します。

4. [**保存**]、[**閉じる**] の順に選びます。 削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理センター</a>で、[**グループ** > **グループ**] ページに移動します。

2. グループ名を選択し、[**名前**] の横にある [**編集**] を選択します。

3. ドロップダウンリストを使用して、別のドメインを選択します。

4. [**保存**]、[**閉じる**] の順に選びます。 削除するドメインに関連付けられているすべてのグループまたは配布リストについて、この処理を繰り返します。

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>手順 3: 古いドメインを削除する

::: moniker range="o365-worldwide"

1. 管理センターで、**[設定]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">[ドメイン]</a> ページの順に移動します。

::: moniker-end

::: moniker range="o365-germany"

1. 管理センターで、[ドメインの**セットアップ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> ] ページに移動します。

::: moniker-end

::: moniker range="o365-21vianet"

1. 管理センターで、[ドメインの**セットアップ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> ] ページに移動します。

::: moniker-end
  
2. [ **ドメイン** ] ページで、削除するドメインを選択します。

3. 右側のウィンドウで、[ **削除**] を選択します。

4. その他のプロンプトに従って、[ **閉じる**] を選択します。

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>ドメインが削除されるまで、どれくらいかかりますか?

Microsoft 365 では、セキュリティグループ、配布リスト、ユーザー、Microsoft 365 グループなどの多くの場所で参照されていない場合、ドメインを削除するのには5分ほどかかる場合があります。 ドメインを使用する参照が多い場合、ドメインが削除されるまでに数時間 (1 日) 程度かかることもあります。
  
数百から数千のユーザーがいる場合は、PowerShell を使用してすべてのユーザーに対するクエリを実行してから、別のドメインに移動してください。これを行わないと、一部のユーザーが UI に表示されない可能性があり、ドメインを削除しようとしてもなぜか失敗します。詳細については、「[Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0)」を参照してください。既定のドメインを設定するには、[Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) を使用します。
  
## <a name="still-need-help"></a>さらにヘルプが必要ですか?

::: moniker range="o365-worldwide"

> [!NOTE]
> アカウントから [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) ドメインを削除することはできません。
  
それでもうまくいかない場合、ドメインを手動で削除する必要があります。[ご連絡いただければ](../contact-support-for-business-products.md)、お手伝いいたします。
  
::: moniker-end

## <a name="related-articles"></a>関連記事

[ドメイン FAQ](../setup/domains-faq.md)

[別の Microsoft 365 for business プランに切り替える](../../commerce/subscriptions/switch-to-a-different-plan.md)

[サブスクリプションをキャンセルする](../../commerce/subscriptions/cancel-your-subscription.md)
