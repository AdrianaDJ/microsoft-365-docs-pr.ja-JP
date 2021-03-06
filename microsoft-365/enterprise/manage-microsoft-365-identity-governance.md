---
title: Microsoft 365 identity ガバナンスを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 identity ガバナンス機能の使用方法について説明します。
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370348"
---
# <a name="manage-microsoft-365-identity-governance"></a>Microsoft 365 identity ガバナンスを管理する

Identity Governance とは、従業員の生産性を確保するのに重要な資産へのアクセスを保護、監視、監査することです。 たとえば、Identity Governance を使用すると、適切なユーザーが正しいリソースにアクセスできるようになり、時間の経過と共にアクセス権が変更されたかどうかを判断できます。

詳細については、「 [Azure Active Directory の id ガバナンスの概要 (AZURE AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)」を参照してください。

## <a name="set-up-azure-ad-access-reviews"></a>Azure AD アクセス レビューを設定する

Azure AD のアクセスレビューを使用すると、ユーザーのアクセスを確認して、適切な人物だけがアクセスできるようにすることができます。 例:

- 新しい従業員が組織に参加すると、生産性を高めるのに適切なアクセス権が必要になります。
- 従業員が他のチーム、場所、または部門に移動するときに、必要に応じて、以前のチーム、場所、または部門へのアクセス権を確保するようにする必要があります。
- 従業員またはゲストが組織を離れたら、アクセスが削除されるようにする必要があります。

これは、ユーザー アカウントに過剰なアクセス権があるかどうかを判断するために、組織がセキュリティ監査の対象になる場合に特に重要です。業界や地域の規制に違反した場合、罰金が発生する可能性があります。

詳細については、「 [access のレビューの概要](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)」を参照してください。

さまざまなアクセス レビューの種類を構成するには、次の記事を参照してください。

- [グループとアプリ](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD ロール](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure リソース ロール](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Azure AD 受給管理の設定

Wiht Azure AD 受給管理では、アクセス要求ワークフロー、アクセス割り当て、レビュー、および有効期限を自動化することで、id とアクセスのライフサイクルをスケールで管理できます。

従業員は、ジョブを実行するためにさまざまなグループ、アプリケーション、およびサイトにアクセスする必要があります。 要件の変更、新しいアプリケーションの追加、またはユーザーに対する追加のアクセス許可が必要になるため、このアクセスを管理するのは困難です。 他の組織と共同作業を行う場合は、他の組織内のユーザーが組織のリソースにアクセスする必要があるかどうかを確認することはできません。また、外部ユーザーには、組織が使用しているアプリケーション、グループ、またはサイトがわからない場合があります。

Azure AD 受給管理は、内部および外部ユーザーのグループ、アプリケーション、および SharePoint サイトへのアクセスをより効率的に管理するのに役立ちます。
 
詳細については、「 [AZURE AD 資格情報管理の概要](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)」を参照してください。
