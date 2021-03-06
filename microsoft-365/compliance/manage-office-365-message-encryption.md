---
title: Office 365 Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Office 365 Message Encryption (OME) の設定を終了したら、いくつかの方法で展開をカスタマイズする方法について説明します。
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815434"
---
# <a name="manage-office-365-message-encryption"></a>Office 365 Message Encryption

Office 365 Message Encryption (OME) の設定を終了すると、いくつかの方法で展開の構成をカスタマイズできます。 たとえば、1回限りのパスコードを有効にするかどうかを構成したり、Outlook on the web の [ **暗号化** ] ボタンを表示したりすることができます。 この記事のタスクでは、その方法について説明します。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>Google、Yahoo、Microsoft アカウントの受信者がこれらのアカウントを使用して Office 365 メッセージ暗号化ポータルにサインインできるかどうかを管理する

新しい Office 365 メッセージ暗号化機能をセットアップすると、組織内のユーザーは組織外の受信者にメッセージを送信できるようになります。 受信者が Google account、Yahoo アカウント、Microsoft アカウントなどの *ソーシャル id* を使用している場合、受信者はソーシャル ID で OME ポータルにサインインできます。 必要に応じて、受信者がソーシャル Id を使用して OME ポータルにサインインすることを許可しないようにすることもできます。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>受信者がソーシャル Id を使用して OME ポータルにサインインできるかどうかを管理するには
  
1. [リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。

2. 次のように、指定された引数を指定して、OMEConfiguration/コマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   たとえば、ソーシャル Id を無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   ソーシャル Id を有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>Office 365 メッセージ暗号化ポータルの1回限りのパスコードの使用を管理する

OME によって暗号化されたメッセージの受信者が Outlook を使用していない場合は、受信者によって使用されるアカウントに関係なく、受信者は、メッセージを読むことができる限られた時間の web 表示リンクを受信します。 このリンクには、1回限りのパスコードが含まれています。 管理者は、受信者がワンタイムパスコードを使用して OME ポータルにサインインできるかどうかを判断できます。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>OME がワンタイムパスコードを生成するかどうかを管理するには
  
1. 組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. OTPEnabled パラメーターを指定して、次のコマンドレットを実行します。

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   たとえば、ワンタイムパスコードを無効にするには、次のようにします。

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   1回限りのパスコードを有効にするには:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a>Outlook on the web で [暗号化] ボタンの表示を管理する

管理者は、このボタンをエンドユーザーに表示するかどうかを管理できます。
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a>Outlook on the web に [暗号化] ボタンを表示するかどうかを管理するには
  
1. 組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   たとえば、[ **暗号化** ] ボタンを無効にするには、次のようにします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   [ **暗号化** ] ボタンを有効にするには:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>IOS メールアプリユーザーの電子メールメッセージのサービス側の復号化を有効にする

IOS メールアプリは、Office 365 メッセージの暗号化で保護されたメッセージを解読できません。 Microsoft 365 管理者は、iOS メールアプリに配信されるメッセージに対してサービス側の復号化を適用することができます。 サービス側の復号化を使用することを選択すると、サービスは、復号化されたメッセージのコピーを iOS デバイスに送信します。 クライアントデバイスは、復号化されたメッセージのコピーを格納します。 また、iOS メールアプリでユーザーにクライアント側の使用権限が適用されない場合でも、メッセージは使用権限に関する情報を保持します。 ユーザーは、メッセージをコピーまたは印刷する権限を持っていない場合でも、メッセージをコピーまたは印刷することができます。 ただし、ユーザーが Microsoft 365 メールサーバーを必要とする操作 (メッセージの転送など) を完了しようとしても、そのユーザーの使用権限が最初に付与されていなかった場合、サーバーはアクションを許可しません。 ただし、エンドユーザーは、iOS メールアプリ内の別のアカウントからメッセージを転送することによって、"転送不可" の使用制限を回避できます。 メールのサービス側の復号化を設定しているかどうかに関係なく、暗号化されたメールの添付ファイルと権限保護されたメールは、iOS メールアプリでは表示できません。
  
IOS メールアプリユーザーに暗号化されたメッセージを送信することを許可しない場合、ユーザーには、メッセージを表示する権限がないことを示すメッセージが表示されます。 既定では、電子メールメッセージのサービス側の復号化は有効になっていません。
  
詳細と、クライアント環境の表示の詳細については、「 [iPhone または iPad で暗号化されたメッセージを表示](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)する」を参照してください。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>Office 365 メッセージの暗号化によって保護されたメッセージを iOS メールアプリのユーザーが表示できるかどうかを管理するには
  
1. 組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. AllowRMSSupportForUnenlightenedApps パラメーターを指定して、次のコマンドレットを実行します。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   たとえば、iOS メールアプリなどの unenlightened アプリに送信される前にメッセージを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   また、暗号化されていないメッセージを unenlightened アプリに送信しないようにサービスを構成するには、次のようにします。

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> 個々のメールボックスポリシー (OWA/ActiveSync) は、これらの設定を上書きします (つまり、それぞれの OWA メールボックスポリシーまたは ActiveSync メールボックスポリシーで False に設定されている場合は、これらの構成は適用されません)。

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>Web ブラウザメールクライアントの電子メール添付ファイルのサービス側復号化を有効にする

通常、Office 365 メッセージの暗号化を使用すると、添付ファイルは自動的に暗号化されます。 管理者は、ユーザーが web ブラウザーからダウンロードした電子メール添付ファイルに対して、サービス側の復号化を適用することができます。
  
サービス側の復号化を使用すると、ファイルの復号化されたコピーがサービスによってデバイスに送信されます。 メッセージはまだ暗号化されています。 また、電子メールの添付ファイルは、ブラウザーがクライアント側の使用権限をユーザーに適用しない場合でも、使用権限に関する情報を保持します。 ユーザーは、元の権限がない場合でも、電子メールの添付ファイルをコピーまたは印刷することができます。 ただし、ユーザーが Microsoft 365 メールサーバーを必要とするアクション (添付ファイルの転送など) を完了しようとした場合、ユーザーが最初に使用権限を持っていなかった場合、サーバーはアクションを許可しません。
  
添付ファイルのサービス側の復号化を設定しているかどうかに関係なく、ユーザーは、暗号化されていて、権限で保護されたメールの添付ファイルを iOS メールアプリで表示することはできません。
  
暗号化された電子メール添付ファイルを許可しない場合、既定では、ユーザーには添付ファイルを表示する権限がないというメッセージが表示されます。
  
Microsoft 365 で、[暗号化のみ] オプションを使用して電子メールおよび電子メール添付ファイルの暗号化を実装する方法の詳細については、「[暗号化のみ」のオプション](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)を参照してください。
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>Web ブラウザーからのダウンロード時に電子メールの添付ファイルの暗号化を解除するかどうかを管理するには
  
1. 組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. DecryptAttachmentForEncryptOnly パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   たとえば、ユーザーが web ブラウザーから電子メールの添付ファイルをダウンロードするときに、添付ファイルを復号化するようにサービスを構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   暗号化された電子メール添付ファイルをダウンロード時に残すようにサービスを構成するには、次のようにします。

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a>すべての外部受信者が OME ポータルを使用して暗号化されたメールを読み取ることを確認する

カスタムブランド化テンプレートを使用すると、受信者が Outlook または web 上の Outlook を使用するのではなく、OME ポータルで暗号化された電子メールを読み取ることを指示するラッパーメールを強制的に受信することができます。 受信者が受信するメールの使用方法をより細かく制御する場合は、この操作を行うことをお勧めします。 たとえば、外部の受信者が web ポータルで電子メールを表示する場合、電子メールの有効期限を設定し、電子メールを取り消すことができます。 これらの機能は、OME ポータルでのみサポートされています。 メールフロールールを作成するときは、[暗号化] オプションと [転送不可] オプションを使用できます。

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a>カスタムテンプレートを使用して、すべての外部受信者が OME ポータルと暗号化された電子メールを強制的に使用するようにする

1. 組織内のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始して Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. New-transportrule コマンドレットを実行します。

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    各部分の意味は次のとおりです。

   - `mail flow rule name` は、新しいメールフロールールに使用する名前です。

   - `option name` は、またはのいずれか `Encrypt` `Do Not Forward` です。

   - `template name` は、カスタムブランド化テンプレートに指定した名前です (例 `OME Configuration` :)。

   "OME Configuration" テンプレートを使用してすべての外部電子メールを暗号化し、暗号化のみのオプションを適用するには、次のようにします。

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   "OME Configuration" テンプレートを使用してすべての外部電子メールを暗号化し、[転送しない] オプションを適用するには、次の手順を実行します。

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>電子メールメッセージと OME ポータルの外観をカスタマイズする

組織に合わせて OME をカスタマイズする方法の詳細については、「 [組織のブランドを暗号化されたメッセージに追加](add-your-organization-brand-to-encrypted-messages.md)する」を参照してください。
  
## <a name="disable-the-new-capabilities-for-ome"></a>OME の新機能を無効にする

この記事は提供されていませんが、必要な場合は、OME の新機能を無効にすることは非常に簡単です。 最初に、新しい OME 機能を使用するように作成したメールフロールールを削除する必要があります。 メールフロールールの削除の詳細については、「 [メールフロールールの管理](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)」を参照してください。 次に、Exchange Online の PowerShell で次の手順を実行します。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>OME の新機能を無効にするには
  
1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. Web 上の Outlook で [ **暗号化** ] ボタンを有効にした場合は、SimplifiedClientAccessEnabled パラメーターを指定して、Set-IRMConfiguration コマンドレットを実行することによって、そのボタンを無効にします。 それ以外の場合は、この手順をスキップします。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. OME の新機能を無効にするには、AzureRMSLicensingEnabled パラメーターを false に設定して、Set-IRMConfiguration コマンドレットを実行します。

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
