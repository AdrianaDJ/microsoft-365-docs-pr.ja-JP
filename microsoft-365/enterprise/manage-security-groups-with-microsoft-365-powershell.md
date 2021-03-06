---
title: PowerShell を使用してセキュリティグループを管理する
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
description: PowerShell を使用してセキュリティグループを管理する方法について説明します。
ms.openlocfilehash: a52fcf6a20598e92f9d5ac8d673a4b1c026030f8
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073231"
---
# <a name="manage-security-groups-with-powershell"></a>PowerShell を使用してセキュリティグループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 の PowerShell は、セキュリティグループを管理するために Microsoft 365 管理センターの代わりとして使用できます。 

この記事では、設定の一覧表示、作成、変更、およびセキュリティグループの削除について説明します。 

この記事のコマンドブロックで変数の値を指定する必要がある場合は、次の手順を実行します。

1. コマンドブロックをクリップボードにコピーして、メモ帳または PowerShell 統合スクリプト環境 (ISE) に貼り付けます。
2. 変数の値を入力し、"<" と ">" の文字を削除します。
3. PowerShell ウィンドウまたは PowerShell ISE でコマンドを実行します。

PowerShell を使用してグループメンバーシップを管理するには、「 [セキュリティグループメンバーシップを維持](maintain-group-membership-with-microsoft-365-powershell.md) する」を参照してください。

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)します。

### <a name="list-your-groups"></a>グループを一覧表示する

すべてのグループを一覧表示するには、このコマンドを使用します。

```powershell
Get-AzureADGroup
```
表示名によって特定のグループの設定を表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>新しいグループを作成する

新しいセキュリティグループを作成するには、次のコマンドを使用します。

```powershell
New-AzureADGroup -Description "<group purpose>" -DisplayName "<name>" -MailEnabled $false -SecurityEnabled $true -MailNickName "<email name>"
```

### <a name="change-the-settings-on-a-group"></a>グループの設定を変更する

これらのコマンドを使用して、グループの設定を表示します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

次に、 [AzureADGroup](https://docs.microsoft.com/powershell/module/azuread/set-azureadgroup) の記事を使用して、設定を変更する方法を決定します。

### <a name="remove-a-security-group"></a>セキュリティグループを削除する

セキュリティグループを削除するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Remove-AzureADGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

### <a name="manage-the-owners-of-a-security-group"></a>セキュリティグループの所有者を管理する

セキュリティグループの現在の所有者を表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```
ユーザー **プリンシパル名 (UPN)** を使用して、ユーザーアカウントをセキュリティグループの現在の所有者に追加するには、次のコマンドを使用します。

```powershell
$userUPN="<UPN of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```
ユーザーアカウントをセキュリティグループの現在の所有者に **表示名** で追加するには、次のコマンドを使用します。

```powershell
$userName="<Display name of the user account to add>"
$groupName="<display name of the group>"
Add-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```
ユーザーアカウントを **UPN** によってセキュリティグループの現在の所有者に削除するには、次のコマンドを使用します。

```powershell
$userUPN="<UPN of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectId
```

ユーザーアカウントを、セキュリティグループの現在の所有者への **表示名** で削除するには、次のコマンドを使用します。

```powershell
$userName="<Display name of the user account to remove>"
$groupName="<display name of the group>"
Remove-AzureADGroupOwner -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId -OwnerId (Get-AzureADUser | Where { $_.DisplayName -eq $userName }).ObjectId
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する

最初に、 [Microsoft 365 テナントに接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)します。

### <a name="list-your-groups"></a>グループを一覧表示する

すべてのグループを一覧表示するには、このコマンドを使用します。

```powershell
Get-MsolGroup
```
表示名によって特定のグループの設定を表示するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName }
```

### <a name="create-a-new-group"></a>新しいグループを作成する

新しいセキュリティグループを作成するには、次のコマンドを使用します。

```powershell
New-MsolGroup -Description "<group purpose>" -DisplayName "<name>"
```

### <a name="change-the-settings-on-a-group"></a>グループの設定を変更する

これらのコマンドを使用して、グループの設定を表示します。

```powershell
$groupName="<display name of the group>"
Get-MsolGroup | Where { $_.DisplayName -eq $groupName } | Select *
```

次に、 [MsolGroup](https://docs.microsoft.com/powershell/module/msonline/set-msolgroup) の記事を使用して、設定を変更する方法を決定します。

### <a name="remove-a-security-group"></a>セキュリティグループを削除する

セキュリティグループを削除するには、次のコマンドを使用します。

```powershell
$groupName="<display name of the group>"
Remove-MsolGroup -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectId
```

## <a name="see-also"></a>関連項目

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

