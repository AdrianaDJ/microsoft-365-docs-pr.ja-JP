---
title: 管理ポータルにアクセスする
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
ms.author: jaimeo
author: jaimeo
ms.topic: article
audience: ITPro
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.openlocfilehash: deeced350ad867a374a486967c2cbd278ba91710
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519331"
---
# <a name="access-the-admin-portal"></a>管理ポータルにアクセスする

Microsoft Managed Desktop service へのゲートウェイは、Microsoft [Azure portal](https://portal.azure.com)です。 Azure ポータルを使用してカスタマイズする方法の詳細については、「 [azure portal のドキュメント](https://docs.microsoft.com/azure/azure-portal/)」を参照してください。 プレビューでは、microsoft [エンドポイントマネージャー](https://endpoint.microsoft.com/)で Microsoft Managed Desktop を検索することもできます。 このポータルのデバイス管理の機能についてよく知らない場合は、 [Microsoft エンドポイントマネージャーのドキュメント](https://docs.microsoft.com/mem/)を参照してください。

> [!NOTE]
> ただし、microsoft Managed Desktop を microsoft [エンドポイントマネージャー](https://endpoint.microsoft.com/) または [Azure portal](https://portal.azure.com)で選択した場合は、次のブラウザーがサポートされます。
> - Microsoft Edge (最新バージョン)
> - Microsoft Internet Explorer 11
> - Safari (最新バージョン、Mac のみ)
> - Chrome (最新バージョン)
> - Firefox (最新バージョン)

Azure portal または Microsoft エンドポイントマネージャーのいずれかで Microsoft 管理対象デスクトップ管理機能にアクセスするには、管理アカウントに特定のアクセス許可が必要です。 役割ベースのアクセス制御 (RBAC) を使用して、組織内のこれらの機能への管理者アクセスを管理することができます。 複数の Azure Active Directory (Azure AD) 管理者の役割および組み込みのカスタムの役割を使用すると、Microsoft 管理対象のデスクトップ管理ポータル内のさまざまな機能に、より詳細な制御を提供できます。 Azure Active Directory ロールの詳細については、「 [Azure Active directory での管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。 さまざまな Microsoft 製品およびサービスに適用される Azure AD 管理者の役割とは異なり、カスタムの役割は Microsoft マネージドデスクトップに固有のものであり、このサービスの管理機能へのアクセスのみを保証します。 管理者は、カスタムロールをユーザーごとに、または Azure AD 管理者ロールと組み合わせて、既存の管理者アカウントに Microsoft 管理されたデスクトップアクセス許可を追加することができます。

以下の各役割は、さまざまなレベルのアクセスを提供するために割り当てることができます。

|Azure AD の役割  |Microsoft マネージドデスクトップのアクセス許可  |
|---------|---------|
|グローバル管理者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルの **すべての機能に対する読み取りおよび書き込みアクセス許可を** 持ちます。         |
|グローバル閲覧者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルの **すべての機能に対して読み取り専用のアクセス許可を** 持ちます。         |
|Intune サービス管理者     |  この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルの **セキュリティに関連しない機能に対する読み取りおよび書き込みアクセス許可を** 持ちます。       |
|サービスサポート管理者     | この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルで **サポート要求を管理するため** の、セキュリティおよび書き込みアクセス許可に **関連しない機能に対する読み取り専用のアクセス許可を** 持ちます。         |
|セキュリティ管理者 | この役割を持つ管理者は、管理ポータルの Microsoft Managed Desktop の **すべての機能に対する読み取り専用のアクセス許可** と、 **セキュリティ関連の機能に対する書き込みアクセス** 許可を持ちます。 |
|セキュリティ閲覧者 |この役割を持つ管理者は、Microsoft Managed Desktop 管理ポータルの **すべての機能に対して読み取り専用のアクセス許可を** 持ちます。|

> [!IMPORTANT]
> グローバル管理者の役割のみが、Microsoft マネージドデスクトップに組織を *登録* するために必要なアクセス許可を持っています。 Azure Active Directory の役割によって、ユーザーアカウントにさまざまな Microsoft サービスの権限が付与されることに注意してください。 Microsoft マネージドデスクトップでの登録を完了した後は、他のタスクを実行するために必要な *最低限* の特権を持つ役割を常に使用する必要があります。

 
|カスタムロール  |Microsoft マネージドデスクトップのアクセス許可  |
|---------|---------|
|Microsoft Managed Desktop Service 管理者  | ユーザーに割り当てられている場合、この役割によって、Microsoft Managed Desktop 管理ポータルの **セキュリティに関連しない機能に対する管理者の読み取りおよび書き込みのアクセス許可** が付与されます。  |
|Microsoft Managed Desktop Service Reader | ユーザーに割り当てられている場合、この役割によって、Microsoft Managed Desktop 管理ポータルの **セキュリティに関連しない機能に対し** て、管理者の読み取り専用アクセス許可が付与されます。 |
|Microsoft Managed Desktop Security Manager |この役割は、ユーザーに割り当てられている場合、Microsoft Managed Desktop 管理ポータルの **セキュリティ関連機能に対してのみ、管理者の読み取りおよび書き込みアクセス許可** を付与します。   |

> [!NOTE]
> セキュリティ機能には、セキュリティ関連の通信、セキュリティ担当者の管理、セキュリティ関連のサポート要求の管理、セキュリティ関連レポートへのアクセスなどがあります。 

## <a name="assigning-roles-to-administrators"></a>管理者への役割の割り当て

Azure Active Directory の役割の割り当てに関するヘルプが必要な場合は、「 [Azure Active directory の管理者ロールのアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)」を参照してください。

組み込みの役割を簡単に管理するために、カスタム役割ごとにセキュリティグループが作成されています (たとえば、「モダン Workplace Roles –セキュリティマネージャー」)。 ユーザーをセキュリティグループのいずれかに割り当てるには、次の手順を実行します。
1.  Microsoft エンドポイントマネージャーポータルに移動する
2.  左側の [グループ] を選択します。
3.  モダンワークプレースの役割を検索し、割り当てる役割に関連付けられているグループを選択します。 
4.  左側の [メンバー] を選択し、コマンドバーで [+ メンバーの追加] を選択します。
5.  追加するユーザーの電子メールを入力します。 外部ユーザーの場合は、グループを割り当てる前に招待する必要があります。
6.  下部にある [選択] を選択します。

> [!NOTE]
> 役割の割り当てでは、セキュリティグループのネストは現在サポートされていません。 
