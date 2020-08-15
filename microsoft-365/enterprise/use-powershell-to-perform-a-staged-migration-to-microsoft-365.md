---
title: Microsoft 365 への段階的な移行に PowerShell を使用する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: PowerShell を使用して、Microsoft 365 への段階的な移行を使用して、時間の経過と共にソース電子メールシステムからコンテンツを移動する方法について説明します。
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691771"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a><span data-ttu-id="dd9f1-103">Microsoft 365 への段階的な移行に PowerShell を使用する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-103">Use PowerShell to perform a staged migration to Microsoft 365</span></span>

<span data-ttu-id="dd9f1-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="dd9f1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dd9f1-105">段階的な移行を使用して、ユーザーメールボックスのコンテンツをソースメールシステムから Microsoft 365 に移行することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 over time using a staged migration.</span></span>
  
<span data-ttu-id="dd9f1-106">この記事では、Exchange Online PowerShell を使用した段階的メール移行に関するタスクを順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-106">This article walks you through the tasks involved with for a staged email migration using Exchange Online PowerShell.</span></span> <span data-ttu-id="dd9f1-107">このトピックでは、 [段階的なメールの移行について理解しておく必要がある](https://go.microsoft.com/fwlink/p/?LinkId=536487)ことを、移行プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-107">The topic, [What you need to know about a staged email migration](https://go.microsoft.com/fwlink/p/?LinkId=536487), gives you an overview of the migration process.</span></span> <span data-ttu-id="dd9f1-108">記事の内容に満足いただけたら、段階的メール移行を使用して、あるメール システムから別のメール システムへのメールボックスの移行を開始してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd9f1-109">また、段階的な移行を実行するには、Exchange 管理センターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-109">You can also use the Exchange admin center to perform staged migration.</span></span> <span data-ttu-id="dd9f1-110">「 [Microsoft 365 へのメールの段階的な移行を実行する」を](https://go.microsoft.com/fwlink/p/?LinkId=536687)参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-110">See [Perform a staged migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536687).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="dd9f1-111">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="dd9f1-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="dd9f1-112">このタスクの予想所要時間:移行バッチの作成に 2 ～ 5 分。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="dd9f1-113">移行バッチ開始後の移行時間は、バッチ内のメールボックスの数、各メールボックスのサイズ、および使用可能なネットワーク容量によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="dd9f1-114">メールボックスを Microsoft 365 に移行するのにかかる時間に影響を与えるその他の要因の詳細については、「 [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="dd9f1-p104">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、トピック「[受信者のアクセス許可](https://go.microsoft.com/fwlink/p/?LinkId=534105)」の中の「移行」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Migration" entry in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="dd9f1-p105">Exchange Online PowerShell コマンドレットを使用するには、サインインしてコマンドレットをローカルの Windows PowerShell セッションにインポートする必要があります。手順については、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=534121)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p105">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session. See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="dd9f1-119">移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=534750)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="dd9f1-120">移行の手順</span><span class="sxs-lookup"><span data-stu-id="dd9f1-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-staged-migration"></a><span data-ttu-id="dd9f1-121">ステップ 1:段階的な移行を準備する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-121">Step 1: Prepare for a staged migration</span></span>

<span data-ttu-id="dd9f1-122">段階的な移行を使用してメールボックスを Microsoft 365 に移行する前に、Exchange 環境にいくつかの変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-122">Before you migrate mailboxes to Microsoft 365 by using a staged migration, there are a few changes you must make to your Exchange environment.</span></span>
  
 <span data-ttu-id="dd9f1-p106">**社内の Exchange Server** に Outlook Anywhere を構成する: メール移行サービスは、Outlook Anywhere (RPC over HTTP としても知られる) を使用して社内の Exchange Server に接続します。Exchange Server 2007 と Exchange 2003 における Outlook Anywhere の設定方法の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p106">**Configure Outlook Anywhere on your on-premises Exchange Server** The email migration service uses Outlook Anywhere (also known as RPC over HTTP), to connect to your on-premises Exchange Server. For information about how to set up Outlook Anywhere for Exchange Server 2007, and Exchange 2003, see the following:</span></span>
  
- <span data-ttu-id="dd9f1-125">「[Exchange 2007:Outlook Anywhere を有効にする方法](https://go.microsoft.com/fwlink/?LinkID=167210)」</span><span class="sxs-lookup"><span data-stu-id="dd9f1-125">[Exchange 2007: How to Enable Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=167210)</span></span>
    
- <span data-ttu-id="dd9f1-126">「[Exchange 2003 での Outlook Anywhere を構成する方法](https://go.microsoft.com/fwlink/?LinkID=167209)」</span><span class="sxs-lookup"><span data-stu-id="dd9f1-126">[How to configure Outlook Anywhere with Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="dd9f1-p107">Outlook Anywhere の構成には、信頼された証明機関 (CA) によって発行された証明書を使用する必要があります。Outlook Anywhere は、自己署名入りの証明書で構成することはできません。詳細については、「[Outlook Anywhere のために SSL を構成する方法](https://go.microsoft.com/fwlink/?LinkID=80875)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p107">You must use a certificate issued by a trusted certification authority (CA) with your Outlook Anywhere configuration. Outlook Anywhere can't be configured with a self-signed certificate. For more information, see [How to configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
 <span data-ttu-id="dd9f1-130">**オプション:Outlook Anywhere**を使用して Exchange 組織に接続できることを確認する: 接続設定をテストするには、次のいずれかの方法を試します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-130">**Optional: Verify that you can connect to your Exchange organization using Outlook Anywhere** Try one of the following methods to test your connection settings.</span></span>
  
- <span data-ttu-id="dd9f1-131">企業ネットワークの外部から Outlook を使用して社内の Exchange メールボックスに接続します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-131">Use Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
- <span data-ttu-id="dd9f1-132">[Microsoft リモート接続アナライザー](https://https://testconnectivity.microsoft.com/)を使用して、接続設定をテストします。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-132">Use the [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) to test your connection settings.</span></span> <span data-ttu-id="dd9f1-133">Outlook Anywhere (RPC over HTTP) または Outlook 自動検出テストを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-133">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
- <span data-ttu-id="dd9f1-134">Exchange Online PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-134">Run the following commands in Exchange Online PowerShell:</span></span>
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 <span data-ttu-id="dd9f1-135">**アクセス許可を設定** するオンプレミスの Exchange 組織 (移行管理者とも呼ばれます) に接続するために使用するオンプレミスのユーザーアカウントは、Microsoft 365 に移行する必要があるオンプレミスのメールボックスにアクセスするために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-135">**Set permissions** The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="dd9f1-136">このユーザー アカウントは、この手順の後半に記載する移行エンドポイント ([ステップ 3:移行エンドポイントを作成する](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint)) を作成して電子メール システムに接続するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-136">This user account is used when you connect to your email system by creating a migration endpoint later in this procedure ([Step 3: Create a migration endpoint](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).</span></span>
  
<span data-ttu-id="dd9f1-137">メールボックスを移行するために、管理者には次のアクセス許可セットのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-137">To migrate the mailboxes, the admin must have one of the following permission sets:</span></span>
  
- <span data-ttu-id="dd9f1-138">社内組織の Active Directory の **Domain Admins** グループのメンバーであること。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-138">Be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="dd9f1-139">or</span><span class="sxs-lookup"><span data-stu-id="dd9f1-139">or</span></span>
    
- <span data-ttu-id="dd9f1-140">社内の各メールボックスに **FullAccess** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-140">Be assigned the **FullAccess** permission for each on-premises mailbox and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
    <span data-ttu-id="dd9f1-141">or</span><span class="sxs-lookup"><span data-stu-id="dd9f1-141">or</span></span>
    
- <span data-ttu-id="dd9f1-142">ユーザー メールボックスを格納する社内のメールボックス データベースに **受信者** のアクセス許可が割り当てられ、社内のユーザー アカウントの **TargetAddress** プロパティを変更するための **WriteProperty** のアクセス許可が割り当てられていること。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-142">Be assigned the **Receive As** permission on the on-premises mailbox database that stores user mailboxes and the **WriteProperty** permission to modify the **TargetAddress** property on the on-premises user accounts.</span></span>
    
<span data-ttu-id="dd9f1-143">これらのアクセス許可を設定する方法については、「 [メールボックスを Microsoft 365 に移行するためのアクセス許可を割り当てる](https://go.microsoft.com/fwlink/?LinkId=521656)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-143">For instructions about how to set these permissions, see [Assign permissions to migrate mailboxes to Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656).</span></span>
  
 <span data-ttu-id="dd9f1-p110">**ユニファイド メッセージング (UM) を無効にする**: 移行する社内のメールボックスで UM がオンになっている場合は、移行前に UM をオフにします。移行の完了後に、メールボックスの UM をオンにします。操作手順については、「[ユーザーのユニファイド メッセージングを無効にする方法](https://go.microsoft.com/fwlink/?LinkId=521891)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p110">**Disable Unified Messaging (UM)** If UM is turned on for the on-premises mailboxes you're migrating, turn off UM before migration. Turn on UM for the mailboxes after migration is complete. For how-to steps, see[disable unified messaging](https://go.microsoft.com/fwlink/?LinkId=521891).</span></span>
  
 <span data-ttu-id="dd9f1-147">**ディレクトリ同期を使用して、Microsoft 365 で新しいユーザーを作成します。**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-147">**Use directory synchronization to create new users in Microsoft 365.**</span></span> <span data-ttu-id="dd9f1-148">ディレクトリ同期を使用して、Microsoft 365 組織のすべてのオンプレミスユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-148">You use directory synchronization to create all the on-premises users in your Microsoft 365 organization.</span></span>
  
<span data-ttu-id="dd9f1-p112">ユーザーの作成後にライセンスを付与する必要があります。ユーザーの作成後、ライセンスを追加するまでに 30 日間があります。ライセンスを追加する手順については、「[ステップ 8:移行後のタスクを完了する](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p112">You need to license the users after they're created. You have 30 days to add licenses after the users are created. For steps to add licenses, see [Step 8: Complete post-migration tasks](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).</span></span>
  
 <span data-ttu-id="dd9f1-152">Microsoft Azure Active Directory (Azure AD) 同期ツールまたは Microsoft Azure AD 同期サービスのいずれかを使用して、Microsoft 365 でオンプレミスユーザーを同期および作成できます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-152">You can use either the Microsoft Azure Active Directory (Azure AD) Synchronization Tool or the Microsoft Azure AD Sync Services  to synchronize and create your on-premises users in Microsoft 365.</span></span> <span data-ttu-id="dd9f1-153">メールボックスを Microsoft 365 に移行した後は、社内組織のユーザーアカウントを管理し、Microsoft 365 組織と同期されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-153">After mailboxes are migrated to Microsoft 365, you manage user accounts in your on-premises organization, and they're synchronized with your Microsoft 365 organization.</span></span> <span data-ttu-id="dd9f1-154">詳細については、「[ディレクトリ統合](https://go.microsoft.com/fwlink/?LinkId=521788) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-154">For more information, see[Directory Integration](https://go.microsoft.com/fwlink/?LinkId=521788) .</span></span>
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a><span data-ttu-id="dd9f1-155">ステップ 2:段階的な移行バッチ用の CSV ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-155">Step 2: Create a CSV file for a staged migration batch</span></span>

<span data-ttu-id="dd9f1-156">Microsoft 365 に移行する社内メールボックスのユーザーを特定した後、コンマ区切り値 (CSV) ファイルを使用して移行バッチを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-156">After you identify the users whose on-premises mailboxes you want to migrate to Microsoft 365, you use a comma separated value (CSV ) file to create a migration batch.</span></span> <span data-ttu-id="dd9f1-157">CSV ファイルの各行 (Microsoft 365 で移行を実行するために使用されます) には、社内メールボックスに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-157">Each row in the CSV file—used by Microsoft 365 to run the migration—contains information about an on-premises mailbox.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dd9f1-158">段階的な移行を使用して Microsoft 365 に移行できるメールボックスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-158">There isn't a limit for the number of mailboxes that you can migrate to Microsoft 365 using a staged migration.</span></span> <span data-ttu-id="dd9f1-159">移行バッチ用の CSV ファイルに含めることができる行数は、最大 2,000 行までです。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-159">The CSV file for a migration batch can contain a maximum of 2,000 rows.</span></span> <span data-ttu-id="dd9f1-160">2,000 を超えるメールボックスを移行するには、追加の CSV ファイルを作成し、各ファイルを使用して新しい移行バッチを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-160">To migrate more than 2,000 mailboxes, create additional CSV files and use each file to create a new migration batch.</span></span> 
  
 <span data-ttu-id="dd9f1-161">**サポートされている属性**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-161">**Supported attributes**</span></span>
  
<span data-ttu-id="dd9f1-p116">段階的な移行用の CSV ファイルは、次の 3 つの属性をサポートします。CSV ファイルの各行はメールボックスに対応し、各属性の値を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p116">The CSV file for a staged migration supports the following three attributes. Each row in the CSV file corresponds to a mailbox and must contain a value for each of these attributes.</span></span>
  
|<span data-ttu-id="dd9f1-164">**属性**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-164">**Attribute**</span></span>|<span data-ttu-id="dd9f1-165">**説明**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-165">**Description**</span></span>|<span data-ttu-id="dd9f1-166">**必須**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-166">**Required?**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd9f1-167">EmailAddress</span><span class="sxs-lookup"><span data-stu-id="dd9f1-167">EmailAddress</span></span>  <br/> |<span data-ttu-id="dd9f1-168">プライマリ SMTP 電子メール アドレス (たとえば、社内メールボックスの場合は pilarp@contoso.com など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-168">Specifies the primary SMTP email address, for example, pilarp@contoso.com, for on-premises mailboxes.</span></span>  <br/> <span data-ttu-id="dd9f1-169">Microsoft 365 のユーザー Id ではなく、オンプレミスのメールボックスのプライマリ SMTP アドレスを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-169">Use the primary SMTP address for on-premises mailboxes and not user IDs from the Microsoft 365.</span></span> <span data-ttu-id="dd9f1-170">たとえば、オンプレミスのドメインが contoso.com という名前で、Microsoft 365 の電子メールドメインが service.contoso.com という名前の場合は、CSV ファイルの電子メールアドレスに contoso.com ドメイン名を使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-170">For example, if the on-premises domain is named contoso.com but the Microsoft 365 email domain is named service.contoso.com, you would use the contoso.com domain name for email addresses in the CSV file.</span></span>  <br/> |<span data-ttu-id="dd9f1-171">必須</span><span class="sxs-lookup"><span data-stu-id="dd9f1-171">Required</span></span>  <br/> |
|<span data-ttu-id="dd9f1-172">Password</span><span class="sxs-lookup"><span data-stu-id="dd9f1-172">Password</span></span>  <br/> |<span data-ttu-id="dd9f1-173">新しい Microsoft 365 メールボックスに設定するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-173">The password to be set for the new Microsoft 365 mailbox.</span></span> <span data-ttu-id="dd9f1-174">Microsoft 365 組織に適用されるパスワード制限は、CSV ファイルに含まれるパスワードにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-174">Any password restrictions that are applied to your Microsoft 365 organization also apply to the passwords included in the CSV file.</span></span>  <br/> |<span data-ttu-id="dd9f1-175">省略可能</span><span class="sxs-lookup"><span data-stu-id="dd9f1-175">Optional</span></span>  <br/> |
|<span data-ttu-id="dd9f1-176">ForceChangePassword</span><span class="sxs-lookup"><span data-stu-id="dd9f1-176">ForceChangePassword</span></span>  <br/> |<span data-ttu-id="dd9f1-177">ユーザーが新しい Microsoft 365 メールボックスに初めてサインインするときにパスワードを変更する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-177">Specifies whether a user must change the password the first time they sign in to their new Microsoft 365 mailbox.</span></span> <span data-ttu-id="dd9f1-178">このパラメーターの値には **True** または **False** を使用してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-178">Use **True** or **False** for the value of this parameter.</span></span> <br/> <span data-ttu-id="dd9f1-179">> [!NOTE]> Active Directory フェデレーション サービス (AD FS) 以上を社内組織に展開してシングル サインオン (SSO) ソリューションを実装した場合、 **ForceChangePassword** 属性の値には **False** を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-179">> [!NOTE]> If you've implemented a single sign-on (SSO) solution by deploying Active Directory Federation Services (AD FS) or greater in your on-premises organization, you must use **False** for the value of the **ForceChangePassword** attribute.</span></span>          |<span data-ttu-id="dd9f1-180">省略可能</span><span class="sxs-lookup"><span data-stu-id="dd9f1-180">Optional</span></span>  <br/> |
   
 <span data-ttu-id="dd9f1-181">**CSV ファイル形式**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-181">**CSV file format**</span></span>
  
<span data-ttu-id="dd9f1-182">以下に、CSV ファイルの形式の例を示します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-182">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="dd9f1-183">この例では、3つのオンプレミスメールボックスが Microsoft 365 に移行されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-183">In this example, three on-premises mailboxes are migrated to Microsoft 365.</span></span>
  
<span data-ttu-id="dd9f1-p121">CSV ファイルの最初の行、つまりヘッダー行には、後続の行で指定される属性 (つまり、フィールド) の名前が示されます。各属性名はコンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p121">The first row, or header row, of the CSV file lists the names of the attributes, or fields, specified in the rows that follow. Each attribute name is separated by a comma.</span></span>
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

<span data-ttu-id="dd9f1-p122">ヘッダー行の下の各行は個々のユーザーを表します。これらの行には、そのユーザーのメールボックスを移行するための情報が含まれます。各行の属性値は、ヘッダー行の属性名と同じ順序で並んでいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p122">Each row under the header row represents one user and supplies the information that will be used to migrate the user's mailbox. The attribute values in each row must be in the same order as the attribute names in the header row.</span></span> 
  
<span data-ttu-id="dd9f1-p123">CSV ファイルの作成には、任意のテキスト エディターや Excel などのアプリケーションを使用します。ファイルは .csv ファイルまたは .txt ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p123">Use any text editor, or an application like Excel , to create the CSV file. Save the file as a .csv or .txt file.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd9f1-p124">CSV ファイルに非 ASCII 文字や特殊文字が含まれている場合は、UTF-8 などの Unicode エンコードで CSV ファイルを保存してください。アプリケーションによっては、コンピューターのシステム ロケールが CSV ファイルで使用されている言語と一致するときに、CSV ファイルを UTF-8 などの Unicode エンコードで保存した方が簡単な場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p124">If the CSV file contains non-ASCII or special characters, save the CSV file with UTF-8 or other Unicode encoding. Depending on the application, saving the CSV file with UTF-8 or other Unicode encoding can be easier when the system locale of the computer matches the language used in the CSV file.</span></span> 
  
### <a name="step-3-create-a-migration-endpoint"></a><span data-ttu-id="dd9f1-192">ステップ 3:移行エンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-192">Step 3: Create a migration endpoint</span></span>
<span data-ttu-id="dd9f1-193"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-193"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="dd9f1-194">電子メールを正常に移行するには、Microsoft 365 が接続して、ソースメールシステムと通信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-194">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="dd9f1-195">これを行うために、Microsoft 365 では移行エンドポイントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-195">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="dd9f1-196">PowerShell を使用して Outlook Anywhere 移行エンドポイントを作成するには、段階的な移行で、最初に[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=534121)を行います。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-196">To create an Outlook Anywhere migration endpoint by using PowerShell, for staged migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="dd9f1-197">移行コマンドの完全な一覧については、「[移動と移行のコマンドレット](https://go.microsoft.com/fwlink/p/?LinkId=534750)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-197">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="dd9f1-198">Exchange Online PowerShell に "StagedEndpoint" という Outlook Anywhere 移行エンドポイントを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-198">To create an Outlook Anywhere migration endpoint called "StagedEndpoint" in Exchange Online PowerShell, run the following commands:</span></span>
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

<span data-ttu-id="dd9f1-199">**New-MigrationEndpoint** コマンドレットの詳細については、「[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-199">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dd9f1-p126">**New-MigrationEndpoint** コマンドレットで **-TargetDatabase** オプションを使用することによって、使用するサービスに対してデータベースを指定することができます。それ以外の場合、データベースは、管理メールボックスが配置されている Active Directory フェデレーション サービス (AD FS) 2.0 サイトからランダムに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p126">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option. Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="dd9f1-202">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-202">Verify it worked</span></span>

<span data-ttu-id="dd9f1-203">Exchange Online PowerShell で、次のコマンドを実行して "StagedEndpoint" 移行エンドポイントに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-203">In Exchange Online PowerShell, run the following command to display information about the "StagedEndpoint" migration endpoint:</span></span>
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a><span data-ttu-id="dd9f1-204">ステップ 4:段階的な移行のバッチを作成および開始する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-204">Step 4: Create and start a stage migration batch</span></span>
<span data-ttu-id="dd9f1-205"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-205"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="dd9f1-p127">Exchange Online PowerShell の **New-MigrationBatch** コマンドレットを使用すると、一括移行の移行バッチを作成できます。 _AutoStart_ パラメーターを含めると、移行バッチを作成して自動的に開始できます。また、別の方法として、 **Start-MigrationBatch** コマンドレットを使用することにより、移行バッチを作成して後で手動で開始できます。この例では、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p127">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration. You can create a migration batch and start it automatically by including the _AutoStart_ parameter. Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet. This example creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

<span data-ttu-id="dd9f1-p128">この例でも、"StagedBatch1" という移行バッチを作成して、前の例で作成した移行エンドポイントを使用します。 _AutoStart_ パラメーターが含まれていないため、移行バッチは移行ダッシュボードで、または **Start-MigrationBatch** コマンドレットを使用して手動で開始する必要があります。前述のように、一度に存在できる一括移行バッチは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-p128">This example also creates a migration batch called "StagedBatch1" and uses the migration endpoint that was created in the previous step. Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet. As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="dd9f1-213">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-213">Verify it worked</span></span>

<span data-ttu-id="dd9f1-214">Exchange Online PowerShell で次のコマンドを実行すると、「StagedBatch1」に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-214">Run the following command in Exchange Online PowerShell to display information about the "StagedBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

<span data-ttu-id="dd9f1-215">また、次のコマンドを実行すると、バッチが開始されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-215">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

<span data-ttu-id="dd9f1-216">**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-216">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a><span data-ttu-id="dd9f1-217">ステップ 5:社内メールボックスをメールが有効なユーザーに変換する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-217">Step 5: Convert on-premises mailboxes to mail-enabled users</span></span>
<span data-ttu-id="dd9f1-218"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-218"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="dd9f1-219">メールボックスのバッチが正常に移行されたら、何らかの方法でユーザーが各自のメールにアクセスできるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-219">After you have successfully migrated a batch of mailboxes, you need some way to let users get to their mail.</span></span> <span data-ttu-id="dd9f1-220">メールボックスが移行されたユーザーには、オンプレミスのメールボックスと Microsoft 365 の両方があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-220">A user whose mailbox has been migrated now has both a mailbox on-premises and one in Microsoft 365.</span></span> <span data-ttu-id="dd9f1-221">Microsoft 365 のメールボックスを持つユーザーは、オンプレミスのメールボックスで新着メールの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-221">Users who have a mailbox in Microsoft 365 will stop receiving new mail in their on-premises mailbox.</span></span> 
  
<span data-ttu-id="dd9f1-222">移行が完了していないため、すべてのユーザーに電子メールの Microsoft 365 を送信する準備ができていません。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-222">Because you are not done with your migrations, you are not yet ready to direct all users to Microsoft 365 for their email.</span></span> <span data-ttu-id="dd9f1-223">両方のメールボックスを持つユーザーに対してはどのようにすれば良いでしょうか。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-223">So what do you do for those people who have both?</span></span> <span data-ttu-id="dd9f1-224">既に移行済みの社内メールボックスをメールが有効なユーザーに変更することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-224">What you can do is change the on-premises mailboxes that you've already migrated to mail-enabled users.</span></span> <span data-ttu-id="dd9f1-225">メールボックスをメールが有効なユーザーに変更する場合は、オンプレミスのメールボックスに移動するのではなく、電子メールに対して Microsoft 365 をユーザーに指示することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-225">When you change from a mailbox to a mail-enabled user, you can direct the user to Microsoft 365 for their email instead of going to their on-premises mailbox.</span></span> 
  
<span data-ttu-id="dd9f1-226">オンプレミスのメールボックスをメールが有効なユーザーに変換するもう1つの重要な理由は、プロキシアドレスをメールが有効なユーザーにコピーすることによって、Microsoft 365 メールボックスからのプロキシアドレスを保持することです。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-226">Another important reason to convert on-premises mailboxes to mail-enabled users is to retain proxy addresses from the Microsoft 365 mailboxes by copying proxy addresses to the mail-enabled users.</span></span> <span data-ttu-id="dd9f1-227">これにより、Active Directory を使用して社内組織からクラウドベースのユーザーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-227">This lets you manage cloud-based users from your on-premises organization by using Active Directory.</span></span> <span data-ttu-id="dd9f1-228">また、すべてのメールボックスを Microsoft 365 に移行した後に、オンプレミスの Exchange Server 組織を使用停止にした場合、メールが有効なユーザーにコピーしたプロキシアドレスは、オンプレミスの Active Directory に残ります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-228">Also, if you decide to decommission your on-premises Exchange Server organization after all mailboxes are migrated to Microsoft 365, the proxy addresses you've copied to the mail-enabled users will remain in your on-premises Active Directory.</span></span>
    
### <a name="step-6-delete-a-staged-migration-batch"></a><span data-ttu-id="dd9f1-229">ステップ 6:段階的な移行バッチを削除する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-229">Step 6: Delete a staged migration batch</span></span>
<span data-ttu-id="dd9f1-230"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-230"><a name="BK_Endpoint"> </a></span></span>

 <span data-ttu-id="dd9f1-231">移行バッチ内のすべてのメールボックスが正常に移行された場合、バッチ内の社内メールボックスをメールが有効なユーザーに変換した後に、段階的な移行バッチを削除する準備が整います。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-231">After all mailboxes in a migration batch have been successfully migrated, and you've converted the on-premises mailboxes in the batch to mail-enabled users, you're ready to delete a staged migration batch.</span></span> <span data-ttu-id="dd9f1-232">メールが移行バッチ内の Microsoft 365 メールボックスに転送されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-232">Be sure to verify that mail is being forwarded to the Microsoft 365 mailboxes in the migration batch.</span></span> <span data-ttu-id="dd9f1-233">段階的な移行バッチを削除すると、移行サービスによって、移行バッチに関連するすべてのレコードがクリーンアップされて移行バッチが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-233">When you delete a staged migration batch, the migration service cleans up any records related to the migration batch and deletes the migration batch.</span></span>
  
<span data-ttu-id="dd9f1-234">Exchange Online PowerShell で "StagedBatch1" 移行バッチを削除するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-234">To delete the "StagedBatch1" migration batch in Exchange Online PowerShell, run the following command.</span></span>
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

<span data-ttu-id="dd9f1-235">**Remove-MigrationBatch** コマンドレットの詳細については、「[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-235">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="dd9f1-236">機能していることを確認する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-236">Verify it worked</span></span>

<span data-ttu-id="dd9f1-237">Exchange Online PowerShell で次のコマンドを実行すると、"IMAPBatch1" に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-237">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch StagedBatch1
```

<span data-ttu-id="dd9f1-238">このコマンドによって、状態が **Removing** の移行バッチが返されるか、移行バッチが見つからず、削除されたことの確認を求めるエラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-238">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="dd9f1-239">**Get-MigrationBatch** コマンドレットの詳細については、「[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-239">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a><span data-ttu-id="dd9f1-240">Step7: Microsoft 365 ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dd9f1-240">Step7: Assign licenses to Microsoft 365 users</span></span>
<span data-ttu-id="dd9f1-241"><a name="BK_Endpoint"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-241"><a name="BK_Endpoint"> </a></span></span>

<span data-ttu-id="dd9f1-242">ライセンスを割り当てることにより、移行されたアカウントの Microsoft 365 ユーザーアカウントをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-242">Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.</span></span> <span data-ttu-id="dd9f1-243">ライセンスを割り当てないと、猶予期間 (30 日) が終了したときにメールボックスが無効になります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-243">If you don't assign a license, the mailbox is disabled when the grace period (30 days) ends.</span></span> <span data-ttu-id="dd9f1-244">Microsoft 365 管理センターでライセンスを割り当てるには、「 [ライセンスの割り当てまたは割り当て解除](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-244">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="dd9f1-245">ステップ 8:移行後のタスクを完了する</span><span class="sxs-lookup"><span data-stu-id="dd9f1-245">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="dd9f1-246"><a name="BK_Postmigration"> </a></span><span class="sxs-lookup"><span data-stu-id="dd9f1-246"><a name="BK_Postmigration"> </a></span></span>

- <span data-ttu-id="dd9f1-247">**ユーザーが各自のメールボックスに簡単にアクセスできるように、自動検出 DNS レコードを作成します。**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-247">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="dd9f1-248">すべてのオンプレミスメールボックスが Microsoft 365 に移行された後、Microsoft 365 組織の自動検出 DNS レコードを構成して、ユーザーが Outlook およびモバイルクライアントを使用して新しい Microsoft 365 メールボックスに簡単に接続できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-248">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="dd9f1-249">この新しい自動検出 DNS レコードは、Microsoft 365 組織に使用しているのと同じ名前空間を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-249">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="dd9f1-250">たとえば、クラウドベースの名前空間が cloud.contoso.com の場合、作成する必要のある自動検出 DNS レコードは autodiscover.cloud.contoso.com となります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-250">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="dd9f1-251">Microsoft 365 では CNAME レコードを使用して、Outlook およびモバイルクライアントの自動検出サービスを実装しています。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-251">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="dd9f1-252">自動検出 CNAME レコードには以下の情報が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-252">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="dd9f1-253">**エイリアス:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="dd9f1-253">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="dd9f1-254">**ターゲット:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dd9f1-254">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="dd9f1-255">詳細については、「 [ドメインを接続するための DNS レコードを追加する](https://go.microsoft.com/fwlink/p/?LinkId=535028)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-255">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="dd9f1-256">**社内の Exchange サーバーの使用を停止します。**</span><span class="sxs-lookup"><span data-stu-id="dd9f1-256">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="dd9f1-257">すべての電子メールが Microsoft 365 メールボックスに直接ルーティングされていることを確認し、オンプレミスの電子メール組織を管理する必要がなくなったか、SSO ソリューションの実装を計画していない場合は、サーバーから Exchange をアンインストールし、オンプレミスの Exchange 組織を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-257">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing an SSO solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="dd9f1-258">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd9f1-258">For more information, see the following:</span></span>
    
  - <span data-ttu-id="dd9f1-259">「[Exchange 2010 の変更または削除](https://go.microsoft.com/fwlink/?LinkId=217936)」</span><span class="sxs-lookup"><span data-stu-id="dd9f1-259">[Modify or Remove Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)</span></span>
    
  - <span data-ttu-id="dd9f1-260">「[Exchange 2007 組織を削除する方法](https://go.microsoft.com/fwlink/?LinkID=100485)」</span><span class="sxs-lookup"><span data-stu-id="dd9f1-260">[How to Remove an Exchange 2007 Organization](https://go.microsoft.com/fwlink/?LinkID=100485)</span></span>
    
  - <span data-ttu-id="dd9f1-261">「[Exchange Server 2003 をアンインストールする方法](https://go.microsoft.com/fwlink/?LinkID=56561)」</span><span class="sxs-lookup"><span data-stu-id="dd9f1-261">[How to Uninstall Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)</span></span>
    
