---
title: セキュリティで保護された電子メールの推奨ポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: 電子メールのポリシーと構成を適用する方法に関する、Microsoft が推奨するポリシーについて説明します。
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: f2d3b9180ad5ab58e92812ed7b2d4f7ba07e2971
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357111"
---
# <a name="policy-recommendations-for-securing-email"></a>電子メールをセキュリティで保護するためのポリシーの推奨事項

この記事では、推奨される id とデバイスアクセスポリシーを実装して、先進認証および条件付きアクセスをサポートする組織の電子メールと電子メールクライアントを保護する方法について説明します。 このガイダンスは、 [一般的な id とデバイスのアクセスポリシー](identity-access-policies.md) を基に作成されており、さらにいくつかの推奨事項も含まれています。

これらの推奨事項は、ニーズの粒度 ( **基準**、 **機密**、 **高規制**) に基づいて適用できる、セキュリティと保護の3つの異なる層に基づいています。 これらのセキュリティ層と、以下の推奨事項で参照されている推奨されるクライアントのオペレーティング システムの詳細については、[推奨されるセキュリティ ポリシーと構成の概要](microsoft-365-policies-configurations.md)に関するページを参照してください。

これらの推奨事項では、ユーザーがモバイルデバイスの iOS および Android 用の Outlook を含むモダンメールクライアントを使用する必要があります。 IOS および Android 用の Outlook は、Office 365 の最適な機能をサポートします。 これらのモバイル Outlook アプリは、モバイル使用をサポートし、他の Microsoft クラウドセキュリティ機能と連携するセキュリティ機能を備えた設計も行われています。 詳細については、「 [iOS および Android 用の OUTLOOK FAQ](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)」を参照してください。

## <a name="update-common-policies-to-include-email"></a>一般的なポリシーを更新して電子メールを含める

電子メールを保護するために、次の図は、共通 id およびデバイスアクセスポリシーから更新するポリシーを示しています。

[![Teams およびその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[この画像のより大きいバージョンを表示する](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Exchange Online の新しいポリシーを追加して、ActiveSync クライアントをブロックすることに注意してください。 これにより、Outlook mobile が強制的に使用されます。

ポリシーの設定時に Exchange Online と Outlook がポリシーのスコープに含まれていた場合は、ActiveSync クライアントをブロックするために新しいポリシーを作成するだけでよいことになります。 次の表に記載されているポリシーを確認し、推奨される追加を行うか、またはこれらが既に含まれていることを確認します。 各ポリシーは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)の関連する構成手順にリンクします。

|保護レベル|Policies|詳細情報|
|---|---|---|
|**Baseline**|[サインインリスクが *中* または *高* の場合は MFA を必須にする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|
||[先進認証をサポートしないクライアントはブロックする](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|クラウドアプリの割り当てに Exchange Online を含める|
||[アプリデータ保護ポリシーを適用する](identity-access-policies.md#apply-app-data-protection-policies)|Outlook がアプリの一覧に含まれていることを確認してください。 各プラットフォーム (iOS、Android、Windows) のポリシーを更新してください。|
||[承認済みアプリとアプリ保護を必要とする](identity-access-policies.md#require-approved-apps-and-app-protection)|クラウドアプリの一覧に Exchange Online を含める|
||[準拠 PC が必要](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|クラウドアプリの一覧に Exchange Online を含める|
||[ActiveSync クライアントをブロックする](#block-activesync-clients)|この新しいポリシーを追加する|
|**機密**|[サインインリスクが *低*、*中*、*高* のときに MFA を必要とする](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|
||[準拠 *して* いる pc とモバイルデバイスが必要](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|クラウドアプリの一覧に Exchange Online を含める|
|**厳しく規制**|[*常に* MFA が必要](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|クラウドアプリの割り当てに Exchange Online を含める|
|

## <a name="block-activesync-clients"></a>ActiveSync クライアントをブロックする

このポリシーでは、ActiveSync クライアントが他の条件付きアクセスポリシーをバイパスできないようにします。 ポリシー構成は、ActiveSync クライアントにのみ適用されます。 [ **[アプリ保護ポリシーを必須](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** にする] を選択すると、このポリシーによって ActiveSync クライアントがブロックされます。 このポリシーの作成の詳細については、「 [条件付きアクセスでのクラウドアプリケーションへのアクセスにアプリ保護ポリシーが必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)」を参照してください。

- 「 [シナリオ 1: Office 365 アプリは、アプリ保護ポリシーを使用して承認済みアプリを必要](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)とする」の「手順 2: exchange Online の Azure AD 条件付きアクセスポリシーを構成する」を参照してください。これにより、exchange ActiveSync クライアントは、基本認証を活用して exchange online に接続することができなくなります。

認証ポリシーを使用して [基本認証を無効](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)にすることもできます。これにより、すべてのクライアントアクセス要求で先進認証を使用することが強制されます。

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Web 上の Outlook から Exchange Online へのアクセスを制限する

ユーザーが umnanaged デバイス上の Outlook on the web から添付ファイルをダウンロードする機能を制限できます。 これらのデバイスのユーザーは、ファイルをリークしてデバイスに格納することなく、Office Online を使用してこれらのファイルを表示および編集できます。 また、ユーザーが管理されていないデバイスで添付ファイルを表示することを禁止することもできます。

それらのステップは次のとおりです。

1. [Exchange Online リモート PowerShell セッションに接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)します。
2. OWA メールボックスポリシーをまだ持っていない場合は、 [新しい-Owam/boxpolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy) コマンドレットを使用して作成します。
3. 添付ファイルの表示を許可するが、ダウンロードしない場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. 添付ファイルをブロックする場合は、次のコマンドを使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Azure ポータルで、次の設定を使用して新しい条件付きアクセスポリシーを作成します。

   **割り当て** \>[ **ユーザーとグループ**]: 該当するユーザーとグループを選択して、対象と除外を行います。

   **割り当て** \>**クラウドアプリまたはアクション** \>**クラウドアプリ** \>**含める** \>**アプリの選択**: **Office 365 Exchange Online** の選択

   **アクセス制御** \>**セッション**: [**アプリの強制制限の使用**] を選択します。

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>IOS および Android デバイスで Outlook を使用する必要があることを要求する

IOS および Android デバイスのユーザーが、iOS および Android 用の Outlook を使用して、職場または学校のコンテンツにのみアクセスできるようにするには、それらの可能性のあるユーザーを対象とする条件付きアクセスポリシーが必要です。

このポリシーを構成する手順については、「 [iOS および Android 用の Outlook を使用して、メッセージのグループ作業アクセスを管理]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)する」を参照してください。

## <a name="set-up-message-encryption"></a>メッセージの暗号化をセットアップする

新しい Office 365 Message Encryption (OME) 機能を使用すると、Azure Information Protection の保護機能を活用できるため、組織は、保護された電子メールを任意のデバイス上のすべてのユーザーと簡単に共有できます。 ユーザーは、保護されたメッセージを他の Microsoft 365 組織や、Outlook.com、Gmail、その他の電子メールサービスを使用しないお客様との間で送受信することができます。

詳細については、「 [Office の新しい365メッセージ暗号化機能をセットアップ](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)する」を参照してください。

## <a name="next-steps"></a>次の手順

![手順 4: Microsoft 365 クラウドアプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

次の条件付きアクセスポリシーを構成します。

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
