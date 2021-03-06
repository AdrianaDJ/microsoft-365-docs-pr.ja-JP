---
title: Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: ハイブリッド先進認証 (HMA) を使用するように Exchange Server をオンプレミスで構成する方法について説明し、ユーザーの認証と承認をセキュリティで保護する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547132"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Exchange Server をオンプレミスで構成して、ハイブリッド先進認証を使用するには

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッド先進認証 (HMA) は、よりセキュリティで保護されたユーザー認証と承認を提供する id 管理の方法で、Exchange server のオンプレミスハイブリッド展開で使用できます。

## <a name="fyi"></a>注意

開始する前に、次のように呼び出します。

- ハイブリッド先進認証の \> HMA

- Exchange オンプレミスの \> EXCH

- Exchange Online \> exo

また、 *この記事のグラフィックに ' グレイアウト ' または ' 淡色 ' のオブジェクトが含まれている場合、灰色の要素が HMA 固有の構成に含まれていない* ことを意味します。

## <a name="enabling-hybrid-modern-authentication"></a>ハイブリッド先進認証を有効にする

HMA を有効にするには、次のようにします。

1. 開始する前に、前提条件を満たしていることを確認してください。

1. 多くの **前提条件** は、Skype for Business と exchange の両方に共通であるため、 [ハイブリッド先進認証の概要と、オンプレミスの Skype For business および exchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)です。 この手順を実行する前に、この記事の手順を開始する必要があります。

1. Azure AD の **サービスプリンシパル名 (spn)** として、オンプレミスの Web サービス url を追加します。

1. すべての仮想ディレクトリで HMA が有効になっていることを確認する

1. EvoSTS 認証サーバーオブジェクトの確認

1. EXCH で HMA を有効にします。

 **メモ** お使いのバージョンの Office は MA をサポートしていますか? 「 [Office 2013 および office 2016 クライアントアプリでの先進認証のしくみ」を](modern-auth-for-office-2013-and-2016.md)参照してください。

## <a name="make-sure-you-meet-all-the-prerequisites"></a>すべての前提条件を満たしていることを確認する

Skype for Business と Exchange の両方に共通の前提条件が多数存在するため、 [ハイブリッド先進認証の概要と、オンプレミスの Skype For business および exchange サーバーで使用するための前提条件](hybrid-modern-auth-overview.md)を確認してください。 この手順を実行する  *前*  に、この記事の手順を開始する必要があります。

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>オンプレミスの web サービス Url を Spn として Azure AD に追加する

オンプレミスの web サービス Url を Azure AD Spn として割り当てるコマンドを実行します。 Spn は、認証と承認の際にクライアントコンピューターとデバイスによって使用されます。 オンプレミスから Azure Active Directory (Azure AD) への接続に使用される可能性があるすべての Url は、Azure AD に登録する必要があります (内部と外部の両方の名前空間が含まれます)。

最初に、AAD で追加する必要があるすべての Url を収集します。 オンプレミスで次のコマンドを実行します。

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

AAD でクライアントが接続できる Url が HTTPS サービスプリンシパル名としてリストされていることを確認します。

1. 最初に、 [次の手順に従っ](connect-to-microsoft-365-powershell.md)て AAD に接続します。

   **メモ** このページの _connect-msolservice_ オプションを使用して、以下のコマンドを使用できるようにする必要があります。

2. Exchange 関連の Url の場合は、次のコマンドを入力します。

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   このコマンドの出力をメモします。このコマンドには、https://  *autodiscover.yourdomain.com*  および Https://  *mail.yourdomain.com* URL が含まれていますが、ほとんどの場合は、00000002-0000-0ff1-ce00-000000000000/から始まる spn から構成されます。 オンプレミスの https://Url が不足している場合は、それらのレコードをこのリストに追加する必要があります。

3. 内部および外部の MAPI/HTTP、EWS、ActiveSync、OAB、および自動検出のレコードがこの一覧に表示されない場合は、次のコマンドを使用して追加する必要があります (Url の例は ' `mail.corp.contoso.com` ' と ' ' ですが、この `owa.contoso.com` **例の url は独自のものに置き換え** ます)。

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. 手順2で New-msolserviceprincipal コマンドを再度実行し、出力を調べて、新しいレコードが追加されたことを確認します。 リスト/スクリーンショットを以前から新しい Spn のリストに比較します (レコードの新しいリストのスクリーンショットを表示することもできます)。 成功した場合は、2つの新しい Url が一覧に表示されます。 この例では、Spn の一覧に特定の Url とが含まれるようになりました  `https://mail.corp.contoso.com`  `https://owa.contoso.com` 。

## <a name="verify-virtual-directories-are-properly-configured"></a>仮想ディレクトリが正しく構成されていることを確認する

これで、次のコマンドを実行することによって、Outlook が使用するすべての仮想ディレクトリで OAuth が適切に有効になっていることを確認できます。

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

出力をチェックして、これらの各 VDirs で **OAuth** が有効になっていることを確認してください。次のようになります (そして、ここで重要な点は ' OAuth ' です)。

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

OAuth がサーバーと4つの仮想ディレクトリのいずれにも存在しない場合は、先に進む前に関連するコマンドを使用して追加する必要があります ([MapiVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory)、 [set-webservicesvirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory)、 [set-oabvirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)、および [new-autodiscovervirtualdirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory))。

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>EvoSTS Auth サーバーオブジェクトが存在することを確認する

この最後のコマンドについては、オンプレミスの Exchange 管理シェルに戻ります。 これで、オンプレミスに evoSTS 認証プロバイダのエントリがあることを検証できます。

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

出力には、EvoSts という名前の AuthServer が表示され、' Enabled ' 状態が True である必要があります。 これが表示されない場合は、ハイブリッド構成ウィザードの最新バージョンをダウンロードして実行する必要があります。

 **重要** ご使用の環境で Exchange 2010 を実行している場合は、EvoSTS 認証プロバイダーは作成されません。

## <a name="enable-hma"></a>HMA を有効にする

Exchange 管理シェルで、オンプレミスの次のコマンドを実行します。

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>ことを確認

HMA を有効にすると、クライアントの次のログインは新しい認証フローを使用します。 HMA を有効にしても、クライアントに対しては再認証はトリガーされませんので注意してください。 クライアントは、認証トークンまたは証明書の有効期間に基づいて再認証を行います。

また、CTRL キーを押しながら Outlook クライアントのアイコン (Windows 通知トレイにもあります) を右クリックし、[接続の状態] をクリックします。 OAuth で使用されるベアラートークンを表す ' 認証 ' の種類 ' ベアラー ' に対してクライアントの SMTP アドレスを検索し \* ます。

 **メモ** HMA を使用して Skype for Business を構成する必要がありますか? [サポートされているトポロジ](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)の一覧と、[構成方法](configure-skype-for-business-for-hybrid-modern-authentication.md)を示す2つの記事が必要になります。

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>iOS および Android 用の Outlook でのハイブリッド先進認証の使用

TCP 443 で Exchange server を使用しているオンプレミスのお客様の場合は、次の IP 範囲をホワイトリストしてください。

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>関連トピック

[Office 365 専任/ITAR から vNext に移行するための先進認証構成要件](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
