---
title: SharePoint Online のキャパシティ プランニングとロード テスト
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
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
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: この記事では、従来のロードテストを実行せずに SharePoint Online に展開する方法について説明します。これは許可されていないためです。
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692066"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="ca300-103">SharePoint Online のキャパシティ プランニングとロード テスト</span><span class="sxs-lookup"><span data-stu-id="ca300-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="ca300-104">この記事では、SharePoint Online でロードテストが許可されていないため、従来のロードテストを行わずに SharePoint Online に展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca300-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="ca300-105">SharePoint Online は、クラウドサービスであり、サービスの負荷の負荷の状態、正常性、および全体的なバランスが Microsoft によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="ca300-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="ca300-106">サイトを正常に起動するための最善の方法は、「 [ポータルの起動を計画](planportallaunchroll-out.md)する」で強調表示されている基本的な原則、ベストプラクティス、推奨事項に従うことです。</span><span class="sxs-lookup"><span data-stu-id="ca300-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="ca300-107">SharePoint Online が容量計画を実行する方法の概要</span><span class="sxs-lookup"><span data-stu-id="ca300-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="ca300-108">オンプレミス展開による SharePoint Online の主な利点の1つは、クラウドの弾力性、および分散した地域におけるユーザーのための最適化です。</span><span class="sxs-lookup"><span data-stu-id="ca300-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="ca300-109">この大規模な環境では、数百万のユーザーに対して日常的にサービスを提供するように設定されているため、ファームを分散および拡張することによって処理能力を効果的に処理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ca300-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="ca300-110">多くの場合、1つのファームの1つのテナントに対する成長は予測できませんが、集約された要求の合計は予測可能です。</span><span class="sxs-lookup"><span data-stu-id="ca300-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="ca300-111">SharePoint Online の拡張傾向を特定することで、今後の拡張を計画できます。</span><span class="sxs-lookup"><span data-stu-id="ca300-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="ca300-112">キャパシティを効率的に使用し、予期しない成長に対処するために、どのファームでも、サービスのさまざまな要素を追跡および監視する自動化があります。</span><span class="sxs-lookup"><span data-stu-id="ca300-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="ca300-113">複数の測定値が使用されており、メインのいずれかが CPU 負荷になっています。これは、フロントエンドサーバーをスケールアップするための信号として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca300-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="ca300-114">さらに、SQL 環境は時間の経過と共に負荷と成長に応じて拡大または縮小し、フェーズと波形に従うことによって、その負荷と成長の適切な配分が可能になるため、 [段階的なアプローチを採用](planportallaunchroll-out.md)することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca300-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="ca300-115">キャパシティは継続的にハードウェアを追加するだけではなく、その容量を管理および制御して、有効なロード要求を処理していることを確認することにも関連しています。</span><span class="sxs-lookup"><span data-stu-id="ca300-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="ca300-116">推奨されているガイダンスに従ってお客様に最適な環境を確保することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ca300-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="ca300-117">また、サービスでの "不適切な動作" の動作を許可しないように、調整パターンと制御を適所に配置することも意味します。</span><span class="sxs-lookup"><span data-stu-id="ca300-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="ca300-118">すべての "不良" 動作は意図的なものではありませんが、その動作の影響が抑制されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca300-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="ca300-119">調整の詳細とその回避方法の詳細については、「 [ガイダンスの調整を回避する方法](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca300-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="ca300-120">テスト SharePoint Online を読み込むことができない理由</span><span class="sxs-lookup"><span data-stu-id="ca300-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="ca300-121">オンプレミス環境では、負荷テストを使用してスケールの仮定を検証し、最終的にはファームの限界点を見つけます。負荷で飽和状態にします。</span><span class="sxs-lookup"><span data-stu-id="ca300-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="ca300-122">SharePoint Online では、スケールが相対的に流動的で、一定のヒューリスティックに基づいて負荷を調整、調整し、制御するため、異なる操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca300-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="ca300-123">このような大規模なマルチテナント環境の場合は、同じファーム内のすべてのテナントを保護する必要があるため、すべてのロードテストが自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="ca300-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="ca300-124">ただし、調整を試みるのではなく、テストをロードしようとすると、disappointing となる可能性がある結果を得ることができます。これは、今日テストしたファームにはテスト期間中にスケール変更があり、テスト後は規模の変更が行われている可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="ca300-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="ca300-125">テスト SharePoint をサービスとして読み込もうとするのではなく、推奨されている手順に従うようにして、 [正常なポータルガイダンスを作成、起動、および維持](https://go.microsoft.com/fwlink/?linkid=2105838) する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca300-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838) guidance.</span></span>