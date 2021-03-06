---
title: グループを比較する
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: 使用可能なグループの種類について説明します。
ms.openlocfilehash: ee8d14035ed9eb8296c54510b8fe1d374c9dc2b2
ms.sourcegitcommit: f3a02584c9354a46c082f8f948b34a177adf65bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "46514769"
---
# <a name="compare-groups"></a>グループを比較する

Microsoft 365 管理センターの [ **グループ**] セクションでは、次の種類のグループを作成および管理できます。 

- **Microsoft 365 グループ** (旧称 Office 365 グループ) は、会社の内外のユーザー間での共同作業に使用されます。
- **配布グループ**は、ユーザーのグループに通知を送信するのに使用されます。
- **セキュリティ グループ**は、SharePoint サイトなどのリソースへのアクセスを許可するために使用されます。
- **メールが有効なセキュリティ グループ**は、SharePoint などのリソースへのアクセスを許可し、それらのユーザーにメールで通知を送信するために使用されます。
- **共有メールボックス**は、会社情報やサポート メール アドレスなど、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

## <a name="microsoft-365-groups"></a>Microsoft 365 グループ

Microsoft 365 グループは、社内外のユーザー間での共同作業に使用されます。 各 Microsoft 365 グループでは、メンバーは会話用のグループ メールおよび共有ワークスペース、ファイル、カレンダー イベント、Planner を利用できます。

[管理者によって有効にされている](manage-guest-access-in-groups.md)限り、組織の外部のユーザーをグループに追加できます。 外部の送信者がグループのメール アドレスにメールを送信できるようにすることもできます。

Microsoft 365 グループは [Azure Active Directory の動的メンバーシップ用に構成でき](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性に基づいてグループ メンバーを自動的に追加または削除できます。

Microsoft 365 グループには、Outlook for iOS や Outlook for Android などのモバイル アプリからアクセスできます。

グループ メンバーは、[管理者によって有効にされている](allow-members-to-send-as-or-send-on-behalf-of-group.md)場合、グループのメール アドレスとして送信したり、グループのメール アドレスの代わりに送信したりできます。

## <a name="distribution-groups"></a>配布グループ

[配布グループ](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)は、ユーザーのグループに通知を送信するのに使用されます。 管理者によって有効にされている場合、外部メールを受信できます。

配布グループは、"建物 A のユーザー" や "Contoso の全員" など、一連のユーザーに情報をブロードキャストする必要がある状況に最適です。

配布グループは、[Microsoft 365 グループ](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)にアップグレードできます。

## <a name="security-groups"></a>セキュリティ グループ

[セキュリティ グループ](../email/create-edit-or-delete-a-security-group.md)は、SharePoint などの Microsoft 365 リソースへのアクセスを許可するために使用されます。 ユーザーを各リソースに個別に追加するのではなく、グループを管理するだけで済むため、管理が容易になります。

セキュリティ グループには、ユーザーまたはデバイスを含めることができます。 デバイス用のセキュリティ グループの作成は、Intune などのモバイル デバイス管理サービスで使用できます。

セキュリティ グループは [Azure Active Directory の動的メンバーシップ用に構成でき](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)、部署、場所、役職などのユーザー属性、またはオペレーティング システムのバージョンなどのデバイス属性に基づいてグループ メンバーまたはデバイスを自動的に追加または削除できます。

## <a name="mail-enabled-security-groups"></a>メールが有効なセキュリティ グループ

メールが有効なセキュリティ グループは通常のセキュリティ グループと同じように機能しますが、Azure Active Directory で動的に管理できず、デバイスを含めることができません。

グループのすべてのメンバーにメールを送信する機能が含まれます。

## <a name="shared-mailboxes"></a>共有メールボックス

[共有メールボックス](../email/create-a-shared-mailbox.md)は、会社情報やサポート メール アドレス、受付デスク、または複数のユーザーが共有する可能性のあるその他の機能など、複数のユーザーが同じメールボックスにアクセスする必要がある場合に使用されます。

管理者が有効にしている場合、共有メールボックスは外部メールを受信できます。

グループ メールボックスへのアクセス許可を持つユーザーは、管理者がそのユーザーに対して必要なアクセス許可を付与している場合、メールボックスのメール アドレスとして送信したり、メールボックスのメール アドレスの代わりに送信したりできます。 これは、ユーザーが "Contoso サポート" や "建物 A の受付デスク" からメールを送信できるため、ヘルプとサポートのメールボックスとして特に役立ちます。

現在、共有メールボックスを Microsoft 365 グループに移行することはできません。 これはあなたが必要とするものでしたか ? ご意見やご要望をお待ちしております。 **[ここで投票してください](https://go.microsoft.com/fwlink/?linkid=871518)**。

## <a name="related-articles"></a>関連記事

[Microsoft 365 グループについて](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Outlook で配布リストをグループにアップグレードする理由](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
