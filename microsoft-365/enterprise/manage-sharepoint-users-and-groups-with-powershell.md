---
title: PowerShell を使用して SharePoint Online のユーザーとグループを管理する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
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
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: この記事では、Microsoft 365 の PowerShell を使用して SharePoint Online ユーザー、グループ、およびサイトを管理する方法について説明します。
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692077"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>PowerShell を使用して SharePoint Online のユーザーとグループを管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

ユーザーアカウントまたはグループの大規模なリストで作業を行う SharePoint Online 管理者は、Microsoft 365 の PowerShell を使用することができます。 

開始する前に、このトピックの手順で SharePoint Online に接続する必要があります。 手順については、「 [SharePoint Online PowerShell への接続](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)」を参照してください。

## <a name="get-a-list-of-sites-groups-and-users"></a>サイト、グループ、ユーザーの一覧を取得する

ユーザーとグループを管理する前に、サイト、グループ、ユーザーの一覧を取得する必要があります。この情報は、この記事の例全体を通して使用できます。

次のコマンドを使用して、テナント内のサイトの一覧を取得します。

```powershell
Get-SPOSite
```

次のコマンドを使用して、テナント内のグループの一覧を取得します。

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

次のコマンドを使用して、テナント内のユーザーの一覧を取得します。

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>サイト コレクション管理者グループにユーザーを追加する

コマンドレットを使用して、 `Set-SPOUser` サイトコレクションのサイトコレクション管理者のリストにユーザーを追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

これらのコマンドを使用するには、引用符で囲まれたすべての内容 (< と > の文字を含む) を正しい名前に置き換えます。

たとえば、次のコマンドを使用すると、Opal Castillo (user name opalc) が Contoso テナント内の ContosoTest サイトコレクションのサイトコレクション管理者の一覧に追加されます。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

これらのコマンドをメモ帳にコピーして貼り付けることができます。 $tenant、$site、および $user の変数値を環境から実際の値に変更し、それを SharePoint Online 管理シェルウィンドウに貼り付けて実行します。

## <a name="add-a-user-to-other-site-collection-groups"></a>他のサイトコレクショングループにユーザーを追加する

この作業では、コマンドレットを使用して、 `Add-SPOUser` サイトコレクションの SharePoint グループにユーザーを追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

たとえば、「Glen Rife (ユーザー名 glenr)」を「contoso テナント内の ContosoTest サイトコレクションの監査者グループに追加してみましょう。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>サイト コレクション グループを作成する

`New-SPOSiteGroup`このコマンドレットを使用して、新しい SharePoint グループを作成し、それをサイトコレクションに追加します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
アクセス許可レベルなどのグループのプロパティは、後でコマンドレットを使用して更新でき `Set-SPOSiteGroup` ます。

たとえば、contoso テナント内の contosotest サイトコレクションに対する表示のみのアクセス許可を持つ監査グループを追加してみましょう。

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>グループからユーザーを削除する

場合によっては、あるサイトまたはすべてのサイトからユーザーを削除する必要があります。たとえば、従業員がある部署から別の部署に異動した場合や、退職した場合などが該当します。対象の従業員が 1 人のみの場合は UI で簡単に削除できますが、部署全体をあるサイトから別のサイトに移動する場合は容易ではありません。

ただし、SharePoint Online 管理シェルと CSV ファイルを使用することで、これは迅速かつ簡単になります。 このタスクでは、まず、Windows PowerShell を使用して、サイト コレクションのセキュリティ グループから 1 人のユーザーを削除します。 次に、CSV ファイルを使用して、複数の異なるサイトから多数のユーザーを削除します。 

コマンド構文を確認できるように、' Remove-SPOUser ' コマンドレットを使用して、1つの Microsoft 365 ユーザーをサイトコレクショングループから削除します。 以下に、構文の一例を示します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
たとえば、contoso テナントの contosotest サイトコレクションのサイトコレクション監査グループから、[村中 Overby を削除しましょう。

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

ユーザーが現在所属しているすべてのグループから、村中を削除するとします。 これを行う方法を次に示します。

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> これは1つの例にすぎません。 たとえば、ユーザーが退職した場合など、ユーザーをすべてのグループから実際に削除しなければならないのでない限り、このコマンドを使用しないでください。

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>ユーザーおよびグループの大規模なリストの管理を自動化する

多数のアカウントを SharePoint サイトに追加してアクセス許可を付与するには、Microsoft 365 管理センター、個々の PowerShell コマンド、または PowerShell を CSV ファイルとして使用できます。 これらの選択肢の中では、CSV ファイルがこのタスクを自動化する最も簡単な方法になります。

基本的なプロセスは、CSV を作成し、ヘッダー (列) を Windows PowerShell スクリプトに必要なパラメーターに対応させることです。 このようなリストは、Excel で簡単に作成して、それを CSV ファイルとしてエクスポートすることができます。 次に、Windows PowerShell スクリプトを使用して、CSV ファイルのレコード (行) を反復処理し、ユーザーをグループに、グループをサイトに追加します。 

たとえば、サイトコレクション、グループ、およびアクセス許可のグループを定義する CSV ファイルを作成してみましょう。 次に、グループにユーザーを取り込むための CSV ファイルを作成します。 最後に、グループを作成してユーザーを取り込む単純な Windows PowerShell スクリプトを作成して実行します。

最初の CSV ファイルは、1 つ以上のグループを 1 つ以上のサイト コレクションに追加します。このファイルの構造は以下のとおりです。

見出し

```powershell
Site,Group,PermissionLevels
```

部分

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

以下は、サンプル ファイルです。

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

2 番目の CSV ファイルは、1 つ以上のユーザーを 1 つ以上のグループに追加します。このファイルの構造は以下のとおりです。

見出し

```powershell
Group,LoginName,Site
```

部分

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

以下は、サンプル ファイルです。

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

次の手順では、2 つの CSV ファイルをドライブに保存する必要があります。 次に、両方の CSV ファイルを使用してアクセス許可とグループメンバーシップを追加するコマンドの例を示します。

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

このスクリプトは、CSV ファイルの内容をインポートし、列の値を使用して、 **remove-spositegroup** および **Add-spouser** コマンドのパラメーターを設定します。 この例では、ドライブ C の theO365Admin フォルダーに保存していますが、任意の場所に保存できます。

次に、同じ CSV ファイルを使用して、複数のサイトにある複数のグループの一連のユーザーを削除してみましょう。 コマンド例を次に示します。

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>ユーザー レポートを生成する

いくつかのサイトに関する単純なレポートを取得して、該当するサイトのユーザーと各ユーザーのアクセス許可レベルやその他のプロパティを表示しなければならない場合があります。以下に、構文の一例を示します。

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

上記のコードは、3 つのサイトのデータを取得して、ローカル ドライブ上のテキスト ファイルに書き込みます。 パラメーター –Append は、既存のファイルに新しいコンテンツを追加することに注意してください。

たとえば、Contoso1 テナントの ContosoTest サイト、TeamSite01 サイト、および Project01 サイトでレポートを実行します。

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

**$Site**変数のみを変更する必要があることに注意してください。 **$Tenant**変数の値は、コマンドの3つの実行によって保持されます。

一方、この操作をすべてのサイトに対して行うとしたら、どうなるでしょうか。以下のコードを使用すれば、すべての Web サイトを入力することなく、このコマンドを使用できます。

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

このレポートはかなり単純ですが、コードを追加すれば、より具体的なレポートや、その他の詳細情報が含まれるレポートを作成できます。 しかし、sharepoint online 管理シェルを使用して SharePoint Online 環境のユーザーを管理する方法についての理解が得られます。
   
## <a name="see-also"></a>関連項目

[SharePoint Online PowerShell に接続する](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[PowerShell を使用して SharePoint Online を管理する](create-sharepoint-sites-and-add-users-with-powershell.md)

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
