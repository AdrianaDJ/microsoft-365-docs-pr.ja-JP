---
title: Microsoft 365 グループのメンバーを追加または削除する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Microsoft 365 管理センターで、グループにメンバーを追加したり、グループからメンバーを削除したり、グループ所有者の状態を管理したりする方法について説明します。
ms.openlocfilehash: a8739b6cd2005598acbfccbaff6131235ec480ee
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753315"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>管理センターを使用して Microsoft 365 グループのメンバーを追加または削除する

Microsoft 365 では、グループメンバーは通常、自分のグループを作成し、参加するグループに自らを追加するか、グループ所有者に招待します。 グループの所有権が変更された場合、またはメンバーを追加または削除することを決定した場合は、管理者としてその変更を行うこともできます。 これらの変更を行うことができるのは、グローバル管理者、Exchange 管理者、グループ管理者、またはユーザー管理者のみです。 [Microsoft 365 グループとは](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 管理者でない場合は、 [Outlook を使用してメンバーを追加または削除](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)できます。
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>管理センターでグループにメンバーを追加する

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。  

2. グループ名を選択します。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべて表示**] を選択し、[メンバーの **追加**] を選択して、[メンバーの追加] を選択します。

4. 追加するメンバーの名前を検索するか選択します。

5. **[保存]** を選択します。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>管理センターでメンバーにグループを追加する

1. 管理センターで、**[ユーザー]** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">[アクティブなユーザー]</a> ページの順に移動します。  

2. ユーザーを選択します。

3. 詳細ウィンドウの [ **アカウント** ] タブで、[ **グループの管理**] を選択します。

4. 追加するグループの名前を検索または選択します。

5. **[保存]** を選択します。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>管理センターでグループからメンバーを削除する

> [!NOTE]
> プライベート グループからメンバーを削除すると、そのユーザーがグループからブロックされるまで 5 分かかります (メンバーシップの変更がドメイン コントローラーで完全に複製された後になります)。

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

2. グループ名を選択します。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[ **すべて表示**] を選択し、メンバーを管理します。

4. 削除するメンバーの横にある [X] を選択します。

5. [ **保存** ] を選択して、メンバーを削除します。

## <a name="manage-group-owner-status"></a>グループの所有者の状態を管理する

既定では、グループを作成したユーザーが、グループの所有者になります。多くの場合、グループには、バックアップ サポートやその他の理由のために複数の所有者がいます。メンバーを所有者ステータスに昇格させたり、所有者をメンバー ステータスに降格させたりすることができます。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>管理センターでメンバーを所有者の状態に昇格させる

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

2. グループ名を選択します。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[すべて表示] を選択し、 **所有者を管理**します。

4. メンバーを検索するか、[ **所有者の追加**] を選択します。

5. 追加するメンバーの名前の横にあるチェックボックスをオンにします。

6. [ **保存**] を選択して、を **閉じ**ます。

### <a name="remove-owner-status-in-the-admin-center"></a>管理センターで所有者の状態を削除する

1. 管理センターで、[**グループ**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">グループ</a>] ページの順に移動します。

2. グループ名を選択します。

3. 詳細ウィンドウの [ **メンバー** ] タブで、[すべて表示] を選択し、 **所有者を管理**します。

4. 所有者の名前の横にある [X] を選択します。

5. **[保存]** を選択します。

## <a name="more-on-managing-membership"></a>メンバーシップの管理に関する詳細

- [Azure Active Directory におけるグループの管理](https://go.microsoft.com/fwlink/?linkid=847632): 「グループのメンバーシップを動的に管理する方法」セクションを参照してください。

- 数百から数千のユーザーをグループに追加するには、 [UnifiedGroupLinks](https://go.microsoft.com/fwlink/p/?LinkId=616191)を使用します。

- [孤立グループに新しい所有者を割り当てる](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>グループの管理に関する記事

- [Outlook で配布リストを Microsoft 365 グループにアップグレードする](../manage/upgrade-distribution-lists.md)

- [Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Microsoft 365 グループでゲストアクセスを管理する](manage-guest-access-in-groups.md)

- [PowerShell を使用して Microsoft 365 グループを管理](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)する: この記事では、主要なコマンドレットについて説明し、例を示します。

- [Microsoft 365 グループの名前付けポリシー](groups-naming-policy.md)