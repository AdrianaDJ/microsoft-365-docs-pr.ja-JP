---
title: 複数地域環境での Exchange Online メールボックスの管理
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: PowerShell を使用して Microsoft 365 環境の Exchange Online の複数地域設定を管理する方法について説明します。
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552009"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>複数地域環境での Exchange Online メールボックスの管理

Microsoft 365 環境で複数の geo プロパティを表示および構成するには、Exchange Online PowerShell が必要です。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

ユーザー オブジェクトの **PreferredDataLocation** プロパティを参照するには、v1.x に [Microsoft Azure Active Directory PowerShell モジュール](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 以降が必要です。 AAD Connect 経由で AAD に同期されたユーザー オブジェクトでは、**PreferredDataLocation** 値を AAD PowerShell 経由で直接変更することはできません。 クラウド専用ユーザー オブジェクトは、AAD PowerShell 経由で変更できます。 Azure AD PowerShell に接続するには、「[PowerShell への接続](connect-to-microsoft-365-powershell.md)」を参照してください。

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Exchange Online PowerShell を使用して、地域の場所に直接接続する

通常、Exchange Online PowerShellは地理上の中央位置に接続します。 しかし、衛星の地理的位置に直接接続することもできます。 パフォーマンスが向上するため、その場所にいるユーザーのみを管理している場合は、衛星地域に直接接続することをお勧めします。

EXO V2 モジュールをインストールして使用するための要件は、「[EXO V2 モジュールをインストールして維持する](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)」に記載されています。

Exchange Online の PowerShell を特定の地域の場所に接続するために、 *Connectionuri* パラメーターは通常の接続手順とは異なります。 残りのコマンドと値は同じです。

具体的には、 `?email=<emailaddress>` _connectionuri_ 値の末尾に値を追加する必要があります。 `<emailaddress>` は、対象と **なる** 地域の場所にあるメールボックスの電子メールアドレスです。 そのメールボックスへのアクセス許可または資格情報への関係は、要因ではありません。電子メールアドレスは、接続先の Exchange Online PowerShell に対してのみを指定します。

Microsoft 365 または Microsoft 365 GCC のお客様は、通常、 _Connectionuri_ パラメーターを使用して Exchange Online PowerShell に接続する必要はありません。 ただし、特定の地域の場所に接続するには、値でを使用できるように、 _Connectionuri_ パラメーターを使用する必要があり `?email=<emailaddress>` ます。

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Exchange Online PowerShell で地域の場所に接続する

次の接続手順は、多要素認証 (MFA) 用に構成されていない、または構成されていないアカウントに対して機能します。

1. Windows PowerShell ウィンドウで、次のコマンドを実行して EXO V2 モジュールを読み込みます。

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. 次の例では、admin@contoso.onmicrosoft.com は管理者アカウントで、ターゲット地域の場所はメールボックス olga@contoso.onmicrosoft.com が存在する場所です。

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. 表示されるプロンプトに、admin@contoso.onmicrosoft.com のパスワードを入力します。 アカウントが MFA に対して構成されている場合は、セキュリティコードも入力する必要があります。

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Exchange Online 組織で構成されている使用可能な地域の場所を表示する

Microsoft 365 Multi-Geo の構成された地域の場所のリストを参照するには、Exchange Online PowerShell で次のコマンドを実行します。

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Exchange Online組織の地理上中央位置を表示する

テナントの地理上中央位置を表示するには、Exchange Online PowerShellで次のコマンドを実行します。

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>メールボックスの地域の場所を検索する

Exchange Online PowerShell の **Get-Mailbox** コマンドレットでは、メールボックスの複数地域に関連した以下のプロパティが表示されます。

- **Database**: データベース名の最初の 3 つの文字は、メールボックスが置かれていることを通知する地域コードに対応します。 オンライン アーカイブ メールボックスには、**ArchiveDatabase** が使用される必要があります。

- **MailboxRegion**: 管理者によって設定された地域の場所コード (Azure AD の **PreferredDataLocation** から同期された) を指定します。

- **MailboxRegionLastUpdateTime**: MailboxRegion が (自動または手動で) 最終更新された日時を示します。

メールボックスのこれらのプロパティを表示するには、次の構文を使用します。

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

たとえば、メール ボックスの chris@contoso.onmicrosoft.com の地理的位置の情報を表示するには、次のコマンドを実行します。

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

コマンドの出力は次のようになります。

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> データベース名の地理的位置コードが **MailboxRegion** 値と一致しない場合、メールボックスは自動的に再配置キューに配置され、 **MailboxRegion** 値で指定された地理的位置に移動します (Exchange Online は、これらのプロパティ値の不一致を検出します)。

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>既存のクラウド専用メールボックスを特定の地域の場所に移動する

クラウド専用ユーザーとは、AAD Connectを介してテナントと同期していないユーザーです。 このユーザーは、Azure AD で直接作成されました。 クラウド専用ユーザーのメールボックスが格納される地理的な場所を表示または指定するには、Windows PowerShell用Azure ADモジュールの **Get-MsolUser** および **Set-MsolUser** コマンドレットを使用します。

ユーザーの **PreferredDataLocation** 値を表示するには、Azure AD PowerShell で次の構文を使用します。

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

たとえば、ユーザー michelle@contoso.onmicrosoft.com の **PreferredDataLocation** 値を表示するには、次のコマンドを実行します。

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

クラウド専用ユーザー オブジェクトの **PreferredDataLocation** 値を変更するには、Azure AD PowerShell で次の構文を使用します。

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

たとえば、**PreferredDataLocation** 値をユーザー michelle@contoso.onmicrosoft.com の欧州連合 (EUR) 地域に設定するには、次のコマンドを実行します。

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - 前述したように、オンプレミスの Active Directory から同期されたユーザーオブジェクトに対して、この手順を使用することはできません。 Active Directory で **PreferredDataLocation** 値を変更し、それを AAD Connect を使用して同期させる必要があります。 詳細については、「[Azure Active Directory Connect 同期: Microsoft 365 リソースの優先されるデータの場所を構成する](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)」を参照してください。
>
> - メールボックスを新しい地域の場所に再配置するための所要時間は次のいくつかの要素によって決まります。
>
>   - メールボックスのサイズと種類。
>   - 移行されるメールボックスの数。
>   - リソース移動の可用性。

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>非アクティブなメールボックスを特定の地域に移動する

**PreferredDataLocation** 値を変更することで、コンプライアンスの目的で保持されている非アクティブなメールボックス (訴訟ホールドのメールボックスなど) を移動することはできません。 非アクティブなメールボックスを別の geo に移動するには、次の手順を実行します。

1. 非アクティブなメールボックスを回復します。 手順については、「 [非アクティブなメールボックスを回復する](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)」を参照してください。

2. 管理フォルダーアシスタントが、 \<MailboxIdentity\> メールボックスの名前、エイリアス、アカウント、または電子メールアドレスに置き換え、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行して、回復されたメールボックスを処理できないようにします。

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. 回復されたメールボックスに **Exchange Online プラン 2** ライセンスを割り当てます。 この手順は、メールボックスを訴訟ホールドの対象に戻すために必要です。 手順については、「 [ユーザーへのライセンスの割り当て](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)」を参照してください。

4. 前のセクションで説明したように、メールボックスの **PreferredDataLocation** 値を構成します。

5. メールボックスが新しい地域の場所に移動されたことを確認した後、回復されたメールボックスを訴訟ホールドの対象に戻します。 手順については、「 [メールボックスを訴訟ホールドの対象にする](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)」を参照してください。

6. 訴訟ホールドが有効になっていることを確認した後、 \<MailboxIdentity\> メールボックスの名前、エイリアス、アカウント、または電子メールアドレスで置き換えて、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)で次のコマンドを実行することによって、管理フォルダーアシスタントがメールボックスを再度処理できるようにします。

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. メールボックスに関連付けられているユーザーアカウントを削除して、メールボックスを再度非アクティブにします。 手順については、「 [組織からユーザーを削除する](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)」を参照してください。 この手順では、他の用途に対して Exchange Online プラン2ライセンスも解放されます。

**注**: 非アクティブなメールボックスを別の地域の場所に移動すると、コンテンツ検索の結果に影響を与えたり、以前の地理的位置からメールボックスを検索したりすることができます。 詳細については、「 [複数地域環境でのコンテンツの検索とエクスポート](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)」を参照してください。

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>特定の地域の場所に新しいクラウド メールボックスを作成する

特定の地域の場所に新しいメールボックスを作成するには、以下の手順のいずれかを実行する必要があります。

- Exchange Online でメールボックスを作成する *前* に、前の「[既存のクラウドのみのメールボックスを特定の地域の場所に移動](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location)する」の説明に従って、 **PreferredDataLocation** の値を構成します。 たとえば、ライセンスを割り当てる前にユーザーの **PreferredDataLocation** 値を構成します。

- **PreferredDataLocation** 値の設定と同時にライセンスを割り当てます。

特定の地域にクラウド専用のライセンスユーザー（AAD Connectと同期していないユーザー）を作成するには、Azure AD PowerShellで次の構文を使用します：

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

この例では、次の値を使用して Elizabeth Brunner 用に新しいユーザー アカウントを作成します。

- ユーザー プリンシパル名: ebrunner@contoso.onmicrosoft.com
- 名: Elizabeth
- 姓: Brunner
- 表示名：Elizabeth Brunner
- パスワード: ランダムに生成され、コマンドの結果に表示される (*パスワード* パラメーターを使用していないため)
- ライセンス：`contoso:ENTERPRISEPREMIUM`（E5）
- 場所: オーストラリア (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Azure AD PowerShell での新しいユーザー アカウントの作成や LicenseAssignment 値の検索の詳細については、「[PowerShell のユーザー アカウントを作成する](create-user-accounts-with-microsoft-365-powershell.md)」と「[PowerShell でライセンスとサービスを確認する](view-licenses-and-services-with-microsoft-365-powershell.md)」を参照してください。

> [!NOTE]
> Exchange Online PowerShellを使用してメールボックスを有効にし、メールボックスを **PreferredDataLocation** で指定した地理上の場所に直接作成する必要がある場合は、クラウドサービスに対して **Enable-Mailbox** や **New-Mailbox** などのExchange Onlineコマンドレットを直接使用する必要があります。 オンプレミスのExchange PowerShellで **Enable-RemoteMailbox** コマンドレットを使用すると、メールボックスは地理上の中央位置に作成されます。

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>既存のオンプレミスのメールボックスを特定の地域の場所にオンボードする

標準のオンボーディング ツールとプロセスを使用して、オンプレミスの Exchange 組織から Exchange Online にメールボックスを移行できます ([EAC の移行ダッシュボード](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)、および Exchange Online PowerShell の [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) コマンドレットを含む)。

最初の手順は、オンボードされる各メールボックスにユーザー オブジェクトが存在することを確認し、正しい **PreferredDataLocation** 値が Azure AD で構成されていることを確認することです。 オンボーディングツールは **PreferredDataLocation** 値に従い、メールボックスを指定された地理的位置に直接移行します。

または、Exchange Online PowerShell の [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) コマンドレットを使用してメールボックスを特定の地域に直接オンボードするために次の手順を使用できます。

1. オンボードされる各メールボックスにユーザー オブジェクトが存在し、Azure AD で **PreferredDataLocation** が適切な値に設定されていることを確認します。 **PreferredDataLocation** の値は、Exchange Online の対応するメール ユーザー オブジェクトの **MailboxRegion** 属性に同期されます。

2. このトピックの前半の接続手順を使用して、特定の衛星地域に直接接続してください。

3. Exchange Online PowerShell で、次のコマンドを実行して、メールボックスの移行を変数で実行するために使用されるオンプレミスの管理者認証情報を保存します。

   ```powershell
   $RC = Get-Credential
   ```

4. Exchange Online PowerShell で、次の例に類似した新しい **New-MoveRequest** を作成します。

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. オンプレミスのExchangeから現在接続している衛星地域に移行する必要があるメールボックスごとに、手順4を繰り返します。

6. If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.

## <a name="multi-geo-reporting"></a>複数地域レポート

Microsoft 365 管理センターの **複数地域利用状況レポート** では、地域の場所ごとのユーザー数が表示されます。 レポートには、当月のユーザー分布が表示され、過去 6 か月間の履歴データが提供されます。

## <a name="see-also"></a>関連項目

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
