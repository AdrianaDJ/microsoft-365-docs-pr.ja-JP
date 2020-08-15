---
title: Office 365 DoD の DNS レコード
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: '概要: Office 365 DoD の DNS レコード'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691835"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="e50e1-103">Office 365 DoD の DNS レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="e50e1-104">*この記事は、Office 365 DoD および Microsoft 365 DoD に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="e50e1-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="e50e1-105">Office 365 DoD へのオンボードの一部として、SMTP および SIP ドメインをオンラインサービステナントに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e50e1-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="e50e1-106">これを行うには、Azure AD PowerShell で Get-msoldomain コマンドレットを使用するか、 [Azure Government ポータル](https://portal.azure.us) を使用してドメインを追加し、所有権を証明するプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e50e1-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="e50e1-107">ドメインをテナントに追加して検証したら、次のガイダンスを使用して、以下のサービスに適切な DNS レコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="e50e1-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="e50e1-108">次の表は、組織のニーズに合わせて変更する必要があります。これには、受信 MX レコードおよびその場で既存の Exchange 自動検出レコードに関する要件があります。</span><span class="sxs-lookup"><span data-stu-id="e50e1-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="e50e1-109">このような DNS レコードをメッセージングチームと調整して、電子メールの停止や不適切な配信を回避することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e50e1-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="e50e1-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e50e1-110">Exchange Online</span></span>

| <span data-ttu-id="e50e1-111">Type</span><span class="sxs-lookup"><span data-stu-id="e50e1-111">Type</span></span> | <span data-ttu-id="e50e1-112">Priority</span><span class="sxs-lookup"><span data-stu-id="e50e1-112">Priority</span></span> | <span data-ttu-id="e50e1-113">ホスト名</span><span class="sxs-lookup"><span data-stu-id="e50e1-113">Host name</span></span> | <span data-ttu-id="e50e1-114">ポイント (アドレスまたは値)</span><span class="sxs-lookup"><span data-stu-id="e50e1-114">Points to address or value</span></span> | <span data-ttu-id="e50e1-115">TTL</span><span class="sxs-lookup"><span data-stu-id="e50e1-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="e50e1-116">MX</span><span class="sxs-lookup"><span data-stu-id="e50e1-116">MX</span></span> | <span data-ttu-id="e50e1-117">.0</span><span class="sxs-lookup"><span data-stu-id="e50e1-117">0</span></span> | @ | <span data-ttu-id="e50e1-118">*tenant*mail.protection.office365.us (詳細については、以下を参照してください)</span><span class="sxs-lookup"><span data-stu-id="e50e1-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="e50e1-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-119">1 Hour</span></span> |
| <span data-ttu-id="e50e1-120">TXT</span><span class="sxs-lookup"><span data-stu-id="e50e1-120">TXT</span></span> | - | @ | <span data-ttu-id="e50e1-121">v = spf1 には、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e50e1-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="e50e1-122">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-122">1 Hour</span></span> |
| <span data-ttu-id="e50e1-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="e50e1-123">CNAME</span></span> | - | <span data-ttu-id="e50e1-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="e50e1-124">autodiscover</span></span> | <span data-ttu-id="e50e1-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="e50e1-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="e50e1-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="e50e1-127">Exchange 自動検出レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="e50e1-128">オンプレミスの Exchange Server を使用している場合は、Exchange Online に移行するときに既存のレコードをそのままにしておき、移行の完了後にそのレコードを更新することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e50e1-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="e50e1-129">Exchange Online MX レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-129">Exchange Online MX Record</span></span>

<span data-ttu-id="e50e1-130">承認済みドメインの MX レコード値は、前述したように、mail.protection.office365.us を使用して既定のテナント名の最初の部分に*テナント*を置き換えて、標準形式に*従います。*</span><span class="sxs-lookup"><span data-stu-id="e50e1-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="e50e1-131">たとえば、テナント名が contoso.onmicrosoft.us の場合は、MX レコードの値として **contoso.mail.protection.office365.us** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e50e1-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="e50e1-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e50e1-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="e50e1-133">CNAME レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-133">CNAME records</span></span>

| <span data-ttu-id="e50e1-134">型</span><span class="sxs-lookup"><span data-stu-id="e50e1-134">Type</span></span> | <span data-ttu-id="e50e1-135">ホスト名</span><span class="sxs-lookup"><span data-stu-id="e50e1-135">Host name</span></span> | <span data-ttu-id="e50e1-136">ポイント (アドレスまたは値)</span><span class="sxs-lookup"><span data-stu-id="e50e1-136">Points to address or value</span></span> | <span data-ttu-id="e50e1-137">TTL</span><span class="sxs-lookup"><span data-stu-id="e50e1-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="e50e1-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="e50e1-138">CNAME</span></span> | <span data-ttu-id="e50e1-139">sip</span><span class="sxs-lookup"><span data-stu-id="e50e1-139">sip</span></span> | <span data-ttu-id="e50e1-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="e50e1-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="e50e1-141">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-141">1 Hour</span></span> |
| <span data-ttu-id="e50e1-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="e50e1-142">CNAME</span></span> | <span data-ttu-id="e50e1-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="e50e1-143">lyncdiscover</span></span> | <span data-ttu-id="e50e1-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="e50e1-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="e50e1-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="e50e1-146">SRV レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-146">SRV records</span></span>

| <span data-ttu-id="e50e1-147">型</span><span class="sxs-lookup"><span data-stu-id="e50e1-147">Type</span></span> | <span data-ttu-id="e50e1-148">サービス</span><span class="sxs-lookup"><span data-stu-id="e50e1-148">Service</span></span> | <span data-ttu-id="e50e1-149">プロトコル</span><span class="sxs-lookup"><span data-stu-id="e50e1-149">Protocol</span></span> | <span data-ttu-id="e50e1-150">ポート</span><span class="sxs-lookup"><span data-stu-id="e50e1-150">Port</span></span> | <span data-ttu-id="e50e1-151">太さ</span><span class="sxs-lookup"><span data-stu-id="e50e1-151">Weight</span></span> | <span data-ttu-id="e50e1-152">優先度</span><span class="sxs-lookup"><span data-stu-id="e50e1-152">Priority</span></span> | <span data-ttu-id="e50e1-153">Name</span><span class="sxs-lookup"><span data-stu-id="e50e1-153">Name</span></span> | <span data-ttu-id="e50e1-154">Target</span><span class="sxs-lookup"><span data-stu-id="e50e1-154">Target</span></span> | <span data-ttu-id="e50e1-155">TTL</span><span class="sxs-lookup"><span data-stu-id="e50e1-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="e50e1-156">SRV</span><span class="sxs-lookup"><span data-stu-id="e50e1-156">SRV</span></span> | <span data-ttu-id="e50e1-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="e50e1-157">\_sip</span></span> | <span data-ttu-id="e50e1-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="e50e1-158">\_tls</span></span> | <span data-ttu-id="e50e1-159">443</span><span class="sxs-lookup"><span data-stu-id="e50e1-159">443</span></span> | <span data-ttu-id="e50e1-160">1-d</span><span class="sxs-lookup"><span data-stu-id="e50e1-160">1</span></span> | <span data-ttu-id="e50e1-161">100</span><span class="sxs-lookup"><span data-stu-id="e50e1-161">100</span></span> | @ | <span data-ttu-id="e50e1-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="e50e1-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="e50e1-163">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-163">1 Hour</span></span> |
| <span data-ttu-id="e50e1-164">SRV</span><span class="sxs-lookup"><span data-stu-id="e50e1-164">SRV</span></span> | <span data-ttu-id="e50e1-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="e50e1-165">\_sipfederationtls</span></span> | <span data-ttu-id="e50e1-166">\_プロトコル</span><span class="sxs-lookup"><span data-stu-id="e50e1-166">\_tcp</span></span> | <span data-ttu-id="e50e1-167">5061</span><span class="sxs-lookup"><span data-stu-id="e50e1-167">5061</span></span> | <span data-ttu-id="e50e1-168">1-d</span><span class="sxs-lookup"><span data-stu-id="e50e1-168">1</span></span> | <span data-ttu-id="e50e1-169">100</span><span class="sxs-lookup"><span data-stu-id="e50e1-169">100</span></span> | @ | <span data-ttu-id="e50e1-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="e50e1-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="e50e1-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="e50e1-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="e50e1-172">追加の DNS レコード</span><span class="sxs-lookup"><span data-stu-id="e50e1-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e50e1-173">DNS ゾーンに既存の *msoid* CNAME レコードがある場合は、この時点でそのレコードを dns から **削除** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e50e1-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="e50e1-174">Msoid レコードは Microsoft 365 Enterprise Apps *(旧称 Office 365 ProPlus)* と互換性がありません。また、ライセンス認証が成功することはありません。</span><span class="sxs-lookup"><span data-stu-id="e50e1-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>