---
title: Microsoft 365 データの不変性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Microsoft 365 が検出可能な形式でデータを保持して、法令遵守、内部ガバナンスの要件、および訴訟のリスクに対処する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c070eea4498aca89d7cdb8fea233d9b9596491a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691822"
---
# <a name="immutability-in-microsoft-365"></a><span data-ttu-id="5af20-103">Microsoft 365 での不変性</span><span class="sxs-lookup"><span data-stu-id="5af20-103">Immutability in Microsoft 365</span></span>

<span data-ttu-id="5af20-104">コンプライアンス、内部ガバナンスの要件、訴訟リスクによって、組織はメールと関連データを検出可能な形式で保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5af20-104">Regulatory compliance, internal governance requirements, or litigation risks require organizations to preserve email and associated data in a discoverable form.</span></span> <span data-ttu-id="5af20-105">システム内のすべてのデータは検出可能である必要があり、破棄または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5af20-105">All data in the system must be discoverable and none of it can be destroyed or altered.</span></span> <span data-ttu-id="5af20-106">業界標準の用語は、"不変" です。</span><span class="sxs-lookup"><span data-stu-id="5af20-106">The industry-standard term for this is "immutability."</span></span>

<span data-ttu-id="5af20-107">従来の不変処理方法では、電子メールメッセージを別の読み取り専用の保存場所に移動することによって動作します。</span><span class="sxs-lookup"><span data-stu-id="5af20-107">Traditional methods for immutability typically worked by moving email messages to a separate, read-only storage location.</span></span> <span data-ttu-id="5af20-108">このようなシステムは、証拠開示のためにメールボックスアイテムを保持することを目的としていますが、通常は日常のワークフローから保持されているアイテムを削除することによって、ユーザーの作業感に影響</span><span class="sxs-lookup"><span data-stu-id="5af20-108">While such systems serve the purpose of preserving mailbox items for discovery, they often affect the user experience by removing preserved items from the customary daily workflow.</span></span> <span data-ttu-id="5af20-109">IT 担当者にとって、この不変手法を使用するには、個別のサーバーとストレージインフラストラクチャを展開し、継続的に保守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5af20-109">For IT professionals, this immutability approach requires the deployment and ongoing maintenance of a separate server and storage infrastructure.</span></span> <span data-ttu-id="5af20-110">検出は、メールシステムの外部にあるツールを使用して実行され、関連する展開とメンテナンスのコストを含みます。</span><span class="sxs-lookup"><span data-stu-id="5af20-110">Discovery is performed with tools external to the mail system and includes associated deployment and maintenance costs.</span></span>

<span data-ttu-id="5af20-111">Microsoft 365 とそのサービスのアーカイブのインプレース保持ポリシー機能と保持ポリシー機能により、受信、内部、送信データの多くのクラスを保持して保持することができます。</span><span class="sxs-lookup"><span data-stu-id="5af20-111">Through in-place retention and preservation policy features of archiving in Microsoft 365 and its services, you can preserve and retain many classes of incoming, internal, and outgoing data.</span></span> <span data-ttu-id="5af20-112">保持されるデータには以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5af20-112">This includes:</span></span>

- <span data-ttu-id="5af20-113">受信メールと送信メールの通信データ</span><span class="sxs-lookup"><span data-stu-id="5af20-113">Inbound and outbound email communications</span></span>
- <span data-ttu-id="5af20-114">メール フォームまたはオンラインド共有キュメントに含まれている帳簿や記録</span><span class="sxs-lookup"><span data-stu-id="5af20-114">Books and records contained in email form or in shared online documents</span></span>
- <span data-ttu-id="5af20-115">会議出席依頼</span><span class="sxs-lookup"><span data-stu-id="5af20-115">Meeting requests</span></span>
- <span data-ttu-id="5af20-116">FAX</span><span class="sxs-lookup"><span data-stu-id="5af20-116">Faxes</span></span>
- <span data-ttu-id="5af20-117">インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="5af20-117">Instant messages</span></span>
- <span data-ttu-id="5af20-118">オンライン会議中に共有されたドキュメント</span><span class="sxs-lookup"><span data-stu-id="5af20-118">Documents shared during online meetings</span></span>
- <span data-ttu-id="5af20-119">ボイスメール</span><span class="sxs-lookup"><span data-stu-id="5af20-119">Voicemails</span></span>

<span data-ttu-id="5af20-120">さらに、Microsoft は、サードパーティのデータキャプチャおよび管理ソリューションとの統合により、他のソースからの [データのアーカイブ](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) を可能にするアドオン機能を開発しました。</span><span class="sxs-lookup"><span data-stu-id="5af20-120">In addition, Microsoft has developed add-on features to allow [archiving of data](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) from other sources through integration with third-party data capturing and management solutions.</span></span> <span data-ttu-id="5af20-121">サードパーティのデータがインポートされた後、Microsoft 365 のコンプライアンス機能をデータに適用することができます。次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="5af20-121">After third-party data is imported, you can apply Microsoft 365 compliance features to the data, including:</span></span>

- [<span data-ttu-id="5af20-122">訴訟ホールド</span><span class="sxs-lookup"><span data-stu-id="5af20-122">Litigation Hold</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)
- [<span data-ttu-id="5af20-123">インプレースの電子情報開示と保持</span><span class="sxs-lookup"><span data-stu-id="5af20-123">In-Place eDiscovery and Hold</span></span>](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)
- [<span data-ttu-id="5af20-124">コンプライアンス検索</span><span class="sxs-lookup"><span data-stu-id="5af20-124">Compliance Search</span></span>](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)
- [<span data-ttu-id="5af20-125">インプレース アーカイブ</span><span class="sxs-lookup"><span data-stu-id="5af20-125">In-Place Archiving</span></span>](https://docs.microsoft.com/microsoft-365/compliance/enable-archive-mailboxes)
- [<span data-ttu-id="5af20-126">メールボックスの監査</span><span class="sxs-lookup"><span data-stu-id="5af20-126">Mailbox auditing</span></span>](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)
- [<span data-ttu-id="5af20-127">アイテム保持ポリシー</span><span class="sxs-lookup"><span data-stu-id="5af20-127">Retention Policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

<span data-ttu-id="5af20-128">たとえば、メールボックスが訴訟ホールドの対象となっている場合、サードパーティのデータは保持されます。</span><span class="sxs-lookup"><span data-stu-id="5af20-128">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="5af20-129">インプレース電子情報開示またはコンプライアンス検索を使用して、サードパーティのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="5af20-129">You can search third-party data using In-Place eDiscovery or Compliance Search.</span></span> <span data-ttu-id="5af20-130">また、Microsoft データの場合と同じように、アーカイブポリシーとアイテム保持ポリシーをサードパーティデータに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5af20-130">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="5af20-131">Microsoft 365 でサードパーティのデータをアーカイブすることにより、組織は政府および規制ポリシーに準拠し続けることができます。</span><span class="sxs-lookup"><span data-stu-id="5af20-131">Archiving third-party data in Microsoft 365 helps your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="5af20-132">Microsoft 365 のアーカイブでは、有価証券取引委員会 (SEC) ルール 17a-4 (SEC) に準拠したストレージが提供されています。</span><span class="sxs-lookup"><span data-stu-id="5af20-132">Archiving in Microsoft 365 provides Securities and Exchange Commission (SEC) Rule 17a-4-compliant storage.</span></span> <span data-ttu-id="5af20-133">Microsoft 365 は、保持ロックを含む、インプレース保持ポリシーと保持ポリシーを使用して、書き換え不可で消去不可能な形式で収集されたすべてのデータの永続的なファイルを保持します。</span><span class="sxs-lookup"><span data-stu-id="5af20-133">Microsoft 365 preserves permanent files of all data collected in a non-rewriteable, non-erasable format using in-place retention policies and preservation policies, including preservation lock.</span></span>

<span data-ttu-id="5af20-134">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5af20-134">Specifically:</span></span>

- <span data-ttu-id="5af20-135">前述のアイテム保持ポリシーを使用して保存されたすべてのレコードは、通常のユーザーの purview から専用のストレージ領域に保持されます。</span><span class="sxs-lookup"><span data-stu-id="5af20-135">All records stored using the retention policies noted above are retained in a dedicated storage area out of the purview of the ordinary user.</span></span> <span data-ttu-id="5af20-136">許可されたユーザーのみが、これらのレコードにアクセスして検索できますが、変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5af20-136">Only authorized users can access and search these records, but cannot alter or erase them.</span></span>
- <span data-ttu-id="5af20-137">各アイテムのメタデータには、保持期間の計算に使用されるタイムスタンプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5af20-137">Metadata for each item includes a timestamp used in the calculation of retention duration.</span></span> <span data-ttu-id="5af20-138">新しいアイテムを受信または作成したときに、タイムスタンプが適用され、メタデータから変更または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="5af20-138">Timestamps are applied when a new item is received or created and cannot be modified or removed from the metadata.</span></span>
- <span data-ttu-id="5af20-139">Microsoft 365 のアーカイブを使用すると、ユーザーはさまざまなアイテム保持ポリシーを組み合わせ、アクションを保持して詳細なアイテム保持ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5af20-139">Archiving in Microsoft 365 allows users to combine different retention policies and hold actions to create granular retention policies.</span></span> <span data-ttu-id="5af20-140">これらのポリシーは、保持されるアイテムの種類または場所、および保持期間を定義します。</span><span class="sxs-lookup"><span data-stu-id="5af20-140">These policies define the type or location of the items preserved and the duration of preservation.</span></span>
- <span data-ttu-id="5af20-141">保持ロック機能を使用すると、ポリシーを制限されたポリシーにするかどうかをユーザーが選択できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5af20-141">The Preservation Lock feature allows users to choose whether to make the policy a restrictive policy.</span></span> <span data-ttu-id="5af20-142">制限付きポリシーを使用すると、すべてのユーザーがアイテム保持ポリシーを削除、無効化、または変更することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="5af20-142">A restrictive policy prohibits anyone from having the ability to remove, disable, or make any changes to the retention policy.</span></span> <span data-ttu-id="5af20-143">これは、保持ロックが有効になっている場合、無効にすることはできず、保持ポリシーによって収集された既存の保管担当者からのデータが保存期間中に上書き、変更、消去、または削除されるメカニズムは存在しないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="5af20-143">This means that once Preservation Lock is enabled, it cannot be disabled, and no mechanism will exist under which any data from existing custodians that has been collected by the retention policies in place may be overwritten, modified, erased, or deleted during the preservation period.</span></span> <span data-ttu-id="5af20-144">さらに、保持ロックで設定された保持期間を短縮または縮小することはできません。</span><span class="sxs-lookup"><span data-stu-id="5af20-144">Further, the hold period set by Preservation Lock may not be shortened or decreased.</span></span> <span data-ttu-id="5af20-145">しかし、前述したように、保存されたデータの保存期間を維持するために法的な要件がある場合は、延長される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5af20-145">It may, however, be lengthened, in the case of a legal requirement to continue retention of the stored data, as noted above.</span></span> <span data-ttu-id="5af20-146">保持ロックを使用すると、管理者または特定のコントロールアクセス権を持つユーザー以外は、その設定を変更したり、2003 365 保存されているデータを上書きまたは消去したりすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="5af20-146">Preservation Lock ensures that no one, not even administrators or those with certain control access, may change the settings or overwrite or erase data that has been stored, bringing archiving in Microsoft 365 in line with the guidance set forth in the 2003 Release of SEC Rule 17a-4.</span></span>

<span data-ttu-id="5af20-147">Microsoft 365 によって規制上の義務にどのように役立つかを理解するために、特にルール17a-4 の要件については、「Exchange Online のアーカイブ、SharePoint Online、OneDrive for Business、Skype for Business に関する [ホワイトペーパー](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5af20-147">To understand how Microsoft 365 helps you meet regulatory obligations, specifically in relation to Rule 17a-4 requirements, see the [whitepaper](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) that covers Exchange Online Archiving, SharePoint Online, OneDrive for Business, and Skype for Business.</span></span> <span data-ttu-id="5af20-148">ホワイトペーパーでは、SEC Rule 17a-4 の各要件に対して Microsoft 365 アーカイブの機能と機能の詳細な分析を行い、Microsoft 365 のアーカイブによってこれらの要件を満たすことができるようにすることについても説明します。</span><span class="sxs-lookup"><span data-stu-id="5af20-148">The whitepaper also provides an in-depth analysis of Microsoft 365 archiving features and functionalities against each of the requirements under SEC Rule 17a-4 and demonstrates to regulated customers how Microsoft 365 archiving can enable them to meet these requirements.</span></span>