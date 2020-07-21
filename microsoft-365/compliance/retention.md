---
title: コンテンツを自動的に保持または削除するアイテム保持ポリシーと保持ラベルの詳細
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 必要なコンテンツを保持し不要なコンテンツを削除するのに役立つ、アイテム保持ポリシーと保持ラベルについて説明します。
ms.openlocfilehash: b67320af6f388386d7b7723bbe3f645b46eed8e7
ms.sourcegitcommit: f7566dd6010744c72684efdc37f4471672330b61
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138215"
---
# <a name="learn-about-retention-policies-and-retention-labels"></a><span data-ttu-id="cf1ca-103">アイテム保持ポリシーと保持ラベルの詳細</span><span class="sxs-lookup"><span data-stu-id="cf1ca-103">Learn about retention policies and retention labels</span></span>

><span data-ttu-id="cf1ca-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="cf1ca-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="cf1ca-p101">ほとんどの組織では、電子メール、ドキュメント、インスタント メッセージなどのデータの量と複雑さが日々増しています。次の必要性から、これらの情報を効果的に管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-p101">For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:</span></span>
  
- <span data-ttu-id="cf1ca-107">**最小限の期間コンテンツを保持することを要求する業界の規制や内部ポリシーを積極的に遵守する**: たとえば、米国企業改革法により、特定の種類のコンテンツを 7 年間保持することが求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-107">**Comply proactively with industry regulations and internal policies** that require you to retain content for a minimum period of time—for example, the Sarbanes-Oxley Act might require you to retain certain types of content for seven years.</span></span> 
- <span data-ttu-id="cf1ca-108">**訴訟やセキュリティ違反が発生した場合にリスクを軽減する**: このために、保持する必要がなくなった古いコンテンツは完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-108">**Reduce your risk in the event of litigation or a security breach** by permanently deleting old content that you're no longer required to keep.</span></span> 
    
- <span data-ttu-id="cf1ca-109">**組織内での効率的な知識の共有と迅速な対応に役立てる**: このために、ユーザーは現時点で関連性のあるコンテンツのみを対象に作業するようにします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-109">**Help your organization to share knowledge effectively and be more agile** by ensuring that your users work only with content that's current and relevant to them.</span></span> 
    
<span data-ttu-id="cf1ca-110">保持設定を構成することは、これらすべての目標を実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-110">Retention settings that you configure can help you achieve all these goals.</span></span> <span data-ttu-id="cf1ca-111">コンテンツの管理には、一般的に次の 2 つのアクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-111">Managing content commonly requires two actions:</span></span>
  
- <span data-ttu-id="cf1ca-112">**コンテンツの保持**: 保持期間が満了するまではコンテンツの完全な削除ができないようにします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-112">**Retaining** content so that it can't be permanently deleted before the end of the retention period.</span></span> 
    
- <span data-ttu-id="cf1ca-113">**コンテンツの削除**: 保持期間の満了時点でコンテンツを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-113">**Deleting** content permanently at the end of the retention period.</span></span> 
    

<span data-ttu-id="cf1ca-114">これら 2 つの保持アクションを使用して、次の結果が得られるように保持設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-114">With these two retention actions, you can configure retention settings for the following outcomes:</span></span>

- <span data-ttu-id="cf1ca-115">保持のみ: コンテンツを無期限または指定した期間保持します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-115">Retain-only: Retain content forever or for a specified period of time.</span></span>
- <span data-ttu-id="cf1ca-116">削除のみ: 指定した期間の後にコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-116">Delete-only: Delete content after a specified period of time.</span></span>
- <span data-ttu-id="cf1ca-117">保持してから削除: コンテンツを指定した期間保持してから削除します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-117">Retain and then delete: Retain content for a specified period of time and then delete it.</span></span>

<span data-ttu-id="cf1ca-118">これらの保持設定は所定の場所にあるコンテンツに作用し、コンプライアンス上の理由でコンテンツを保持する必要がある場合でも、追加のストレージを作成して構成するための追加のオーバーヘッドを節約できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-118">These retention settings work with content in place that saves you the additional overheads of creating and configuring additional storage when you need to retain content for compliance reasons.</span></span> <span data-ttu-id="cf1ca-119">また、このデータをコピーして同期するために、カスタマイズしたプロセスを実装する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-119">In addition, you don't need to implement customized processes to copy and synchronize this data.</span></span>

## <a name="how-retention-settings-work-with-content-in-place"></a><span data-ttu-id="cf1ca-120">保持設定が所定の場所にあるコンテンツに作用するしくみ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-120">How retention settings work with content in place</span></span>

<span data-ttu-id="cf1ca-121">コンテンツに保持設定が割り当てられるとき、そのコンテンツは元の場所にそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-121">When content has retention settings assigned to it, that content remains in its original location.</span></span> <span data-ttu-id="cf1ca-122">ユーザーは何事もなかったかのように、ドキュメントやメールで作業を続けることができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-122">People can continue to work with their documents or mail as if nothing's changed.</span></span> <span data-ttu-id="cf1ca-123">アイテム保持ポリシーに含まれているコンテンツをユーザーが編集または削除すると、そのコンテンツのコピーが、保持設定を適用した時点の状態で自動的に保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-123">But if they edit or delete content that's included in the retention policy, a copy of the content is automatically retained as it existed when you applied the retention settings.</span></span>
  
- <span data-ttu-id="cf1ca-124">SharePoint および OneDrive サイトの場合: コピーは、**アイテム保管**ライブラリに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-124">For SharePoint and OneDrive sites: The copy is retained in the **Preservation Hold** library.</span></span>

- <span data-ttu-id="cf1ca-125">Exchange メールボックスの場合: コピーは、**[回復可能なアイテム]** フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-125">For Exchange mailboxes: The copy is retained in the **Recoverable Items** folder.</span></span> 

- <span data-ttu-id="cf1ca-126">Teams のチャネルおよびチャット メッセージの場合: コピーは、Exchange の **[回復可能なアイテム]** フォルダー内の隠しフォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-126">For Teams channel and chat messages: The copy is retained in a hidden folder within the Exchange **Recoverable Items** folder.</span></span>

> [!NOTE]
> <span data-ttu-id="cf1ca-127">アイテム保管ライブラリは、サイトのストレージ クォータから除外されていないストレージを消費します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-127">The Preservation Hold library consumes storage that isn't exempt from a site's storage quota.</span></span> <span data-ttu-id="cf1ca-128">SharePoint グループや Microsoft 365 グループに対して保持設定を使用する場合は、ストレージを増やすことが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-128">You might need to increase your storage when you use retention settings for SharePoint and Microsoft 365 groups.</span></span>
> 
<span data-ttu-id="cf1ca-129">セキュリティで保護されているこれらの場所や保持されているコンテンツは、ほとんどのユーザーには表示されません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-129">These secure locations and the retained content are not visible to most people.</span></span> <span data-ttu-id="cf1ca-130">ほとんどの場合、ユーザーは自分が作業しているコンテンツが保持設定の対象であることを知る必要さえありません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-130">In most cases, people do not even need to know that their content is subject to retention settings.</span></span>

<span data-ttu-id="cf1ca-131">保持設定がさまざまなワークロードに対してどのように機能するかの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-131">For more detailed information about how retention settings work for different workloads, see the following articles:</span></span>

- [<span data-ttu-id="cf1ca-132">SharePoint と OneDrive の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="cf1ca-132">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="cf1ca-133">Microsoft Teams の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="cf1ca-133">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="cf1ca-134">Exchange の保持の詳細</span><span class="sxs-lookup"><span data-stu-id="cf1ca-134">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="retention-policies-and-retention-labels"></a><span data-ttu-id="cf1ca-135">アイテム保持ポリシーと保持ラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-135">Retention policies and retention labels</span></span>

<span data-ttu-id="cf1ca-136">保持設定をコンテンツに割り当てる場合、アイテム保持ポリシーと保持ラベルの両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-136">You can use both retention policies and retention labels to assign your retention settings to content.</span></span> 

<span data-ttu-id="cf1ca-137">サイト レベルやメールボックス レベルで同一の保持設定を割り当てるには、アイテム保持ポリシーを使用します。一方、アイテム レベル (フォルダー、ドキュメント、メール) で保持設定を割り当てるには、保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-137">Use a retention policy to assign the same retention settings for content at a site or mailbox level, and use a retention label to assign retention settings at an item level (folder, document, email).</span></span>

<span data-ttu-id="cf1ca-138">たとえば、SharePoint サイト内のすべてのドキュメントを 5 年間保持する必要がある場合は、同じ保持ラベルをサイト内のすべてのドキュメントに適用するよりも、アイテム保持ポリシーを使用する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-138">For example, if all documents in a SharePoint site should be retained for five years, it's more efficient to do this with a retention policy than apply the same retention label to all documents in that site.</span></span> <span data-ttu-id="cf1ca-139">一方、サイト内の一部のドキュメントは 5 年間保持し、一部は 10 年間保持する必要がある場合、アイテム保持ポリシーではこれを行うことができません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-139">However, if some documents in that site should be retained for five years and others retained for ten years, a retention policy wouldn't be able to do this.</span></span> <span data-ttu-id="cf1ca-140">アイテム レベルで保持設定を指定する必要がある場合は、保持ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-140">When you need to specify retention settings at the item level, use retention labels.</span></span> 

<span data-ttu-id="cf1ca-141">アイテム保持ポリシーとは異なり、保持ラベルによる保持設定は、コンテンツが別の Microsoft 365 の場所にコピーまたは移動された場合でも、コンテンツと共に維持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-141">Unlike retention policies, retention settings from retention labels persist with the content if it’s copied or moved to a different Microsoft 365 location.</span></span> <span data-ttu-id="cf1ca-142">また、保持ラベルには、アイテム保持ポリシーではサポートされていない次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-142">In addition, retention labels have the following capabilities that retention policies don't support:</span></span> 
 
- <span data-ttu-id="cf1ca-143">コンテンツの保持期間や最終更新日以外に、コンテンツにラベルが付けられた時点やイベントに基づいて保持期間を開始するオプション。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-143">Options to start the retention period from when the content was labeled or based on an event, in addition to the age of the content or when it was last modified.</span></span>

- <span data-ttu-id="cf1ca-144">[トレーニング可能な分類子](classifier-getting-started-with.md)を使用して、ラベル付けするコンテンツを識別する。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-144">Use [trainable classifiers](classifier-getting-started-with.md) to identify content to label.</span></span>

- <span data-ttu-id="cf1ca-145">SharePoint ドキュメントに既定のラベルを適用する。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-145">Apply a default label for SharePoint documents.</span></span>

- <span data-ttu-id="cf1ca-146">コンテンツを完全に削除する前にコンテンツを確認する[廃棄確認](disposition-reviews.md) のサポート。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-146">Support [disposition review](disposition-reviews.md) to review the content before it's permanently deleted.</span></span>

- <span data-ttu-id="cf1ca-147">ラベル設定の一部として、コンテンツを [[レコード]](records.md) としてマークし、保持期間の終了時にコンテンツが削除されるときに [廃棄の証明](disposition.md#disposition-of-records) を常に取得する。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-147">Mark the content as a [record](records.md) as part of the label settings, and always have [proof of disposition](disposition.md#disposition-of-records) when content is deleted at the end of its retention period.</span></span>

### <a name="retention-policies"></a><span data-ttu-id="cf1ca-148">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-148">Retention policies</span></span>

<span data-ttu-id="cf1ca-149">アイテム保持ポリシーは、次の場所に適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-149">Retention policies can be applied to the following locations:</span></span>
- <span data-ttu-id="cf1ca-150">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="cf1ca-150">Exchange email</span></span>
- <span data-ttu-id="cf1ca-151">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="cf1ca-151">SharePoint site</span></span>
- <span data-ttu-id="cf1ca-152">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="cf1ca-152">OneDrive accounts</span></span>
- <span data-ttu-id="cf1ca-153">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-153">Microsoft 365 groups</span></span>
- <span data-ttu-id="cf1ca-154">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf1ca-154">Skype for Business</span></span>
- <span data-ttu-id="cf1ca-155">Exchange パブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-155">Exchange public folders</span></span>
- <span data-ttu-id="cf1ca-156">チームのチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-156">Teams channel messages</span></span>
- <span data-ttu-id="cf1ca-157">Teams のチャット</span><span class="sxs-lookup"><span data-stu-id="cf1ca-157">Teams chats</span></span>

<span data-ttu-id="cf1ca-158">複数の場所にも特定の場所やユーザーにも、1 つのポリシーを非常に効率的に適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-158">You can very efficiently apply a single policy to multiple locations, or to specific locations or users.</span></span>
    
<span data-ttu-id="cf1ca-159">ポリシーは、すべてのコンテンツに適用することも、キーワードや[機密情報の種類](sensitive-information-type-entity-definitions.md)を含むコンテンツなど、特定の条件を満たすコンテンツに適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-159">You can also apply a policy to all content or to content when it meets specific conditions, such as content that contains keywords or [sensitive information types](sensitive-information-type-entity-definitions.md).</span></span>

#### <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a><span data-ttu-id="cf1ca-160">[保持ロック] を使用して規制要件に準拠する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-160">Use Preservation Lock to comply with regulatory requirements</span></span>

<span data-ttu-id="cf1ca-161">一部の組織は、米国証券取引委員会 (SEC) 規則 17a-4 など、規制機関によって定義された規則に準拠する必要があります。その場合、アイテム保持ポリシーをオンにした後、それをオフにしたり、制限を緩和したりすることはできないという要求があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-161">Some organizations might need to comply with rules defined by regulatory bodies such as the Securities and Exchange Commission (SEC) Rule 17a-4, which requires that after a retention policy is turned on, it cannot be turned off or made less restrictive.</span></span> 

<span data-ttu-id="cf1ca-162">保管ロックを使用すると、アイテム保持ポリシーがロックされ、管理者を含むいかなるユーザーも、ポリシーをオフにすることや削除すること、またその制限を緩和することができなくなるため、組織はこのような規制要件を確実に満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-162">Preservation Lock ensures your organization can meet such regulatory requirements because it locks a retention policy so that no one—including the administrator—can turn off the policy, delete the policy, or make it less restrictive.</span></span>
  
<span data-ttu-id="cf1ca-163">保持ポリシーがロックされている場合:</span><span class="sxs-lookup"><span data-stu-id="cf1ca-163">When a retention policy is locked:</span></span>

- <span data-ttu-id="cf1ca-164">誰もそれをオフにすることはできません</span><span class="sxs-lookup"><span data-stu-id="cf1ca-164">No one can it turn off</span></span>
- <span data-ttu-id="cf1ca-165">場所は追加できますが、削除できません</span><span class="sxs-lookup"><span data-stu-id="cf1ca-165">Locations can be added but not removed</span></span>
- <span data-ttu-id="cf1ca-166">ポリシーの対象となるコンテンツは、保持期間中は変更または削除できません</span><span class="sxs-lookup"><span data-stu-id="cf1ca-166">Content subject to the policy can't be modified or deleted during the retention period</span></span>
- <span data-ttu-id="cf1ca-167">保持期間を延長することはできますが、短縮することはできません</span><span class="sxs-lookup"><span data-stu-id="cf1ca-167">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="cf1ca-168">要約すると、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-168">In summary, a locked retention policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cf1ca-169">アイテム保持ポリシーをロックする前に、その影響を理解し、組織が規制要件を満たす必要があるかどうかを確認することは非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-169">Before you lock a retention policy, it's critical that you understand the impact and confirm whether it's required for your organization to meet regulatory requirements.</span></span> <span data-ttu-id="cf1ca-170">保管ロックを適用すると、管理者はアイテム保持ポリシーを無効にすることも削除することもできなくなります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-170">Administrators won't be able to disable or delete a retention policy after the preservation lock is applied.</span></span>

#### <a name="releasing-a-retention-policy"></a><span data-ttu-id="cf1ca-171">アイテム保持ポリシーを解除する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-171">Releasing a retention policy</span></span>

<span data-ttu-id="cf1ca-172">アイテム保持ポリシーに保持ロックがない場合、アイテム保持ポリシーをいつでもオフにしたり削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-172">Providing your retention policy doesn't have a Preservation Lock, you can turn off or delete a retention policy at any time.</span></span> 

<span data-ttu-id="cf1ca-173">この操作を行うと、[アイテム保管ライブラリ] で保持されている SharePoint や OneDrive のコンテンツは、すぐには完全に削除されません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-173">When you do so, any SharePoint or OneDrive content that's being retained in the Preservation Hold library is not immediately and permanently deleted.</span></span> <span data-ttu-id="cf1ca-174">代わりに、不注意によるデータの損失を防ぐために、30 日間の猶予期間があります。そのポリシーのコンテンツの有効期限は、[アイテム保管ライブラリ] には表示されず、必要に応じてコンテンツを復元できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-174">Instead, to help prevent inadvertent data loss, there is a 30-day grace period, during which content expiration for that policy does not happen in the Preservation Hold library, so that you can restore any content from there, if needed.</span></span> <span data-ttu-id="cf1ca-175">また、猶予期間中はこのコンテンツを手動で削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-175">Additionally, you can't manually delete this content during the grace period.</span></span>

<span data-ttu-id="cf1ca-176">猶予期間中にアイテム保持ポリシーをもう一度有効にすることができます。そのポリシーのコンテンツは削除されません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-176">You can turn on the retention policy again during the grace period, and no content will be deleted for that policy.</span></span>

<span data-ttu-id="cf1ca-177">この SharePoint と OneDrive の 30 日の猶予期間は、Exchange の 30 日の保留期間に対応しています。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-177">This 30-day grace period in SharePoint and OneDrive corresponds to the 30-day delay hold in Exchange.</span></span> <span data-ttu-id="cf1ca-178">詳しくは、[メールボックスの管理についての詳細](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold) をご覧ください。。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-178">For more information, see [Managing mailboxes on delay hold](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="cf1ca-179">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-179">Retention labels</span></span>

<span data-ttu-id="cf1ca-180">保持ラベルは、異なる保持設定を必要とするさまざまな種類のコンテンツに対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-180">Use retention labels for different types of content that require different retention settings.</span></span> <span data-ttu-id="cf1ca-181">例:</span><span class="sxs-lookup"><span data-stu-id="cf1ca-181">For example:</span></span>
  
- <span data-ttu-id="cf1ca-182">最低限の期間、保持する必要のある納税申告書。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-182">Tax forms that need to be retained for a minimum period of time.</span></span> 
    
- <span data-ttu-id="cf1ca-183">特定の期間が経過した後、完全に削除する必要があるプレス資料。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-183">Press materials that need to be permanently deleted when they reach a specific age.</span></span> 
    
- <span data-ttu-id="cf1ca-184">特定の期間保持した後に完全に削除する必要がある競合企業のリサーチ。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-184">Competitive research that needs to be retained for a specific period and then permanently deleted.</span></span> 
    
- <span data-ttu-id="cf1ca-185">編集も削除もできないように、レコードとしてマークする必要がある就労ビザ。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-185">Work visas that must be marked as a record so that they can't be edited or deleted.</span></span> 
    
<span data-ttu-id="cf1ca-186">いずれの場合も、保持ラベルを使用すると、アイテム レベル (ドキュメントやメール) でガバナンス制御用の保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-186">In all these cases, retention labels let you apply retention settings for governance control at the item level (document or email).</span></span>
  
<span data-ttu-id="cf1ca-187">保持ラベルを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-187">With retention labels, you can:</span></span>
  
- <span data-ttu-id="cf1ca-188">**組織のユーザーが保持ラベルを手動で適用できるようにする**。ユーザーが保持ラベルを手動で適用できるのは、Outlook および Outlook on the web、OneDrive、SharePoint​​、Microsoft 365 グループ内のコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-188">**Enable people in your organization to apply a retention label manually** to content in Outlook and Outlook on the web, OneDrive, SharePoint, and Microsoft 365 groups.</span></span> <span data-ttu-id="cf1ca-189">多くの場合、ユーザーは自分が操作するコンテンツの種類を最もよく知っているので、コンテンツを分類して適切な保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-189">Users often know best what type of content they're working with, so they can classify it and have the appropriate retention settings applied.</span></span> 
    
- <span data-ttu-id="cf1ca-190">コンテンツに次のものが含まれている場合など、特定の条件に一致するときには、**保持ラベルをコンテンツに自動的に適用**できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-190">**Apply retention labels to content automatically** if it matches specific conditions, such as when the content contains:</span></span> 
    - <span data-ttu-id="cf1ca-191">特定の種類の機密情報。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-191">Specific types of sensitive information.</span></span>
    - <span data-ttu-id="cf1ca-192">作成したクエリに一致する特定のキーワード。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-192">Specific keywords that match a query you create.</span></span>
    - <span data-ttu-id="cf1ca-193">トレーニング可能な分類子のパターン マッチ。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-193">Pattern matches for a trainable classifier.</span></span>

- <span data-ttu-id="cf1ca-194">**コンテンツにラベルが付けられた時点から保持期間を開始する**。SharePoint サイトや OneDrive アカウントのドキュメント、および予定表アイテム以外のメール アイテムに対してこの操作を行えます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-194">**Start the retention period from when the content was labeled** for documents in SharePoint sites and OneDrive accounts, and to email items with the exception of calendar items.</span></span> <span data-ttu-id="cf1ca-195">この構成の保持ラベルを予定表アイテムに適用すると、保持期間はアイテムが送信された時点から開始されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-195">If you apply a retention label with this configuration to a calendar item, the retention period starts from when it is sent.</span></span>

- <span data-ttu-id="cf1ca-196">従業員の退職、契約の期限切れなど、**イベントの発生時に保持期間を開始する**。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-196">**Start the retention period when an event occurs**, such as employees leave the organization, or contracts expire.</span></span>

- <span data-ttu-id="cf1ca-197">SharePoint の**ドキュメント ライブラリ、フォルダー、またはドキュメント セットに既定の保持ラベルを適用**することにより、この場所に保存するすべてのドキュメントに既定の保持ラベルが継承されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-197">**Apply a default retention label to a document library, folder, or document set** in SharePoint, so that all documents that are stored in that location inherit the default retention label.</span></span>

<span data-ttu-id="cf1ca-198">さらに、保持ラベルは、Microsoft 365 アプリとサービス全体でのメールとドキュメントの[レコード管理](records-management.md)をサポートします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-198">Additionally, retention labels support [records management](records-management.md) for email and documents across Microsoft 365 apps and services.</span></span> <span data-ttu-id="cf1ca-199">保持ラベルを使用して、コンテンツをレコードとして分類できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-199">You can use a retention label to classify content as a record.</span></span> <span data-ttu-id="cf1ca-200">この操作を行い、コンテンツがMicrosoft 365 に残っている場合、ラベルを変更または削除することはできません。また、コンテンツを編集または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-200">When this happens and the content remains in Microsoft 365, the label can't be changed or removed, and the content can't be edited or deleted.</span></span> 

<span data-ttu-id="cf1ca-201">保持ラベルは、[秘密度ラベル](sensitivity-labels.md)とは異なり、コンテンツが Microsoft 365 以外の場所に移動した場合は保持されません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-201">Retention labels, unlike [sensitivity labels](sensitivity-labels.md), do not persist if the content is moved outside Microsoft 365.</span></span>

<span data-ttu-id="cf1ca-202">テナントでサポートされる保持ラベルの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-202">There is no limit to the number of retention labels that are supported for a tenant.</span></span> <span data-ttu-id="cf1ca-203">ただし、10,000 はテナントでサポートされるポリシーの最大数であり、これらには、ラベルを適用するポリシー (保持ラベル ポリシーと自動適用アイテム保持ポリシー) とアイテム保持ポリシーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-203">However, 10,000 is the maximum number of policies that are supported for a tenant and these include the policies that apply the labels (retention label policies and auto-apply retention policies), as well as retention policies.</span></span>

#### <a name="classifying-content-without-applying-any-actions"></a><span data-ttu-id="cf1ca-204">アクションを適用しないでコンテンツを分類する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-204">Classifying content without applying any actions</span></span>

<span data-ttu-id="cf1ca-205">保持ラベルの主な目的はコンテンツを保持または削除することですが、保持やその他のアクションを有効にしないで保持ラベルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-205">Although the main purpose of retention labels is to retain or delete content, you can also use retention labels without turning on any retention or other actions.</span></span> <span data-ttu-id="cf1ca-206">この場合、テキスト ラベルとしてのみ保持ラベルを使用し、他のアクションは適用しません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-206">In this case, you can use a retention label simply as a text label, without enforcing any actions.</span></span>
  
<span data-ttu-id="cf1ca-207">たとえば、アクションを含まない "後で確認" という名前の保持ラベルを作成して適用し、後からそのコンテンツを見つけるためにそのラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-207">For example, you can create and apply a retention label named "Review later" with no actions, and then use that label to find that content later.</span></span>
  
![保持がオフになっている [ラベル設定] ページ](../media/retention-label-retentionoff.png)

#### <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="cf1ca-209">DLP ポリシーで保持ラベルを条件として使用する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-209">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="cf1ca-210">SharePoint のドキュメントのデータ損失防止 (DLP) ポリシーの条件として、保持ラベルを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-210">You can specify a retention label as a condition in a data loss prevention (DLP) policy for documents in SharePoint.</span></span> <span data-ttu-id="cf1ca-211">たとえば、指定された保持ラベルがドキュメントに適用されている場合はそのドキュメントが組織外に共有されないように、DLP ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-211">For example, configure a DLP policy to prevent documents from being shared outside the organization if they have a specified retention label applied to it.</span></span>

<span data-ttu-id="cf1ca-212">詳細については、「[DLP ポリシーでの条件としての保持ラベルの使用](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-212">For more information, see [Using a retention label as a condition in a DLP policy](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>

#### <a name="retention-labels-and-policies-that-apply-them"></a><span data-ttu-id="cf1ca-213">保持ラベルと保持ラベルを適用するポリシー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-213">Retention labels and policies that apply them</span></span>

<span data-ttu-id="cf1ca-214">保持ラベルは、独立した再利用可能な文書パーツです。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-214">Retention labels are independent, reusable building blocks.</span></span> <span data-ttu-id="cf1ca-215">保持ラベル ポリシーの主な目的は、保持ラベルのセットをグループ化して、ラベルを表示する場所を特定することです。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-215">The primary purpose of a retention label policy is to group a set of retention labels and specify the locations where you want those labels to appear.</span></span> <span data-ttu-id="cf1ca-216">そうすることにより、管理者とユーザーはラベルをそれらの場所のコンテンツに適用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-216">Then, admins and users can apply those labels to content in those locations.</span></span>
  
![ラベル、ラベル ポリシー、および場所の図](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
<span data-ttu-id="cf1ca-218">保持ラベルを発行すると、それらは保持ラベル ポリシーに含まれます。このポリシーを使用することで、管理者やユーザーは次の中から選択して保持ラベルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-218">When you publish retention labels, they're included in a retention label policy that make them available for admins and users to select:</span></span>

- <span data-ttu-id="cf1ca-219">1 つの保持ラベルを複数の保持ラベル ポリシーに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-219">A single retention label can be included in many retention label policies.</span></span>

- <span data-ttu-id="cf1ca-220">保持ラベル ポリシーは保持ラベルを発行する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-220">Retention label policies specify the locations to publish the retention labels.</span></span>

- <span data-ttu-id="cf1ca-221">1 つの場所を複数の保持ラベル ポリシーに含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-221">A single location can also be included in many retention label policies.</span></span>

<span data-ttu-id="cf1ca-222">保持ラベル ポリシーに加えて、1 つ以上の自動適用ポリシーを作成して、それぞれに保持ラベルを 1 つ指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-222">In addition to retention label policies, you can also create one or more auto-apply policies, each with a single retention label.</span></span> <span data-ttu-id="cf1ca-223">このポリシーを使うと、ポリシーで指定した条件が満たされた場合に、保持ラベルが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-223">With this policy, a retention label is automatically applied when conditions that you specify in the policy are met.</span></span> 

#### <a name="retention-label-policies-and-locations"></a><span data-ttu-id="cf1ca-224">保持ラベルのポリシーと場所</span><span class="sxs-lookup"><span data-stu-id="cf1ca-224">Retention label policies and locations</span></span>

<span data-ttu-id="cf1ca-225">保持ラベルの内容に応じて、多様な種類の保持ラベルをさまざまな場所に発行できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-225">Different types of retention labels can be published to different locations, depending on what the retention label does.</span></span>
  
| <span data-ttu-id="cf1ca-226">保持ラベルの種類</span><span class="sxs-lookup"><span data-stu-id="cf1ca-226">If the retention label is…</span></span> | <span data-ttu-id="cf1ca-227">ラベル ポリシーの適用先</span><span class="sxs-lookup"><span data-stu-id="cf1ca-227">Then the label policy can be applied to…</span></span> |
|:-----|:-----|
|<span data-ttu-id="cf1ca-228">管理者とエンド ユーザーに発行されたラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-228">Published to admins and end users</span></span>  <br/> |<span data-ttu-id="cf1ca-229">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-229">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
|<span data-ttu-id="cf1ca-230">機密情報の種類またはトレーニング可能な分類子に基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-230">Auto-applied based on sensitive information types or trainable classifiers</span></span>  <br/> |<span data-ttu-id="cf1ca-231">Exchange (すべてのメールボックスのみ)、SharePoint、OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf1ca-231">Exchange (all mailboxes only), SharePoint, OneDrive</span></span>  <br/> |
|<span data-ttu-id="cf1ca-232">クエリに基づいて自動適用されたラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-232">Auto-applied based on a query</span></span>  <br/> |<span data-ttu-id="cf1ca-233">Exchange、SharePoint、OneDrive、Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-233">Exchange, SharePoint, OneDrive, Microsoft 365 Groups</span></span>  <br/> |
   
<span data-ttu-id="cf1ca-234">Exchange の自動適用保持ラベルは、新しく送信されたメッセージ (転送中のデータ) のみに適用され、現在メールボックスにあるすべてのアイテム (保存データ) には適用されません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-234">In Exchange, auto-apply retention labels are applied only to messages newly sent (data in transit), not to all items currently in the mailbox (data at rest).</span></span> <span data-ttu-id="cf1ca-235">また、機密情報の種類やトレーニング可能な分類子の自動適用保持ラベルはすべてのメールボックスのみに適用でき、特定のメールボックスを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-235">Also, auto-apply retention labels for sensitive information types and trainable classifiers apply to all mailboxes; you can't select specific mailboxes.</span></span>
  
<span data-ttu-id="cf1ca-236">Exchange パブリック フォルダー、Skype、および Teams チャネルのメッセージとチャットは、保持ラベルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-236">Exchange public folders, Skype, and Teams channel messages and chats do not support retention labels.</span></span> <span data-ttu-id="cf1ca-237">これらの場所のコンテンツを保持または削除するには、代わりにアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-237">To retain and delete contain from these locations, use retention policies instead.</span></span>

#### <a name="only-one-retention-label-at-a-time"></a><span data-ttu-id="cf1ca-238">一度に 1 つの保持ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-238">Only one retention label at a time</span></span>

<span data-ttu-id="cf1ca-239">メールやドキュメントに一度に割り当てられる保持ラベルは 1 つのみです。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-239">An email or document can have only a single retention label assigned to it at a time:</span></span>
  
- <span data-ttu-id="cf1ca-240">管理者やエンド ユーザーが手動で割り当てた保持ラベルの場合、ユーザーは割り当てられている保持ラベルを削除または変更できます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-240">For retention labels assigned manually by admins or end users, people can remove or change the retention label that's assigned.</span></span>
    
- <span data-ttu-id="cf1ca-241">コンテンツに自動適用ラベルが割り当てられている場合は、このラベルを発行済みの保持ラベルで置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-241">If content has an auto-apply label assigned, this label can be replaced by a published retention label.</span></span>
    
- <span data-ttu-id="cf1ca-242">コンテンツに発行済みの保持ラベルが割り当てられている場合は、このラベルを自動適用ラベルで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-242">If content has a published retention label assigned, an auto-apply label cannot replace it.</span></span>
    
- <span data-ttu-id="cf1ca-243">自動適用ラベルを割り当てるルールが複数あり、コンテンツが複数のルールの条件を満たしている場合、最も古いルールの保持ラベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-243">If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the retention label for the oldest rule is assigned.</span></span>
    
<span data-ttu-id="cf1ca-244">保持ラベルが別の保持ラベルではなくどのように適用されるかを理解するには、ラベルを明示的に割り当てることと、ラベルを暗黙的に割り当てることの違いを理解することが役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-244">To understand how and why one retention label is applied rather than another, it's helpful to understand the difference between explicitly assign a label, and implicitly assigned a label:</span></span>

- <span data-ttu-id="cf1ca-245">ラベル ポリシーから適用された保持ラベルは明示的に割り当てられる</span><span class="sxs-lookup"><span data-stu-id="cf1ca-245">Retention labels applied from a label policy are explicitly assigned</span></span>
- <span data-ttu-id="cf1ca-246">自動適用ポリシーから自動的に適用された保持ラベルは、暗黙的に割り当てられる</span><span class="sxs-lookup"><span data-stu-id="cf1ca-246">Retention labels applied automatically from an auto-apply policy are implicitly assigned</span></span>

<span data-ttu-id="cf1ca-247">明示的に割り当てられた保持ラベルは、暗黙的に割り当てられた保持ラベルよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-247">An explicitly assigned retention label takes precedence over an implicitly assigned retention label.</span></span> <span data-ttu-id="cf1ca-248">詳細については、このページの「[保持の原則または優先順位](retention.md#the-principles-of-retention-or-what-takes-precedence)」のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-248">For more information, see the [The principles of retention, or what takes precedence?](retention.md#the-principles-of-retention-or-what-takes-precedence) section on this page.</span></span>

#### <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a><span data-ttu-id="cf1ca-249">コンテンツ検索を使用した特定の保持ラベルが適用されたすべてのコンテンツの検索</span><span class="sxs-lookup"><span data-stu-id="cf1ca-249">Using Content Search to find all content with a specific retention label applied to it</span></span>

<span data-ttu-id="cf1ca-250">ユーザーまたは自動適用によって保持ラベルがコンテンツに割り当てられた後、コンテンツ検索を使用して、特定の保持ラベルで分類されているすべてのコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-250">After retention labels are assigned to content, either by users or auto-applied, you can use content search to find all content that's classified with a specific retention label.</span></span>
  
<span data-ttu-id="cf1ca-251">コンテンツ検索を作成するとき、**コンプライアンス ラベル**の条件を選択し、完全な保持ラベル名を入力するか、ラベル名の一部を入力してワイルドカードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-251">When you create a content search, choose the **Compliance label** condition, and then enter the complete retention label name or part of the label name and use a wildcard.</span></span> <span data-ttu-id="cf1ca-252">詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-252">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
![コンプライアンス ラベルの条件](../media/compliance-label-condition.png)


## <a name="compare-capabilities-for-retention-policies-and-retention-labels"></a><span data-ttu-id="cf1ca-254">アイテム保持ポリシーと保持ラベルの機能比較</span><span class="sxs-lookup"><span data-stu-id="cf1ca-254">Compare capabilities for retention policies and retention labels</span></span>

<span data-ttu-id="cf1ca-255">次の表は、アイテム保持ポリシーと保持ラベルのどちらを使用するかを、機能に基づいて決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-255">Use the following table to help you identify whether to use a retention policy or retention label, based on capabilities.</span></span>

|<span data-ttu-id="cf1ca-256">機能</span><span class="sxs-lookup"><span data-stu-id="cf1ca-256">Capability</span></span>|<span data-ttu-id="cf1ca-257">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-257">Retention policy</span></span> |<span data-ttu-id="cf1ca-258">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="cf1ca-258">Retention label</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cf1ca-259">保持してから削除、保持のみ、削除のみを指定できる保持設定</span><span class="sxs-lookup"><span data-stu-id="cf1ca-259">Retention settings that can retain and then delete, retain-only, or delete-only</span></span> |<span data-ttu-id="cf1ca-260">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-260">Yes</span></span> |<span data-ttu-id="cf1ca-261">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-261">Yes</span></span> |
|<span data-ttu-id="cf1ca-262">サポートされるワークロード:</span><span class="sxs-lookup"><span data-stu-id="cf1ca-262">Workloads supported:</span></span> <br /><span data-ttu-id="cf1ca-263">- Exchange</span><span class="sxs-lookup"><span data-stu-id="cf1ca-263">- Exchange</span></span> <br /><span data-ttu-id="cf1ca-264">- SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf1ca-264">- SharePoint</span></span> <br /><span data-ttu-id="cf1ca-265">- OneDrive</span><span class="sxs-lookup"><span data-stu-id="cf1ca-265">- OneDrive</span></span> <br /><span data-ttu-id="cf1ca-266">- Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-266">- Microsoft 365 groups</span></span> <br /><span data-ttu-id="cf1ca-267">- Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf1ca-267">- Skype for Business</span></span> <br /><span data-ttu-id="cf1ca-268">- Teams</span><span class="sxs-lookup"><span data-stu-id="cf1ca-268">- Teams</span></span>|<br /> <span data-ttu-id="cf1ca-269">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-269">Yes</span></span> <br /> <span data-ttu-id="cf1ca-270">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-270">Yes</span></span> <br /> <span data-ttu-id="cf1ca-271">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-271">Yes</span></span> <br /> <span data-ttu-id="cf1ca-272">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-272">Yes</span></span> <br /> <span data-ttu-id="cf1ca-273">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-273">Yes</span></span> <br /> <span data-ttu-id="cf1ca-274">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-274">Yes</span></span> | <br /> <span data-ttu-id="cf1ca-275">はい (パブリック フォルダーを除く)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-275">Yes, except public folders</span></span> <br /> <span data-ttu-id="cf1ca-276">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-276">Yes</span></span> <br /> <span data-ttu-id="cf1ca-277">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-277">Yes</span></span> <br /> <span data-ttu-id="cf1ca-278">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-278">Yes</span></span> <br /> <span data-ttu-id="cf1ca-279">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-279">No</span></span> <br /> <span data-ttu-id="cf1ca-280">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-280">No</span></span>  |
|<span data-ttu-id="cf1ca-281">保持の自動適用</span><span class="sxs-lookup"><span data-stu-id="cf1ca-281">Retention applied automatically</span></span> | <span data-ttu-id="cf1ca-282">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-282">Yes</span></span> | <span data-ttu-id="cf1ca-283">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-283">Yes</span></span> |
|<span data-ttu-id="cf1ca-284">保持の手動適用</span><span class="sxs-lookup"><span data-stu-id="cf1ca-284">Retention applied manually</span></span> | <span data-ttu-id="cf1ca-285">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-285">No</span></span> | <span data-ttu-id="cf1ca-286">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-286">Yes</span></span> |
|<span data-ttu-id="cf1ca-287">エンド ユーザー向け UI の存在</span><span class="sxs-lookup"><span data-stu-id="cf1ca-287">UI presence for end users</span></span> | <span data-ttu-id="cf1ca-288">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-288">No</span></span> | <span data-ttu-id="cf1ca-289">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-289">Yes</span></span> |
|<span data-ttu-id="cf1ca-290">コンテンツが移動された場合の保持</span><span class="sxs-lookup"><span data-stu-id="cf1ca-290">Persists if the content is moved</span></span> | <span data-ttu-id="cf1ca-291">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-291">No</span></span> | <span data-ttu-id="cf1ca-292">はい (Microsoft 365 内)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-292">Yes, within Microsoft 365</span></span> |
|<span data-ttu-id="cf1ca-293">レコードとしてアイテムを宣言</span><span class="sxs-lookup"><span data-stu-id="cf1ca-293">Declare item as a record</span></span>| <span data-ttu-id="cf1ca-294">不要</span><span class="sxs-lookup"><span data-stu-id="cf1ca-294">No</span></span> | <span data-ttu-id="cf1ca-295">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-295">Yes</span></span> |
|<span data-ttu-id="cf1ca-296">ラベル作成時またはイベント発生時に保持期間を開始</span><span class="sxs-lookup"><span data-stu-id="cf1ca-296">Start the retention period when labeled or based on an event</span></span> | <span data-ttu-id="cf1ca-297">不要</span><span class="sxs-lookup"><span data-stu-id="cf1ca-297">No</span></span> | <span data-ttu-id="cf1ca-298">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-298">Yes</span></span> |
|<span data-ttu-id="cf1ca-299">処理確認</span><span class="sxs-lookup"><span data-stu-id="cf1ca-299">Disposition review</span></span> | <span data-ttu-id="cf1ca-300">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-300">No</span></span>| <span data-ttu-id="cf1ca-301">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-301">Yes</span></span> |
|<span data-ttu-id="cf1ca-302">廃棄の証明 (最大 7 年間)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-302">Proof of disposition for up to 7 years</span></span> | <span data-ttu-id="cf1ca-303">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-303">No</span></span> |<span data-ttu-id="cf1ca-304">はい (アイテムがレコードとして宣言されている場合)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-304">Yes, when item is declared a record</span></span>|
|<span data-ttu-id="cf1ca-305">保持対象のアイテムの特定</span><span class="sxs-lookup"><span data-stu-id="cf1ca-305">Identify items subject to retention:</span></span> <br /> <span data-ttu-id="cf1ca-306">- コンテンツ検索</span><span class="sxs-lookup"><span data-stu-id="cf1ca-306">- Content Search</span></span> <br /> <span data-ttu-id="cf1ca-307">- データ分類ページ、コンテンツ エクスプローラー、アクティビティ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-307">- Data classification page, content explorer, activity explorer</span></span> | <br /> <span data-ttu-id="cf1ca-308">不要</span><span class="sxs-lookup"><span data-stu-id="cf1ca-308">No</span></span> <br /> <span data-ttu-id="cf1ca-309">いいえ</span><span class="sxs-lookup"><span data-stu-id="cf1ca-309">No</span></span> | <br /> <span data-ttu-id="cf1ca-310">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-310">Yes</span></span> <br /> <span data-ttu-id="cf1ca-311">はい</span><span class="sxs-lookup"><span data-stu-id="cf1ca-311">Yes</span></span>|

<span data-ttu-id="cf1ca-312">アイテム保持ポリシーと保持ラベルの両方を補完的な保持方法として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-312">Note that you can use both retention policies and retention labels as complementary retention methods.</span></span> <span data-ttu-id="cf1ca-313">例:</span><span class="sxs-lookup"><span data-stu-id="cf1ca-313">For example:</span></span>

1. <span data-ttu-id="cf1ca-314">最終更新日から 5 年後にコンテンツを自動的に削除するアイテム保持ポリシーを作成して構成し、すべての OneDrive アカウントにそのポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-314">You create and configure a retention policy that automatically deletes content five years after it's last modified, and apply the policy to all OneDrive accounts.</span></span>

2. <span data-ttu-id="cf1ca-315">コンテンツを無期限に保持する保持ラベルを作成して構成し、すべての OneDrive アカウントに対して発行するラベル ポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-315">You create and configure a retention label that keeps content forever and add this to a label policy that you publish to all OneDrive accounts.</span></span> <span data-ttu-id="cf1ca-316">5 年間更新されない場合でも自動削除されないようにする必要のある特定のドキュメントに対して、このラベルを手動で適用する方法をユーザーに説明します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-316">You explain to users how to manually apply this label to specific documents that should be excluded from automatic deletion if not modified after five years.</span></span>

<span data-ttu-id="cf1ca-317">アイテム保持ポリシーと保持ラベルを組み合わせて使用する方法、および組み合わせて使用した場合の結果の確認方法の詳細については、保持の原則と優先順位について説明している次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-317">For more information about how retention policies and retention labels work together and how to determine their combined outcome, see the next section that explains the principles of retention and what takes precedence.</span></span>

## <a name="the-principles-of-retention-or-what-takes-precedence"></a><span data-ttu-id="cf1ca-318">保持の原則と優先順位</span><span class="sxs-lookup"><span data-stu-id="cf1ca-318">The principles of retention, or what takes precedence?</span></span>

<span data-ttu-id="cf1ca-319">コンテンツにアイテム保持ポリシーや保持ラベルがいくつか適用されており、それぞれのポリシーやラベルに異なるアクション (保持、削除、保持してから削除) や保持期間が指定されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-319">It's possible or even likely that content might have several retention policies and retention labels applied to it, each with a different action (retain, delete, or retain and then delete) and retention period.</span></span> <span data-ttu-id="cf1ca-320">優先順位</span><span class="sxs-lookup"><span data-stu-id="cf1ca-320">What takes precedence?</span></span> 

<span data-ttu-id="cf1ca-321">大まかに言えば、保持は削除より常に優先され、最長の保持期間が優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-321">At a high level, you can be assured that retention always takes precedence over deletion, and then the longest retention period wins.</span></span> 

<span data-ttu-id="cf1ca-322">とはいえ、組み合わせて使用する場合は他にも決定要因があります。結果を理解するため、次のフロー図を使用して説明します。この図の各レベルは、優先順位に従って上から下に配列されており、上位のレベルで結果が決定する場合は次のレベルには進みません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-322">However, there are a few more factors to throw into the mix, so use the following flow to understand the outcome where each level acts as a tie-breaker from top to bottom: If the outcome is determined by the first level, there's no need to progress to the next level, and so on.</span></span> <span data-ttu-id="cf1ca-323">そのレベルのルールで結果が決定しない場合のみ、フロー図の下位のレベルに進み、その保持設定の優先順位で結果を判断します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-323">Only if the outcome can't be determined by the rules for the level does the flow move down to the next level to determine the outcome for which retention settings take precedence.</span></span>

![保持の原則の図](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
<span data-ttu-id="cf1ca-325">4 つのレベルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-325">Explanation for the four different levels:</span></span>
  
1. <span data-ttu-id="cf1ca-326">**削除よりも保持が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-326">**Retention wins over deletion.**</span></span> <span data-ttu-id="cf1ca-327">3 年後に Exchange メールを削除するように構成されているアイテム保持ポリシーがあり、加えて 5 年間 Exchange メールを保持してから削除するように構成されている別のアイテム保持ポリシーもあるとします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-327">Suppose that one retention policy is configured to delete Exchange email after three years, but another retention policy is configured to retain Exchange email for five years and then delete it.</span></span> <span data-ttu-id="cf1ca-328">作成後 3 年に達するコンテンツはすべて削除され、ユーザーのビューから非表示になりますが、コンテンツが完全に削除される 5 年に達するまで、[回復可能なアイテム] フォルダーに保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-328">Any content that reaches three years old will be deleted and hidden from the users' view, but still retained in the Recoverable Items folder until the content reaches five years old, when it is permanently deleted.</span></span> 
2. <span data-ttu-id="cf1ca-329">**最長の保持期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-329">**The longest retention period wins.**</span></span> <span data-ttu-id="cf1ca-330">期間の異なる複数の保持設定がコンテンツに対して指定されている場合、そのコンテンツは最長の保持期間が終了するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-330">If content is subject to multiple retention settings that retain content for different periods of time, the content will be retained until the end of the longest retention period.</span></span>
    
3. <span data-ttu-id="cf1ca-331">**明示的に含める方が、暗黙的に含めるよりも優先されます。**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-331">**Explicit inclusion wins over implicit inclusion.**</span></span> <span data-ttu-id="cf1ca-332">これは、次のことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-332">This means:</span></span> 
    
    1. <span data-ttu-id="cf1ca-333">Exchange メールや OneDrive ドキュメントなど、ユーザーが保持設定を含む保持ラベルをアイテムに手動で割り当てた場合は、サイト レベルまたはメールボックス レベルで割り当てられているアイテム保持ポリシーや、ドキュメント ライブラリに割り当てられている既定の保持ラベルよりも、手動で割り当てたラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-333">If a retention label with retention settings is manually assigned by a user to an item, such as an Exchange email or OneDrive document, that retention label takes precedence over both a retention policy assigned at the site or mailbox level and a default retention label assigned to the document library.</span></span> <span data-ttu-id="cf1ca-334">たとえば、明示的な保持ラベルでは 10 年間コンテンツを保持するように構成され、サイトに割り当てられているアイテム保持ポリシーでは 5 年間のみコンテンツを保持するように構成されている場合、明示的な保持ラベルが優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-334">For example, if the explicit retention label is configured to retain content for ten years, but a retention policy assigned to the site is configured to retain content for only five years, the retention label takes precedence.</span></span> <span data-ttu-id="cf1ca-335">自動適用の保持ラベルは、Microsoft 365 によって自動的に適用されるため、明示的ではなく、暗黙的とされます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-335">Auto-applied retention labels are considered implicit rather than explicit, because they're applied automatically by Microsoft 365.</span></span>
    
    2. <span data-ttu-id="cf1ca-336">アイテム保持ポリシーに特定のユーザーのメールボックスまたは OneDrive のアカウントなどの特定の場所が含まれている場合、そのアイテム保持ポリシーは、すべてのユーザーのメールボックスまたは OneDrive のアカウントに適用されるが、そのユーザーのメールボックスを特に含まない別の保持ポリシーよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-336">If a retention policy includes a specific location, such as a specific user's mailbox or OneDrive account, that retention policy takes precedence over another retention policy that applies to all users' mailboxes or OneDrive accounts but doesn't specifically include that user's mailbox.</span></span>
    
4. <span data-ttu-id="cf1ca-337">**最短の削除期間が優先されます。**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-337">**The shortest deletion period wins.**</span></span> <span data-ttu-id="cf1ca-338">同様に、保持期間なしでコンテンツを削除する複数の保持設定が指定されている場合、そのコンテンツは最短保持期間の終了時に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-338">Similarly, if content is subject to multiple retention settings that delete content without a retention period, that content will be deleted at the end of the shortest retention period.</span></span> 

<span data-ttu-id="cf1ca-339">最後に、アイテム保持ポリシーや保持ラベルでは、電子情報開示のために保持しているコンテンツを完全に削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-339">Finally, a retention policy or retention label cannot permanently delete any content that's on hold for eDiscovery.</span></span> <span data-ttu-id="cf1ca-340">電子情報開示のための保持を解除すると、コンテンツは再びそのワークロードに対するセキュリティで保護された場所のクリーンアップ プロセスの対象になります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-340">When that hold is released, the content again becomes eligible for the cleanup process in the secured locations for the workload.</span></span>

## <a name="powershell-cmdlets-for-retention-policies-and-retention-labels"></a><span data-ttu-id="cf1ca-341">アイテム保持ポリシーと保持ラベルの PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="cf1ca-341">PowerShell cmdlets for retention policies and retention labels</span></span>

<span data-ttu-id="cf1ca-342">保持コマンドレットを使用するには、最初に [Office 365 セキュリティ/コンプライアンス センターの PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) に接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-342">To use the retention cmdlets, you must first [connect to the Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span> <span data-ttu-id="cf1ca-343">次に、次のいずれかのコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-343">Then, use any of the following cmdlets:</span></span>

- [<span data-ttu-id="cf1ca-344">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="cf1ca-344">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)

- [<span data-ttu-id="cf1ca-345">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="cf1ca-345">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)

- [<span data-ttu-id="cf1ca-346">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="cf1ca-346">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)

- [<span data-ttu-id="cf1ca-347">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="cf1ca-347">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)

- [<span data-ttu-id="cf1ca-348">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="cf1ca-348">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)

- [<span data-ttu-id="cf1ca-349">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="cf1ca-349">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)

- [<span data-ttu-id="cf1ca-350">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="cf1ca-350">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)

- [<span data-ttu-id="cf1ca-351">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="cf1ca-351">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)

- [<span data-ttu-id="cf1ca-352">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="cf1ca-352">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)

- [<span data-ttu-id="cf1ca-353">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="cf1ca-353">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)

- [<span data-ttu-id="cf1ca-354">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="cf1ca-354">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)

- [<span data-ttu-id="cf1ca-355">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="cf1ca-355">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)

- [<span data-ttu-id="cf1ca-356">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="cf1ca-356">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)

- [<span data-ttu-id="cf1ca-357">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="cf1ca-357">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)

## <a name="use-retention-policies-and-retention-labels-instead-of-older-features"></a><span data-ttu-id="cf1ca-358">以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-358">Use retention policies and retention labels instead of older features</span></span>

<span data-ttu-id="cf1ca-359">情報ガバナンスを目的として、Microsoft 365 のコンテンツをプロアクティブに保持または削除する必要がある場合は、次に示す以前の機能の代わりにアイテム保持ポリシーと保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-359">If you need to proactively retain or delete content in Microsoft 365 for information governance, we recommend that you use retention policies and retention labels instead of the following older features.</span></span> 
  
<span data-ttu-id="cf1ca-360">これらの以前の機能を現在使用している場合、それらもアイテム保持ポリシーおよび保持ラベルと並行して機能し続けます。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-360">If you currently use these older features, they will continue to work side-by-side with retention policies and retention labels.</span></span> <span data-ttu-id="cf1ca-361">ただし、今後はアイテム保持ポリシーと保持ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-361">However, we recommend that going forward, you use retention policies and retention labels instead.</span></span> <span data-ttu-id="cf1ca-362">それらは、Microsoft 365 全体でコンテンツの保持と削除の両方を集中管理する単一のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-362">They provide you with a single mechanism to centrally manage both retention and deletion of content across Microsoft 365.</span></span>

<span data-ttu-id="cf1ca-363">**Exchange Online の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-363">**Older features from Exchange Online:**</span></span>

- <span data-ttu-id="cf1ca-364">[インプレース ホールドと訴訟ホールド](https://go.microsoft.com/fwlink/?linkid=846124) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-364">[In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery hold)</span></span> 

- [<span data-ttu-id="cf1ca-365">Exchange Online メールボックスに適用されている保留の種類を特定する方法</span><span class="sxs-lookup"><span data-stu-id="cf1ca-365">How to identify the type of hold placed on an Exchange Online mailbox</span></span>](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- <span data-ttu-id="cf1ca-366">[メッセージング レコード管理 (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) とも呼ばれる、[保持タグおよびアイテム保持ポリシー](https://go.microsoft.com/fwlink/?linkid=846125) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-366">[Retention tags and retention policies](https://go.microsoft.com/fwlink/?linkid=846125), also known as [messaging records management (MRM)](https://go.microsoft.com/fwlink/?linkid=846126) (deletion only)</span></span>
    
<span data-ttu-id="cf1ca-367">「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-367">See also [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).</span></span>


<span data-ttu-id="cf1ca-368">**SharePoint と OneDrive の古い機能:**</span><span class="sxs-lookup"><span data-stu-id="cf1ca-368">**Older features from SharePoint and OneDrive:**</span></span>

- <span data-ttu-id="cf1ca-369">[電子情報開示センターでのコンテンツのケースへの追加とソースの保留リストへの配置](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (電子情報開示の保留リスト)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-369">[Add content to a case and place sources on hold in the eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery hold)</span></span> 
    
- <span data-ttu-id="cf1ca-370">[ドキュメント削除ポリシーの概要](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-370">[Document deletion policies](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (deletion only)</span></span>
    
- <span data-ttu-id="cf1ca-371">[インプレース レコード管理の構成](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (保持のみ)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-371">[Configuring in place records management](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (retention only)</span></span> 
    
- <span data-ttu-id="cf1ca-372">[サイトのクローズと削除のポリシーを使用する](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-372">[Use policies for site closure and deletion](https://support.microsoft.com/ja-JP/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (deletion only)</span></span> 
    
- <span data-ttu-id="cf1ca-373">[情報管理ポリシー](intro-to-info-mgmt-policies.md) (削除のみ)</span><span class="sxs-lookup"><span data-stu-id="cf1ca-373">[Information management policies](intro-to-info-mgmt-policies.md) (deletion only)</span></span>
     
<span data-ttu-id="cf1ca-374">以前に情報ガバナンスを目的として電子情報開示の保留のいずれかを使用したことがある場合は、予防的なコンプライアンスのために、代わりにアイテム保持ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-374">If you've previously used any of the eDiscovery holds for the purpose of information governance, for proactive compliance, use a retention policy instead.</span></span> <span data-ttu-id="cf1ca-375">電子情報開示は、保留リストのみに使用します。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-375">Use eDiscovery for holds only.</span></span>
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a><span data-ttu-id="cf1ca-376">アイテム保持ポリシーと SharePoint コンテンツ タイプ ポリシーまたは情報管理ポリシー</span><span class="sxs-lookup"><span data-stu-id="cf1ca-376">Retention policies and SharePoint content type policies or information management policies</span></span>

<span data-ttu-id="cf1ca-377">コンテンツ タイプ ポリシーまたは情報管理ポリシーの SharePoint サイトを構成して、リストまたはライブラリのコンテンツを保持している場合は、前者のポリシーは無視され、保持ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-377">If you have configured SharePoint sites for content type policies or information management policies to retain content for a list or library, those policies are ignored while a retention policy is in effect.</span></span> 

## <a name="related-information"></a><span data-ttu-id="cf1ca-378">関連情報</span><span class="sxs-lookup"><span data-stu-id="cf1ca-378">Related information</span></span>

- [<span data-ttu-id="cf1ca-379">SharePoint Online の制限</span><span class="sxs-lookup"><span data-stu-id="cf1ca-379">SharePoint Online Limits</span></span>](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [<span data-ttu-id="cf1ca-380">Microsoft Teams の制限事項と仕様</span><span class="sxs-lookup"><span data-stu-id="cf1ca-380">Limits and specifications for Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [<span data-ttu-id="cf1ca-381">SEC Rule 17a-4 に準拠する </span><span class="sxs-lookup"><span data-stu-id="cf1ca-381">Comply with SEC Rule 17a-4</span></span>](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a><span data-ttu-id="cf1ca-382">次の手順</span><span class="sxs-lookup"><span data-stu-id="cf1ca-382">Next steps</span></span>

<span data-ttu-id="cf1ca-383">アイテム保持ポリシーを作成する準備ができている場合は、「[アイテム保持ポリシーを作成して構成する](create-retention-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf1ca-383">If you are ready to create retention policies, see [Create and configure retention policies](create-retention-policies.md).</span></span>

<span data-ttu-id="cf1ca-384">保持ラベルを作成して適用するには:</span><span class="sxs-lookup"><span data-stu-id="cf1ca-384">To create and apply retention labels:</span></span>
- [<span data-ttu-id="cf1ca-385">アイテム保持ラベルを作成してアプリに適用する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-385">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="cf1ca-386">保持ラベルをコンテンツに自動的に適用する</span><span class="sxs-lookup"><span data-stu-id="cf1ca-386">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)
