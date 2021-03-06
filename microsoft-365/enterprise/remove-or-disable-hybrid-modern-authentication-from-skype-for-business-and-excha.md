---
title: Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事では、Skype for Business と Exchange からハイブリッド先進認証を削除または無効化する方法について説明します。
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547098"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Skype for Business および Exchange からのハイブリッド先進認証の削除または無効化

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ハイブリッドモダン認証 (HMA) を有効にして、現在の環境に適していないことを検出した場合は、HMA を無効にすることができます。 この記事では、その方法について説明します。
  
## <a name="who-is-this-article-for"></a>この記事の対象読者

Skype for Business Online、オンプレミス、または Exchange Online またはオンプレミスで先進認証を有効にしている場合に、HMA を無効にするには、次の手順を実行します。

> [!IMPORTANT]
> Skype for business Online またはオンプレミスでトポロジが混在していて、開始する前にサポートされているトポロジを確認する必要がある場合は、「[先進認証でサポートされている skype For business トポロジ](https://technet.microsoft.com/library/mt803262.aspx)」を参照してください。
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>ハイブリッド先進認証を無効にする方法 (Exchange)

1. **Exchange オンプレミス**: Exchange 管理シェルを開き、次のコマンドを実行します。 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange online**: リモート PowerShell を使用して [exchange online に接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) します。 *OAuth2ClientProfileEnabled*フラグを ' false ' にするには、次のコマンドを実行します。

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>ハイブリッド先進認証を無効にする方法 (Skype for Business)

1. **Skype For Business オンプレミス**: skype For Business 管理シェルで次のコマンドを実行します。

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype For Business online**: リモート PowerShell を使用して [Skype for business online に接続](manage-skype-for-business-online-with-microsoft-365-powershell.md) します。 先進認証を無効にするには、次のコマンドを実行します。

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[モダン認証の概要に戻る](hybrid-modern-auth-overview.md) 
  

