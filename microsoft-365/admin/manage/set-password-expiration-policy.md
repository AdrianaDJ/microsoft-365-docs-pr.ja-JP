---
title: 組織のパスワード有効期限ポリシーを設定します。
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: Microsoft 365 管理センターで組織のパスワード有効期限ポリシーを設定する方法について説明します。
ms.openlocfilehash: 39726846d591b2d1f72a89a7dc59038c726a8e80
ms.sourcegitcommit: 21c3e44862854c74e4008cfb661840f069c6b709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787524"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>組織のパスワード有効期限ポリシーを設定します。

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-worldwide)」を参照してください。

::: moniker-end

## <a name="before-you-begin"></a>開始する前に

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。 これらの手順を完了するには、Microsoft 365 の管理者アカウントでサインインする必要があります。 [管理者アカウントとは](../admin-overview/admin-overview.md)。

これらの手順を実行するには、[グローバル管理者またはパスワード管理者](../add-users/about-admin-roles.md)としてログインしている必要があります。

ユーザーの場合は、自分のパスワードを期限なしに設定する権限はありません。 職場または学校のテクニカル サポートに、この記事の手順を実行するように依頼してください。

管理者は、ユーザー パスワードを一定の日数が経過したら期限切れにするか、パスワードの有効期限が切れないように設定することができます。

## <a name="set-password-expiration-policy"></a>パスワードの有効期限ポリシーを設定する

> [!Tip]
> 既定では、パスワードの有効期限は 90 日に設定されています。 最近の研究では、強制的なパスワードの変更はメリットよりデメリットの方が大きいことが強く示唆されています。 ハッカーが簡単に推測できる方法で、より弱いパスワードの選択、パスワードの再利用、または古いパスワードの更新をユーザーに促します。 パスワードを無期限に設定する場合は、[多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)を有効にすることをお勧めします。

特定の時間が経過するとユーザーのパスワードが期限切れになるように設定する場合は、以下の手順に従います。
> [!IMPORTANT]
> [グローバル管理者](../add-users/about-admin-roles.md)のみ次の手順を実行できます。
  
1. 管理センターで、[ **設定** ] \> [ **組織の設定** ] の順に移動します。

2. [<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページに移動します。
 グローバル管理者でない場合は、[セキュリティとプライバシー] オプションは表示されません。
  
3. [ **パスワードの有効期限ポリシー** ] を選択します。
  
4. ユーザーがパスワードを変更する必要がないようにするには、[ **数日後にユーザーのパスワードが期限切れになるように設定する** ] の横のチェックボックスを選択します。
  
5. パスワードの有効期限が切れる頻度を入力します。 14 〜 730 の日数を選択します。
  
6. 2 つ目のボックスに、パスワードが期限切れになる前にユーザーに通知する日数を入力して、[ **保存** ] を選択します。 日数を 1 から 30 から選びます。

7. ユーザーのパスワードの有効期限が切れた場合は、画面の右下隅に通知が表示されます。
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>パスワードの有効期限機能に関する重要事項
  
- Outlook アプリのみを使用するユーザーには、キャッシュで有効期限が切れるまで Microsoft 365 パスワードのリセットは強制されません。これは、実際に期限が切れた日から数日経過することがあります。管理者レベルでは、これに対する回避策はありません。

## <a name="prevent-last-password-from-being-used-again"></a>最後に使用したパスワードの再使用を禁止する

ユーザーが古いパスワードを再使用できないようにするには、オンプレミスの Active Directory (AD) でパスワードの履歴の記録を適用します。 詳細については、[「カスタムパスワードポリシーを作成する 」](https://docs.microsoft.com/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)を参照してください。

Azure AD では、ユーザーがパスワードを変更する場合、前回のパスワードは使用できません。 パスワード ポリシーは、Azure AD で直接作成および管理されるすべてのユーザーアカウントに適用されます。 このパスワード ポリシーは変更できません。 詳細については、「[Azure AD のパスワード ポリシー](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)」を参照してください。

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>オンプレミスの Active Directory から Azure AD (Microsoft 365) へユーザー パスワード ハッシュを同期する

この記事は、クラウド専用ユーザー (Azure AD) の有効期限ポリシーを設定するユーザーを対象にしています。 パスワード ハッシュ同期、パススルー認証、ADFSなどのオンプレミス フェデレーションを使用するハイブリッド ID ユーザーには適用されません。
  
ユーザー パスワード ハッシュをオンプレミスの AD から Azure AD に同期する方法については、「[Implement password hash synchronization with Azure AD Connect sync (Azure AD Connect 同期でパスワード ハッシュ同期を実装する)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Azure Active Directory のパスワード ポリシーとアカウントの制限

Azure Active Directory には、その他のパスワード ポリシーと制限を設定できます。 詳細については、「[Azure Active Directory のパスワード ポリシーとアカウントの制限](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy)」を確認してください。

## <a name="update-password-policy"></a>パスワードポリシーの更新

Set-MsolPasswordPolicy コマンドレットは、指定されたドメインまたはテナントのパスワードポリシーを更新します。 2つの設定が必要です。まず、パスワードを変更するまでの有効期間を指定します。2番目に、パスワードの有効期限が近づいているという最初の通知をユーザーが受け取るときにトリガーされる、パスワードの有効期限までの日数を示します。

特定のドメインまたはテナントのパスワードポリシーを更新する方法については、[「Set-MsolPasswordPolicy」](https://docs.microsoft.com/powershell/module/msonline/set-msolpasswordpolicy?view=azureadps-1.0)を参照してください。

## <a name="related-content"></a>関連コンテンツ

[ユーザーが自分でパスワードをリセットできるようにする](../add-users/let-users-reset-passwords.md)

[パスワードをリセットする](../add-users/reset-passwords.md)