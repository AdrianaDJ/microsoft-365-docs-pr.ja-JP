---
title: Office 365 のネットワークと移行の計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: この記事には、ネットワークの計画、テスト、Office 365 への移行に関する情報へのリンクが含まれています。
ms.openlocfilehash: 1e6973f93c65012f4ca007332a47cc6b9e67b3b0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692177"
---
# <a name="network-and-migration-planning-for-office-365"></a><span data-ttu-id="231a2-103">Office 365 のネットワークと移行の計画</span><span class="sxs-lookup"><span data-stu-id="231a2-103">Network and migration planning for Office 365</span></span>

<span data-ttu-id="231a2-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="231a2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="231a2-105">この記事には、ネットワークの計画とテスト、および Office 365 への移行に関する情報へのリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="231a2-105">This article contains links to information about network planning and testing, and migration to Office 365.</span></span>
  
<span data-ttu-id="231a2-106">Office 365 に初めて展開するか、Office に移行する前に、これらのトピックの情報を使用して必要な帯域幅を推定し、Office 365 に展開または移行するのに十分な帯域幅があるかどうかをテストして確認することができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-106">Before you deploy for the first time or migrate to Office 365, you can use the information in these topics to estimate the bandwidth you need and then to test and verify that you have enough bandwidth to deploy or migrate to Office 365.</span></span>

<span data-ttu-id="231a2-107">この記事は [、Office 365 のネットワーク計画とパフォーマンスチューニング](https://aka.ms/tune)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="231a2-107">This article is part of [Network planning and performance tuning for Office 365](https://aka.ms/tune).</span></span>

<span data-ttu-id="231a2-108">Microsoft 365 およびその他の Microsoft クラウドプラットフォームおよびサービスに対してネットワークを最適化するための手順については、「 [エンタープライズアーキテクトのための Microsoft クラウドネットワーク](https://aka.ms/cloudarchnetworking) 」のポスターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-108">For the steps to optimize your network for Microsoft 365 and other Microsoft cloud platforms and services, see the [Microsoft Cloud Networking for Enterprise Architects](https://aka.ms/cloudarchnetworking) poster.</span></span>
   
## <a name="estimate-network-bandwidth-requirements"></a><span data-ttu-id="231a2-109">ネットワーク帯域幅の要件を見積もる</span><span class="sxs-lookup"><span data-stu-id="231a2-109">Estimate network bandwidth requirements</span></span>
<span data-ttu-id="231a2-110"><a name="EstimateBandwidthRequirements"> </a></span><span class="sxs-lookup"><span data-stu-id="231a2-110"><a name="EstimateBandwidthRequirements"> </a></span></span>

<span data-ttu-id="231a2-111">Office 365 を使用すると、組織のインターネット回線の使用率が向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="231a2-111">Using Office 365 may increase the utilization of your organization's internet circuit.</span></span> <span data-ttu-id="231a2-112">Office 365 が完全に展開され、少なくとも20% の容量を維持している間に、使用可能な帯域幅の量が増加しているかどうかを判断することが重要です。</span><span class="sxs-lookup"><span data-stu-id="231a2-112">It's important to determine if the amount of bandwidth currently available is enough to handle the estimated increase once Office 365 is fully deployed while leaving at least 20% capacity to handle the busiest of days.</span></span>
  
<span data-ttu-id="231a2-113">帯域幅を推定するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="231a2-113">To estimate the bandwidth, use the following steps:</span></span>
  
1. <span data-ttu-id="231a2-114">各インターネット出口を使用するクライアントの数を評価します。</span><span class="sxs-lookup"><span data-stu-id="231a2-114">Assess the number of clients that will use each Internet egress.</span></span> <span data-ttu-id="231a2-115">Terabit ネットワークが可能な限り多くの接続を処理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="231a2-115">Let our multi-terabit network handle as much of the connection as possible.</span></span> 
    
2. <span data-ttu-id="231a2-116">クライアントが使用できる Office 365 サービスと機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-116">Determine which Office 365 services and features will be available for clients to use.</span></span> <span data-ttu-id="231a2-117">さまざまなサービスや利用状況のプロファイルを持つユーザーのグループが存在する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="231a2-117">You will likely have groups of people with different services or usage profiles.</span></span>
    
3. <span data-ttu-id="231a2-118">クライアントのパイロットグループに対するネットワークの使用を測定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-118">Measure the network use for a pilot group of clients.</span></span> <span data-ttu-id="231a2-119">パイロットクライアントが、組織内のユーザーのさまざまなプロファイルおよび地理的に異なる場所を代表するものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="231a2-119">Ensure the pilot clients are representative of the different profiles of people in the organization as well as the different geographic locations.</span></span> <span data-ttu-id="231a2-120">[Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)と[Skype for business](https://go.microsoft.com/fwlink/p/?LinkId=321551)の従来の電卓や、自分のネットワークで実行した[ケーススタディ](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)に対して、結果をクロスチェックすることができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-120">You can cross-check your results against our old calculators for [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) and [Skype for Business](https://go.microsoft.com/fwlink/p/?LinkId=321551) or the [case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) we performed on our own network.</span></span> 
    
4. <span data-ttu-id="231a2-121">ネットワークに変更を加える前に、パイロットグループの測定値を使用して、組織のニーズ全体を推定し、見積もりを検証するために再テストします。</span><span class="sxs-lookup"><span data-stu-id="231a2-121">Use the measurements from the pilot group to extrapolate the entire organization's needs and re-test to validate the estimations before making any changes to your network.</span></span>
    
## <a name="test-your-existing-network"></a><span data-ttu-id="231a2-122">既存のネットワークをテストする</span><span class="sxs-lookup"><span data-stu-id="231a2-122">Test your existing network</span></span>
<span data-ttu-id="231a2-123"><a name="calculators"> </a></span><span class="sxs-lookup"><span data-stu-id="231a2-123"><a name="calculators"> </a></span></span>

 <span data-ttu-id="231a2-124">**ネットワークツール。**</span><span class="sxs-lookup"><span data-stu-id="231a2-124">**Network tools.**</span></span> <span data-ttu-id="231a2-125">インターネット帯域幅をテストおよび検証して、ダウンロード、アップロード、および待機時間の制約を決定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-125">Test and validate your Internet bandwidth to determine download, upload, and latency constraints.</span></span> <span data-ttu-id="231a2-126">これらのツールは、完全に展開された後と同様に、移行のためのネットワークの機能を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="231a2-126">These tools will help you determine the capabilities of your network for migration as well as after you're fully deployed.</span></span> 
    
- <span data-ttu-id="231a2-127">[Microsoft リモート接続アナライザー](https://go.microsoft.com/fwlink/p/?LinkId=517243): Exchange Online 環境での接続をテストします。</span><span class="sxs-lookup"><span data-stu-id="231a2-127">[Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Tests connectivity in your Exchange Online environment.</span></span>
    
- <span data-ttu-id="231a2-128">Outlook および Office 365 の問題を修正するには、 [Microsoft Support And Recovery Assistant For Office 365](https://diagnostics.office.com/#/Download?env=SOC) を使用します。</span><span class="sxs-lookup"><span data-stu-id="231a2-128">Use the [Microsoft Support and Recovery Assistant for Office 365](https://diagnostics.office.com/#/Download?env=SOC) to fix Outlook and Office 365 problems.</span></span> 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a><span data-ttu-id="231a2-129">Office 365 のネットワーク計画と移行パフォーマンスの向上のためのベストプラクティス</span><span class="sxs-lookup"><span data-stu-id="231a2-129">Best practices for network planning and improving migration performance for Office 365</span></span>
<span data-ttu-id="231a2-130"><a name="BestPractices"> </a></span><span class="sxs-lookup"><span data-stu-id="231a2-130"><a name="BestPractices"> </a></span></span>

<span data-ttu-id="231a2-131">Office 365 の動作を向上させる方法の詳細については、これらのベストプラクティスをさらに掘り下げて説明します。</span><span class="sxs-lookup"><span data-stu-id="231a2-131">Dig a little deeper into these best practices for more information about improving your Office 365 experience.</span></span>
  
1. <span data-ttu-id="231a2-132">すぐにユーザーのサポートを開始する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="231a2-132">Want to get started helping your users right away?</span></span> <span data-ttu-id="231a2-133">ネットワークが連携していない場合に、SharePoint Online、Exchange Online、Lync Online などの Office 365 を使用する際のヒントについては、「 [office 365 を低速ネットワークで使用するためのベストプラクティス](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-133">See [Best practices for using Office 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) for tips on using Office 365, including SharePoint Online, Exchange Online, and Lync Online, when your network just isn't cooperating.</span></span> <span data-ttu-id="231a2-134">この記事では、Office 365 の動作を最適化するための TechNet および Support.office.com のコンテンツのロードについて説明し、web ページをカスタマイズする簡単な方法について説明します。また、最適な Office 365 環境に合わせて Internet Explorer 設定を設定する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="231a2-134">This article links out to loads of content on TechNet and Support.office.com for optimizing your Office 365 experience and includes information on easy ways to customize your web pages and how to set your Internet Explorer settings for the best Office 365 experience.</span></span> 
    
2. <span data-ttu-id="231a2-135">「 [Office 365 のネットワーク接続の原則](https://aka.ms/o365networkingprinciples) 」を参照して、office 365 のトラフィックを安全に管理し、最適なパフォーマンスを得るための接続の原則について理解します。</span><span class="sxs-lookup"><span data-stu-id="231a2-135">Read [Office 365 Network Connectivity Principles](https://aka.ms/o365networkingprinciples) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> <span data-ttu-id="231a2-136">この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="231a2-136">This article will help you understand the most recent guidance for securely optimizing Office 365 network connectivity.</span></span> 
    
3. <span data-ttu-id="231a2-137">Windows 更新プログラムのスケジュールを慎重に管理することによって、メールの移行のパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="231a2-137">Improve mail migration performance by carefully managing the schedule for Windows Updates.</span></span> <span data-ttu-id="231a2-138">クライアントコンピューターをバッチ処理で更新し、ネットワーク帯域幅の使用を制限するために Office 365 に移行する前にすべてのクライアントコンピューターが更新されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-138">You can update your client computers in batches and ensure that all client computers are updated before migrating to Office 365 to regulate the use of network bandwidth.</span></span> <span data-ttu-id="231a2-139">詳細については、「 [365 Office のデスクトップを手動で更新および構成する (最新の更新プログラム](https://support.microsoft.com/gp/office-2013-365-update))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-139">For more information, see [Manually update and configure desktops for Office 365 for the latest updates](https://support.microsoft.com/gp/office-2013-365-update).</span></span>
    
4. <span data-ttu-id="231a2-140">Office 365 のネットワークトラフィックは、信頼されたインターネットサービスとして扱われ、組織によっては、信頼されていないインターネットサービスへのネットワークトラフィックに関する、従来のフィルタリングやスキャンの多くをバイパスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="231a2-140">Office 365 network traffic performs best when it's treated as a trusted Internet service and allowed to bypass much of the traditional filtering and scanning that some organizations place on network traffic to untrusted Internet services.</span></span> <span data-ttu-id="231a2-141">これには、プロキシユーザー認証やパケット検査などの送信処理の削除に加えて、適切なネットワークアドレス変換 (NAT) を使用してインターネットへのローカル出口を保証し、増加したネットワーク要求を処理するのに十分な帯域幅容量を含めることが含まれます。</span><span class="sxs-lookup"><span data-stu-id="231a2-141">This typically includes removing outbound processing such as proxy user authentication and packet inspection, as well as ensuring local egress to the Internet with the proper Network Address Translation (NAT) and enough bandwidth capacity to handle the increased network requests.</span></span> <span data-ttu-id="231a2-142">ネットワーク上の信頼されたインターネットサービスとして Office 365 を処理するようにネットワークを構成する方法の詳細については、「 [office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="231a2-142">Refer to [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)for additional guidance on configuring your network to handle Office 365 as a trusted Internet service on your network.</span></span>
    
1. <span data-ttu-id="231a2-143">[Office 365 エンドポイントの管理](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)を確認します。</span><span class="sxs-lookup"><span data-stu-id="231a2-143">Ensure [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span> <span data-ttu-id="231a2-144">Office 365 に送られる追加のトラフィックは、送信プロキシ接続の増加と、TLS/SSL を介したセキュリティで保護されたトラフィックの増加につながります。</span><span class="sxs-lookup"><span data-stu-id="231a2-144">The additional traffic going to Office 365 results in an increase of outbound proxy connections as well as an increase in secure traffic over TLS/SSL.</span></span>
    
2. <span data-ttu-id="231a2-145">送信プロキシでユーザー認証が必要な場合は、接続が遅くなったり、機能が失われたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="231a2-145">If your outbound proxies require user authentication you may experience slow connectivity or a loss of functionality.</span></span> <span data-ttu-id="231a2-146">Office 365 ドメインの認証要件を省略すると、このオーバーヘッドを減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-146">Bypassing the authentication requirement for the Office 365 domains can reduce this overhead.</span></span>
    
3. <span data-ttu-id="231a2-147">多数の共有予定表とメールボックスがある場合、Outlook から Exchange への接続数が増加する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="231a2-147">If you have a large number of shared calendars and mailboxes, you may see an increase in the number of connections from Outlook to Exchange.</span></span> <span data-ttu-id="231a2-148">たとえば、Outlook クライアントは、使用されている共有予定表ごとに、最大2つの追加の接続を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="231a2-148">For instance, the Outlook client may open up to two additional connections for each shared calendar in use.</span></span> <span data-ttu-id="231a2-149">このような状況では、出口プロキシが接続を処理できることを確認するか、Outlook 用 Office 365 への接続のプロキシをバイパスするようにします。</span><span class="sxs-lookup"><span data-stu-id="231a2-149">In this situation, ensure that the egress proxy can handle the connections, or bypass the proxy for connections to Office 365 for Outlook.</span></span>
    
4. <span data-ttu-id="231a2-150">パブリック IP アドレスに対してサポートされるデバイスの最大数と、複数の IP アドレス間で負荷分散を行う方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="231a2-150">Determine the maximum number of supported devices for a public IP address and how to load balance across multiple IP addresses.</span></span> <span data-ttu-id="231a2-151">詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="231a2-151">For more information, see [NAT support with Office 365](nat-support-with-microsoft-365.md).</span></span>
    
5. <span data-ttu-id="231a2-152">ネットワーク上のコンピューターからの送信接続を調査している場合は、このフィルター処理を Office 365 ドメインにバイパスすると、接続性とパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="231a2-152">If you're inspecting outbound connections from computers on your network, bypassing this filtering to the Office 365 domains will improve connectivity and performance.</span></span> <span data-ttu-id="231a2-153">さらに、送信検査をバイパスすることで、単一のインターネット出口の必要性がなくなり、Office 365 の宛先のネットワーク要求に対してローカルのインターネット出口が有効になります。</span><span class="sxs-lookup"><span data-stu-id="231a2-153">Additionally, bypassing outbound inspection often removes the need for a single Internet egress and enables local Internet egress for Office 365 destined network requests.</span></span>
    
6. <span data-ttu-id="231a2-154">内部ネットワーク設定を見つけるお客様は、パフォーマンスに影響を与える場合があります。</span><span class="sxs-lookup"><span data-stu-id="231a2-154">Some customers find internal network settings may affect performance.</span></span> <span data-ttu-id="231a2-155">最大転送単位 (MTU) サイズ、ネットワーク自動ネゴシエーションまたは自動検出、インターネットへのサブ最適なルートなどの設定は、よく見られる場所です。</span><span class="sxs-lookup"><span data-stu-id="231a2-155">Settings such as maximum transmission unit (MTU) size, network auto-negotiation or auto-detection, and sub-optimal routes to the Internet are common places to look.</span></span>
    
## <a name="network-planning-reference-for-office-365"></a><span data-ttu-id="231a2-156">Office 365 のネットワーク計画リファレンス</span><span class="sxs-lookup"><span data-stu-id="231a2-156">Network planning reference for Office 365</span></span>
<span data-ttu-id="231a2-157"><a name="NetReference"> </a></span><span class="sxs-lookup"><span data-stu-id="231a2-157"><a name="NetReference"> </a></span></span>

<span data-ttu-id="231a2-158">これらのトピックには、詳細な Office 365 のネットワーク参照情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="231a2-158">These topics contain detailed Office 365 network reference information.</span></span>
  
- [<span data-ttu-id="231a2-159">Office 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="231a2-159">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [<span data-ttu-id="231a2-160">コンテンツ配信ネットワーク</span><span class="sxs-lookup"><span data-stu-id="231a2-160">Content delivery networks</span></span>](content-delivery-networks.md)
    
- [<span data-ttu-id="231a2-161">Office 365 の外部ドメイン ネーム システムのレコード</span><span class="sxs-lookup"><span data-stu-id="231a2-161">External Domain Name System records for Office 365</span></span>](external-domain-name-system-records.md)
    
- [<span data-ttu-id="231a2-162">Office 365 サービスでの IPv6 サポート</span><span class="sxs-lookup"><span data-stu-id="231a2-162">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
    
- [<span data-ttu-id="231a2-163">Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="231a2-163">Office 365 Network Connectivity Principles</span></span>](https://aka.ms/o365networkingprinciples)
    
- [<span data-ttu-id="231a2-164">Office 365 のビデオネットワークについてよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="231a2-164">Office 365 video networking Frequently Asked Questions (FAQ)</span></span>](office-365-video-networking-faq.md)
    
- [<span data-ttu-id="231a2-165">Office 365 サービスに接続するネットワーク デバイスの計画</span><span class="sxs-lookup"><span data-stu-id="231a2-165">Plan for network devices that connect to Office 365 services</span></span>](plan-for-network-devices.md)
    
- [<span data-ttu-id="231a2-166">Office 365 サービスのセットアップガイド</span><span class="sxs-lookup"><span data-stu-id="231a2-166">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a><span data-ttu-id="231a2-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="231a2-167">See also</span></span>

[<span data-ttu-id="231a2-168">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="231a2-168">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)