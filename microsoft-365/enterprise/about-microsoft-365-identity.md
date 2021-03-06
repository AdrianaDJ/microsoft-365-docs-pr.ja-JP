---
title: Microsoft 365 identity モデルと Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: クラウドのみまたはハイブリッドの id モデルを使用して、Microsoft 365 の Azure AD ユーザー id サービスを管理する方法について説明します。
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327953"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 identity モデルと Azure Active Directory

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 では、Azure Active Directory (Azure AD) を使用して、microsoft 365 サブスクリプションに含まれているクラウドベースのユーザー id と認証サービスを使用して、Microsoft 365 の id と認証を管理しています。 Id インフラストラクチャを正しく構成することは、組織の Microsoft 365 のユーザーアクセスとアクセス許可を管理するために不可欠です。

開始する前に、Microsoft 365 の ID モデルと認証の概要についてこのビデオをご覧ください。

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

最初の計画の選択は、Microsoft 365 の id モデルです。

## <a name="microsoft-365-identity-models"></a>Microsoft 365 id モデル

ユーザーアカウントを計画するには、まず、Microsoft 365 で2つの id モデルを理解する必要があります。 組織の id は、クラウド内でのみ管理できます。または、オンプレミスの Active Directory ドメインサービス (AD DS) の id を維持して、ユーザーが Microsoft 365 cloud services にアクセスするときの認証に使用することができます。  

ここでは、2種類の id と、それらのユーザーにとって最適なものと利点を示します。

| 属性 | クラウド専用 ID | ハイブリッド ID |
|:-------|:-----|:-----|
| **定義** | ユーザーアカウントは、Microsoft 365 サブスクリプションの Azure AD テナントにのみ存在します。 | ユーザーアカウントが AD DS に存在し、Microsoft 365 サブスクリプションの Azure AD テナントにもコピーがあります。 Azure AD のユーザーアカウントには、既にハッシュされた AD DS ユーザーアカウントのパスワードが含まれている場合もあります。 |
| **Microsoft 365 でユーザー資格情報を認証する方法** | Microsoft 365 サブスクリプションの Azure AD テナントは、クラウド id アカウントを使用して認証を実行します。 | Microsoft 365 サブスクリプションの Azure AD テナントは、認証プロセスを処理するか、またはユーザーを別の id プロバイダーにリダイレクトします。 |
| **最適シナリオ** | 社内の AD DS を必要としない、または必要としない組織。 | AD DS または別の id プロバイダーを使用している組織。 |
| **最大のメリット** | 簡単に使用できます。 その他のディレクトリツールやサーバーは必要ありません。 | ユーザーは、オンプレミスまたはクラウドベースのリソースにアクセスするときに同じ資格情報を使用できます。 |
||||

## <a name="cloud-only-identity"></a>クラウド専用 ID

クラウド専用の id は、Azure AD のみに存在するユーザーアカウントを使用します。 クラウドのみの id は、通常、オンプレミスサーバーを持たない小規模な組織、または AD DS を使用してローカル id を管理しない小規模な組織で使用されます。 

ここでは、クラウド専用の id の基本的なコンポーネントを示します。
 
![クラウド専用の id の基本的なコンポーネント](../media/about-microsoft-365-identity/cloud-only-identity.png)

オンプレミスとリモート (オンライン) の両方のユーザーは、Azure AD のユーザーアカウントとパスワードを使用して、Microsoft 365 クラウドサービスにアクセスします。 Azure AD は、保存されたユーザーアカウントとパスワードに基づいてユーザー資格情報を認証します。

### <a name="administration"></a>管理
ユーザーアカウントは Azure AD にのみ格納されるので、 [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/add-users/) や [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)などのツールを使用してクラウド id を管理します。 

## <a name="hybrid-identity"></a>ハイブリッド ID

ハイブリッド id は、オンプレミスの AD DS で開始され、Microsoft 365 サブスクリプションの Azure AD テナントにコピーを持つアカウントを使用します。 ただし、ほとんどの変更は1つの方法でのみフローします。 AD DS ユーザーアカウントに加えた変更は、Azure AD のコピーと同期されます。 しかし、新しいユーザーアカウントなどの Azure AD のクラウドベースのアカウントに加えられた変更は、AD DS と同期されません。

Azure AD Connect は、継続的なアカウント同期を提供します。 オンプレミスのサーバー上で実行され、AD DS の変更を確認し、それらの変更を Azure AD に転送します。 Azure AD Connect は、同期されているアカウントをフィルター処理する機能と、パスワードハッシュ同期 (PHS) と呼ばれるユーザーパスワードのハッシュバージョンを同期するかどうかを指定する機能を提供します。

ハイブリッド id を実装すると、オンプレミスの AD DS が、アカウント情報の権限のあるソースになります。 これは、ほとんどがオンプレミスの管理タスクを実行することを意味します。これは、Azure AD に同期されます。 

ハイブリッド id のコンポーネントを次に示します。

![ハイブリッド id のコンポーネント](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD テナントには、AD DS アカウントのコピーがあります。 この構成では、オンプレミスのユーザーと Microsoft 365 cloud services にアクセスするリモートユーザーの両方が Azure AD に対して認証されます。

>[!Note]
>ハイブリッド id のユーザーアカウントを同期するには、常に Azure AD Connect を使用する必要があります。 ライセンスの割り当てとグループ管理、アクセス許可の構成、およびユーザーアカウントに関連するその他の管理タスクを実行するには、Azure AD の同期されたユーザーアカウントが必要です。
>

### <a name="administration"></a>管理

元のユーザーアカウントと権限のあるユーザーアカウントは、オンプレミスの AD DS に格納されているので、AD DS を管理するのと同じツールを使用して id を管理します。 

Microsoft 365 管理センターまたは Microsoft 365 の PowerShell を使用して、Azure AD で同期されたユーザーアカウントを管理することはありません。

## <a name="next-step"></a>次の手順

クラウド専用の id モデルが必要な場合は、「 [cloud only identity](cloud-only-identities.md)」を参照してください。

ハイブリッド id モデルが必要な場合は、「 [ハイブリッド id](plan-for-directory-synchronization.md)」を参照してください。


## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise の概要](microsoft-365-overview.md)
