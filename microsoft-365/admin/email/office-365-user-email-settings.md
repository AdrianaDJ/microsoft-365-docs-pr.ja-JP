---
title: Office 365 ユーザーのメール設定
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
ms.collection:
- Adm_O365
- Adm_TOC
localization_priority: Priority
ms.assetid: 03083fdf-bc52-409a-b2ac-2a5f5c308fa0
description: ここでは、ユーザーに対する設定を管理する方法について説明します。
ms.openlocfilehash: 7f79f90c9fe94596a5901d8ce9e6b31ba0af881e
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42255212"
---
# <a name="office-365-user-email-settings"></a><span data-ttu-id="2675b-103">Office 365 ユーザーのメール設定</span><span class="sxs-lookup"><span data-stu-id="2675b-103">Office 365 user email settings</span></span>

<span data-ttu-id="2675b-104">Office 365 組織の管理者は、ユーザーに対するメールの設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-104">As the admin of an Office 365 organization, there are email settings you can manage on your users.</span></span> <span data-ttu-id="2675b-105">ここでは、これらの設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2675b-105">This article gives you information on managing these settings.</span></span>

## <a name="summary-of-email-settings"></a><span data-ttu-id="2675b-106">メール設定の概要</span><span class="sxs-lookup"><span data-stu-id="2675b-106">Summary of email settings</span></span>

<span data-ttu-id="2675b-107">Office 365 のユーザーに対して変更できるさまざまなメール設定を以下の表に示します。</span><span class="sxs-lookup"><span data-stu-id="2675b-107">This table explains the various email settings you can change for a user in Office 365.</span></span>


|<span data-ttu-id="2675b-108">メール設定</span><span class="sxs-lookup"><span data-stu-id="2675b-108">Mail setting</span></span>|<span data-ttu-id="2675b-109">説明</span><span class="sxs-lookup"><span data-stu-id="2675b-109">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="2675b-110">メールボックスのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2675b-110">Mailbox permissions</span></span>| <span data-ttu-id="2675b-111">[**読み取りと管理**] では、ユーザーが他のユーザーのメールボックスを読み取り、管理できるかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-111">**Read and manage** allows you to set whether people can read and manage other people's mailboxes.</span></span> <span data-ttu-id="2675b-112">また、[**差出人を指定して送信する**] および [**代理人として送信する**] 権限をユーザーに設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2675b-112">You can also set **Send as** and **Send on behalf** permissions for a person.</span></span> <span data-ttu-id="2675b-113">詳細については、「[Office 365 の別のユーザーにメールボックス アクセス許可を付与する - 管理者ヘルプ](../add-users/give-mailbox-permissions-to-another-user.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2675b-113">Check out [Give mailbox permissions to another user in Office 365 - Admin Help](../add-users/give-mailbox-permissions-to-another-user.md) for more details.</span></span> |
|<span data-ttu-id="2675b-114">メール アプリ</span><span class="sxs-lookup"><span data-stu-id="2675b-114">Email apps</span></span>| <span data-ttu-id="2675b-115">[メール アプリ] では、ユーザーが Office 365 のメールにアクセスするために使用するアプリを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-115">Email apps allows you to choose the apps a user can use to access their Office 365 email.</span></span> |
|<span data-ttu-id="2675b-116">グローバル アドレス一覧に表示する</span><span class="sxs-lookup"><span data-stu-id="2675b-116">Show in global address list</span></span>| <span data-ttu-id="2675b-117">[グローバル アドレス一覧に表示する] では、組織のアドレス一覧でユーザーのメールボックスの表示を有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2675b-117">Show in global address list allows you to enable or disable the visibility of the user's mailbox in the organization's address list.</span></span> |
|<span data-ttu-id="2675b-118">メールの転送</span><span class="sxs-lookup"><span data-stu-id="2675b-118">Email forwarding</span></span>|<span data-ttu-id="2675b-119">[メールの転送] では、ユーザーに転送するメール アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-119">Email forwarding allows you to add a forwarding email address to a user.</span></span> <span data-ttu-id="2675b-120">この操作は、ユーザーが複数のメール アドレスを持っていて、そのすべてのメール アドレスでメールを受信する場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-120">You might want to do this if the person has multiple email addresses and they want to receive emails at all their email addresses.</span></span> <span data-ttu-id="2675b-121">詳細については、「[Office 365 でメールの転送を構成する](configure-email-forwarding.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2675b-121">Check out [Configure email forwarding in Office 365](configure-email-forwarding.md) for more details.</span></span>|
|<span data-ttu-id="2675b-122">自動応答</span><span class="sxs-lookup"><span data-stu-id="2675b-122">Automatic replies</span></span>|<span data-ttu-id="2675b-123">[自動応答] では、ユーザーのメール アドレスにメールが送信された場合の自動応答を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-123">Automatic replies allows you to set an automatic reply when someone sends an email to the person's email address.</span></span> <span data-ttu-id="2675b-124">この操作は、従業員が退職し、メールの送信者に知らせたい場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-124">You might want to do this if an employee leaves your company and you want to let the email sender know.</span></span>|
|<span data-ttu-id="2675b-125">その他の操作</span><span class="sxs-lookup"><span data-stu-id="2675b-125">More actions</span></span>| <span data-ttu-id="2675b-126">[**共有メールボックスに変換する**] では、ユーザーのメールボックスを共有メールボックスに変換することができます。</span><span class="sxs-lookup"><span data-stu-id="2675b-126">**Convert to shared mailbox** allows you to convert the user's mailbox to a shared mailbox.</span></span> <span data-ttu-id="2675b-127">この操作は、ユーザーが組織を退職し、しばらくの間そのユーザーのメールボックス データを維持したい場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-127">You might do this if the person leaves your organization and you want to keep their mailbox data around for a while.</span></span> <span data-ttu-id="2675b-128">「[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md)」および「[共有メールボックスを開いて使う](https://support.office.com/article/open-and-use-a-shared-mailbox-in-outlook-d94a8e9e-21f1-4240-808b-de9c9c088afd)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2675b-128">Check out [Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) and [Open and use a shared mailbox](https://support.office.com/article/open-and-use-a-shared-mailbox-in-outlook-d94a8e9e-21f1-4240-808b-de9c9c088afd).</span></span></br><span data-ttu-id="2675b-129">[**Exchange のプロパティの編集**] では、Exchange 管理センターを使用して追加の Exchange Online タスクを管理できます。</span><span class="sxs-lookup"><span data-stu-id="2675b-129">**Edit Exchange properties** allows you to manage additional Exchange Online tasks using the Exchange admin center.</span></span> <span data-ttu-id="2675b-130">「[Exchange Online でのユーザー メールボックスの管理](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2675b-130">Read about [managing user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span>|