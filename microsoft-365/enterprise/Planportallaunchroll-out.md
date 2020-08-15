---
title: SharePoint Online でポータルの起動ロールアウトプランを計画する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: この記事では、SharePoint Online でのポータルの起動を計画する方法と、正常に起動するために必要な手順について説明します。
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692203"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a><span data-ttu-id="7723f-103">SharePoint Online でポータルの起動ロールアウトプランを計画する</span><span class="sxs-lookup"><span data-stu-id="7723f-103">Planning your portal launch roll-out plan in SharePoint Online</span></span>

<span data-ttu-id="7723f-104">ポータルは、イントラネット上の SharePoint サイトであり、サイト上のコンテンツを使用する多数のサイト ビューアーがいます。</span><span class="sxs-lookup"><span data-stu-id="7723f-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="7723f-105">大規模な組織では、会社ポータルと人事ポータルなど、これらのいくつかが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-105">In large organizations there could be several of these; for example, a company portal and an HR portal.</span></span> <span data-ttu-id="7723f-106">通常、ポータルには、サイトとそのコンテンツの作成および作成者は比較的少ないです。</span><span class="sxs-lookup"><span data-stu-id="7723f-106">Typically portals have relatively few people who create and author the site and its content.</span></span> <span data-ttu-id="7723f-107">ポータルへのほとんどの訪問者は、コンテンツの読み取りと使用のみを行います。</span><span class="sxs-lookup"><span data-stu-id="7723f-107">Most visitors to the portal only read and consume the content.</span></span>

<span data-ttu-id="7723f-108">この記事では、SharePoint Online への展開とロールアウト計画を計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7723f-108">This article describes how to plan your deployment and roll-out plan to SharePoint Online.</span></span> <span data-ttu-id="7723f-109">また、SharePoint Online で従来のロードテストが許可されていない場合の対処方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="7723f-109">It also provides approaches to follow as traditional load testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="7723f-110">SharePoint Online はクラウドサービスであり、サービスの負荷の負荷と状態のバランスと全体的なバランスが Microsoft によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="7723f-110">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service are managed by Microsoft.</span></span>

<span data-ttu-id="7723f-111">ポータルを成功させるための基本的な原則、プラクティス、および推奨事項に従って、正常なポータルを作成[、起動](https://go.microsoft.com/fwlink/?linkid=2105838)、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7723f-111">To help in creating a successful portal, follow the basic principles, practices and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838)</span></span> 

<span data-ttu-id="7723f-112">展開方法については、以下で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="7723f-112">The deployment approach is highlighted below.</span></span>

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a><span data-ttu-id="7723f-113">SharePoint Online での容量計画の概要</span><span class="sxs-lookup"><span data-stu-id="7723f-113">Overview of capacity planning in SharePoint Online</span></span>
<span data-ttu-id="7723f-114">キャパシティを効率的に使用し、予期しない成長を処理するために、どのファームでも、特定の使用シナリオを追跡する自動化があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-114">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks certain usage scenarios.</span></span> <span data-ttu-id="7723f-115">1つのファーム内の1つのテナントに正確な成長は予測できませんが、集約された要求の合計は予測可能です。</span><span class="sxs-lookup"><span data-stu-id="7723f-115">While exact growth is unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="7723f-116">SharePoint Online の拡張傾向を特定することで、今後の拡張を計画できます。</span><span class="sxs-lookup"><span data-stu-id="7723f-116">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span> <span data-ttu-id="7723f-117">容量計画の詳細 [と SharePoint Online のロードテスト](capacity-planning-and-load-testing-sharepoint-online.md)の詳細については、を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7723f-117">For more information on [Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).</span></span>

<span data-ttu-id="7723f-118">正常な起動の重要な部分は、以下に説明する「ウェーブ」または「段階的なロールアウト」アプローチです。</span><span class="sxs-lookup"><span data-stu-id="7723f-118">A key part of a successful launch is the "wave" or "phased roll-out" approach detailed below.</span></span> 

## <a name="can-i-load-test-sharepoint-online"></a><span data-ttu-id="7723f-119">テスト SharePoint Online を読み込むことはできますか?</span><span class="sxs-lookup"><span data-stu-id="7723f-119">Can I load test SharePoint Online?</span></span>
<span data-ttu-id="7723f-120">SharePoint Online は、共有された複数のテナント環境で、複数のファーム間でバランスが取れており、継続的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="7723f-120">SharePoint Online is a shared multi-tenanted environment which is balanced across farms and scale is adjusted in an on-going basis.</span></span> <span data-ttu-id="7723f-121">負荷テスト SharePoint Online などの環境では、拡張の変更によって予期しない結果が得られるだけでなく、許可されません。</span><span class="sxs-lookup"><span data-stu-id="7723f-121">Load testing an environment, like SharePoint Online, whose scale changes continuously will not only  give you unexpected results but it is not permitted.</span></span> 

<span data-ttu-id="7723f-122">詳細につい[ては、「容量計画と負荷テスト (SharePoint Online)」を参照して](capacity-planning-and-load-testing-sharepoint-online.md)ください。</span><span class="sxs-lookup"><span data-stu-id="7723f-122">Learn more:  [Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)</span></span>

## <a name="optimize-pages-by-following-recommended-guidelines"></a><span data-ttu-id="7723f-123">推奨ガイドラインに従ってページを最適化する</span><span class="sxs-lookup"><span data-stu-id="7723f-123">Optimize pages by following recommended guidelines</span></span>
<span data-ttu-id="7723f-124">オンプレミス展開からのページは、sharepoint online の推奨ガイドラインに対して確認することなく、SharePoint Online に移動するだけではありません。</span><span class="sxs-lookup"><span data-stu-id="7723f-124">Pages from an on-Premise deployment should not simply be moved as they are onto SharePoint Online without reviewing them against recommended guidelines for SharePoint Online.</span></span> <span data-ttu-id="7723f-125">最善の方法は、組織内のほとんどのユーザーがサイトの開始点としてアクセスできるように、SharePoint のサイトまたはポータルのすべてのホームページを常に最適化することです。</span><span class="sxs-lookup"><span data-stu-id="7723f-125">The best approach is to always optimize any home page for any site or portal in SharePoint, as this is where most users in your organization will access as the starting point for your site(s).</span></span>

<span data-ttu-id="7723f-126">いくつかの基本的な要因を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-126">A few basic factors should be considered:</span></span>
- <span data-ttu-id="7723f-127">オンプレミスの展開では、オブジェクトキャッシュ、出力キャッシュ、blob キャッシュなどの従来のサーバー側キャッシュを活用できます。</span><span class="sxs-lookup"><span data-stu-id="7723f-127">On-Premise deployments can leverage traditional server-side caches like object cache, output cache and blob cache.</span></span> <span data-ttu-id="7723f-128">クラウドでのトポロジの違いにより、これらのオプションは特にスケールの違いによって実現できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-128">With the topology differences in the cloud, these options are not necessarily available as the sheer scale differences make them less viable approaches.</span></span>
- <span data-ttu-id="7723f-129">クラウドの使用に使用されるページ/機能/カスタマイズは、ユーザーの時間と分散した場所によって、異なる領域または地域のユーザーが一貫した環境を持つように最適化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-129">Any pages / features / customizations used for cloud consumption should be optimized for higher latency as well as the distributed locations of users, so that users in different areas or regions have a more consistent experience.</span></span> <span data-ttu-id="7723f-130">クラウド提供コンテンツ配信ネットワーク (CDN) のように、分散ユーザーベースおよびモダン SharePoint に最適化するための最適化を行います。最新の既知の良好 (LKG) は、box (OOTB) web パーツで利用できます。</span><span class="sxs-lookup"><span data-stu-id="7723f-130">Cloud offers optimizations like Content Delivery Networks (CDN) to optimize for a distributed user base as well as for modern SharePoint, the last known good (LKG) is utilized by our out of the box (OOTB) web parts.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="7723f-131">対処方法:</span><span class="sxs-lookup"><span data-stu-id="7723f-131">What to do:</span></span>
 - <span data-ttu-id="7723f-132">SharePoint Online のすべてのサイトページでは、Chromium 拡張機能である [ページ診断ツール](https://aka.ms/perftool)を使用して、ガイダンスの分析と提供を支援します。</span><span class="sxs-lookup"><span data-stu-id="7723f-132">For all site pages in SharePoint Online use the [Page Diagnostics tool](https://aka.ms/perftool), which is a Chromium extension which will assist with analyzing and providing guidance.</span></span> <span data-ttu-id="7723f-133">これは、分析と最適化の出発点として設計されているため、サイトの所有者、編集者、管理者、および開発者が使用できます。</span><span class="sxs-lookup"><span data-stu-id="7723f-133">This can be used by site owners, editors, administrators and developers as it is designed to be a starting point for analysis and optimization.</span></span>
 - <span data-ttu-id="7723f-134">開発者は、モダンページのブラウザーで、F12 ブラウザー開発者ツールや CTRL + F12 のような開発ツールも使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-134">Developers should also use development tools like F12 browser developer tool as well as CTRL-F12 in the browser on modern pages.</span></span> <span data-ttu-id="7723f-135">[Fiddler](https://www.telerik.com/download/fiddler) を使用して、ページのサイズの重み (ページ数 (メガバイト)) と、ページ全体の読み込みに影響を与える呼び出しおよび要素の数を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="7723f-135">[Fiddler](https://www.telerik.com/download/fiddler) can also be used to review the size weight (how large the page is in megabytes) of the page and the number of calls and elements impacting the overall page load.</span></span> 

<span data-ttu-id="7723f-136">ここでは、ページを最適化するための簡単な概要を説明しました。</span><span class="sxs-lookup"><span data-stu-id="7723f-136">This section was a brief summary for optimizing pages.</span></span>  <span data-ttu-id="7723f-137">詳細については、「  [正常なポータルの作成、起動、保守](https://go.microsoft.com/fwlink/?linkid=2105838)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7723f-137">To learn more see:  [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span>

## <a name="follow-a-wave--phased-roll-out-approach"></a><span data-ttu-id="7723f-138">ウェーブ/フェーズのロールアウトアプローチに従う</span><span class="sxs-lookup"><span data-stu-id="7723f-138">Follow a Wave / Phased roll-out approach</span></span>
<span data-ttu-id="7723f-139">サイトを起動する従来のビッグバンアプローチでは、カスタマイズ、外部ソース、サービス、またはプロセスが適切な規模でテストされたことを確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="7723f-139">The traditional big bang approach for site launches will not allow verification that customizations, external sources, services or processes have been tested at the right scale.</span></span> <span data-ttu-id="7723f-140">これは、月単位で起動することを意味するわけではありませんが、組織の規模に応じて少なくとも数日間にわたってお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7723f-140">This doesn't mean that it will take months to launch, but it is recommended over at least several days dependent on your organization size.</span></span> <span data-ttu-id="7723f-141">そのため、ウェーブロールアウトプランに従うと、次のフェーズに進む前に問題を一時停止して解決することができ、問題の影響を受ける可能性のあるユーザーの数が減少します。</span><span class="sxs-lookup"><span data-stu-id="7723f-141">Following a wave roll-out plan therefore gives you the option to pause and resolve issues before proceeding with the next phase and therefore lowers the potential number of users impacted by any issues.</span></span> <span data-ttu-id="7723f-142">サービスとしての SharePoint は、利用状況と予測される使用状況に基づいて容量を拡大します。また、発売を通知する必要はありません。そのためには、成功を確実にするためにガイドラインに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-142">SharePoint as a service scales your capacity based on usage and predicted usage and whilst we don't need you to notify us of your launch, you should follow the guidelines to ensure success.</span></span>
  
<span data-ttu-id="7723f-143">次の図に示すように、招待されたユーザーの数は、実際にサイトを使用しているユーザーよりも大幅に高くなることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="7723f-143">As shown in the following image, often the number of users that are invited is significantly higher than those that actually use the site.</span></span> <span data-ttu-id="7723f-144">この図は、リリースを展開する方法に関する戦略を示しています。</span><span class="sxs-lookup"><span data-stu-id="7723f-144">This image shows a strategy about how to roll out a release.</span></span> <span data-ttu-id="7723f-145">この方法では、大多数のユーザーが表示される前に SharePoint サイトを改善する方法を特定できます。</span><span class="sxs-lookup"><span data-stu-id="7723f-145">This method helps identify ways to improve the SharePoint site before the majority of the users see it.</span></span>
  
![招待ユーザーとアクティブなユーザーを示すグラフ](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
<span data-ttu-id="7723f-147">パイロットフェーズでは、組織が信頼していることを認識しているユーザーからのフィードバックを取得することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7723f-147">In the pilot phase, it is good to get feedback from users that the organization trusts and knows will be engaged.</span></span> <span data-ttu-id="7723f-148">このようにすると、システムがどのように使用されているか、またどのように実行されているかを把握することができます。</span><span class="sxs-lookup"><span data-stu-id="7723f-148">This way it is possible to gauge how the system is being used, as well as how it is performing.</span></span>
  
<span data-ttu-id="7723f-149">各ウェーブで、各機能に関するユーザーのフィードバックと、展開の各ウェーブのパフォーマンスを収集します。</span><span class="sxs-lookup"><span data-stu-id="7723f-149">During each of the waves, gather user feedback around the features as well as the performance during each wave of deployment.</span></span> <span data-ttu-id="7723f-150">これには、システムをゆっくり導入して、システムの使用が増えるにつれて改善を行うという利点があります。</span><span class="sxs-lookup"><span data-stu-id="7723f-150">This has the advantage of slowly introducing the system and making improvements as the system gets more use.</span></span> <span data-ttu-id="7723f-151">これにより、サイトがより多くのユーザーにロールアウトされ、ページ最適化のガイドラインに従うことで、ユーザーにとって良好な状態が保証されるので、増加した負荷に対応できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7723f-151">This also allows us to react to the increased load as the site is rolled out to more and more users and combined with following the guidelines for page optimization ensures a positive experience for your users.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="7723f-152">対処方法:</span><span class="sxs-lookup"><span data-stu-id="7723f-152">What to do:</span></span>
- <span data-ttu-id="7723f-153">各フェーズのタイミングを決定し、続行する前に調整する必要があるかどうかについて、緊急時対応/一時停止があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7723f-153">Decide on the timing of each phase and ensure that you have a contingency / pause opportunity, should you need to make adjustments before continuing</span></span>
- <span data-ttu-id="7723f-154">有効にする必要がある最初のユーザーグループを計画し、前の部分に移動するために必要なフィードバックを確実に受信するようにします。</span><span class="sxs-lookup"><span data-stu-id="7723f-154">Plan your first group of users that you want to enable, to ensure you receive the feedback you need to move forward.</span></span> <span data-ttu-id="7723f-155">これは、可能な場合に、フィードバックをタイムリーに提供するアクティブなユーザーグループを選択できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7723f-155">This means that where possible, select an active group of users that will provide feedback in a timely fashion</span></span>
- <span data-ttu-id="7723f-156">各ウェーブを計画する際には、小さなユーザーベース (5000 ユーザー未満) で開始して、各ウェーブの処理中にグループのサイズを大きくします。</span><span class="sxs-lookup"><span data-stu-id="7723f-156">As you plan each wave, try and start with a small user base (less than 5000 users), and then increase the group sizes as you proceed with each wave.</span></span> <span data-ttu-id="7723f-157">これにより、ずらす方法を作成し、必要になる可能性のある一時停止の機会を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7723f-157">This helps to create a staggered approach and allows easier pause opportunities that may be needed.</span></span>