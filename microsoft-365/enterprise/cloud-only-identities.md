---
title: Microsoft 365 クラウドのみの id
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Microsoft 365 サブスクリプションがクラウド専用の id を使用しているときに、ユーザーとグループを作成する方法について説明します。
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327929"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 クラウドのみの id

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

クラウド専用の id を使用すると、すべてのユーザー、グループ、および連絡先が、Microsoft 365 サブスクリプションの Azure Active Directory (Azure AD) テナントに格納されます。 ここでは、クラウド専用の id の基本的なコンポーネントを示します。
 
![クラウド専用の id の基本コンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

組織内のユーザーとユーザーアカウントは、さまざまな方法で分類できます。 たとえば、一部は従業員で、恒久的な状態になっています。 一部のベンダー、請負業者、またはパートナーは、一時的な状態になっています。 ユーザーアカウントを持たない外部ユーザーも、対話とコラボレーションをサポートするために特定のサービスやリソースへのアクセスを引き続き付与する必要があります。 次に、例を示します。

- テナント アカウントは、組織内でクラウド サービスのライセンスを付与したユーザーを表します。

- B2B (Business to Busines) アカウントは、コラボレーションへの参加のために招待された組織外部のユーザーを表します。

組織内のユーザーの種類の株価を取得します。 グループ化とは たとえば、組織に対して、レベルの高い機能または目的によってユーザーをグループ化することができます。

また、一部のクラウド サービスを、ユーザー アカウントを持たない組織外のユーザーと共有できます。この場合、このような外部ユーザーのグループも指定する必要があります。

Azure AD のグループは、クラウド環境の管理を簡素化するいくつかの目的に使用できます。 たとえば、Azure AD グループでは、次のことを行うことができます。

- グループベースのライセンスを使用して、Microsoft 365 のライセンスをメンバーとして追加されるとすぐに、自動的にユーザーアカウントに割り当てます。
- ユーザーアカウントの属性 (部署名など) に基づいて、ユーザーアカウントを特定のグループに動的に追加します。
- サービスとしてのソフトウェア (SaaS) アプリケーションのユーザーを自動的にプロビジョニングし、多要素認証 (MFA) やその他の条件付きアクセスポリシーを使用してそれらのアプリケーションへのアクセスを保護します。
- SharePoint Online チームサイトのアクセス許可とアクセス許可のレベルをプロビジョニングします。

## <a name="next-steps-for-cloud-only-identity"></a>クラウド専用の id の次の手順

- [ユーザー アカウントを管理する](manage-microsoft-365-accounts.md)
- [ユーザー アカウントにライセンスを割り当てる](assign-licenses-to-user-accounts.md)
- [グループとグループメンバーシップを管理する](manage-microsoft-365-groups.md)
- [ユーザーアカウントのパスワードを管理する](manage-microsoft-365-passwords.md)
