---
title: PowerShell を使用してパスワードを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
description: PowerShell を使用してパスワードを管理する方法について説明します。
ms.openlocfilehash: ac0a47edb4ccbed93c1a3b88df083d463784b4a4
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073214"
---
# <a name="manage-passwords-with-powershell"></a>PowerShell を使用してパスワードを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 の PowerShell を microsoft 365 管理センターの代わりとして使用して、Microsoft 365 でパスワードを管理することができます。 

この記事のコマンドブロックで変数の値を指定する必要がある場合は、次の手順を実行します。

1. コマンドブロックをクリップボードにコピーして、メモ帳または PowerShell 統合スクリプト環境 (ISE) に貼り付けます。
2. 変数の値を入力し、"<" と ">" の文字を削除します。
3. PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。

### <a name="set-a-password"></a>パスワードを設定する

ユーザーアカウントのパスワードを指定するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword
```
### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

次のコマンドを使用してパスワードを設定し、ユーザーに新しいパスワードの変更を強制します。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -EnforceChangePasswordPolicy $true
```

次のコマンドを使用して、パスワードを設定し、ユーザーが次回サインインしたときに新しいパスワードを強制的に変更するようにします。

```powershell
$userUPN="<user account sign in name, such as belindan@contoso.com>"
$newPassword="<new password>"
$secPassword = ConvertTo-SecureString $newPassword -AsPlainText -Force
Set-AzureADUserPassword -ObjectId  $userUPN -Password $secPassword -ForceChangePasswordNextLogin $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

### <a name="set-a-password"></a>パスワードを設定する

ユーザーアカウントのパスワードを指定するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name>"
$newPassword="<new password>"
Set-MsolUserPassword -UserPrincipalName $userUPN -NewPassword $newPassword
```

### <a name="force-a-user-to-change-their-password"></a>ユーザーにパスワードの変更を強制する

ユーザーが自分のパスワードを変更するように強制するには、次のコマンドを使用します。

```powershell
$userUPN="<user account sign in name>"
Set-MsolUserPassword -UserPrincipalName $userUPN -ForceChangePassword $true
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

