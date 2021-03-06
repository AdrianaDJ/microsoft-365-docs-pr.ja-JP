---
title: 電子情報開示調査のためにコンプライアンスの境界を設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンスの境界を使用して、Microsoft 365 で電子情報開示マネージャーが検索できるユーザーコンテンツの場所を制御する論理的な境界を作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: afc01ea88e9a2de6550741dcaac105ef764a752f
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131132"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations"></a>電子情報開示調査のためにコンプライアンスの境界を設定する

この記事のガイダンスは、コア電子情報開示またはアドバンスト eDiscovery のどちらかを使用して調査を管理する場合に適用できます。

コンプライアンス境界は、電子情報開示マネージャーが検索できるユーザーコンテンツの場所 (メールボックス、OneDrive アカウント、SharePoint サイトなど) を制御する、組織内で論理的な境界を作成します。 また、コンプライアンスの境界は、組織内の法律、人的リソース、またはその他の調査を管理するために使用される電子情報開示ケースにアクセスできるユーザーを制御します。 多国籍企業では、多くの場合、地理的な boarders および規制を遵守する必要があり、政府機関に対しては、多くの場合、さまざまな機関に分かれているため、コンプライアンスの境界が必要になります。 Microsoft 365 では、コンテンツ検索を実行し、電子情報開示ケースを使用して調査を管理する際に、これらの要件を満たすためにコンプライアンスの境界が役立ちます。
  
次の図の例を使用して、コンプライアンスの境界がどのように機能するかを説明します。
  
![コンプライアンスの境界は、電子情報開示ケースへのアクセスを制御するエージェンシーおよび管理役割グループへのアクセスを制御する検索アクセス許可フィルターで構成されます。](../media/M365_ComplianceBoundary_OrgChart_v2.png)
  
この例では、Contoso LTD. は、2つの子会社 (2 番目のコーヒーと Coho) で構成される組織です。 ビジネスでは、電子情報開示 mangers と調査担当者が、エージェンシー内の Exchange メールボックス、OneDrive アカウント、および SharePoint サイトのみを検索できるようにする必要があります。 また、電子情報開示マネージャーおよび調査担当者は、エージェンシーの電子情報開示ケースのみを表示でき、メンバーとなっているケースにのみアクセスできます。 以下に、コンプライアンスの境界がこれらの要件を満たす方法を示します。
  
- コンテンツ検索の検索アクセス許可フィルター機能は、電子情報開示の管理者および捜査担当者が検索できるコンテンツの場所を制御します。 つまり、Fourth Coffee 代理店の情報開示マネージャーと調査担当者は、Fourth Coffee の子会社のコンテンツの場所のみ検索できます。 同じ制限が Coho Winery の子会社にも適用されます。

    役割グループは、セキュリティ & コンプライアンスセンターで電子情報開示ケースを表示できるユーザーを制御します。 つまり、電子情報開示マネージャーと調査担当者には、その機関の電子情報開示ケースのみが表示されます。

- 役割グループは、電子情報開示ケースにメンバーを割り当てることができるユーザーも制御します。 つまり、電子情報開示マネージャーと調査担当者は、自分がメンバーになっているケースにのみメンバーを割り当てることができます。

コンプライアンスの境界を設定するプロセスは次のとおりです。
  
[手順 1: ユーザー属性を識別して、機関を定義する](#step-1-identify-a-user-attribute-to-define-your-agencies)

[手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[手順 3: 各エージェンシーの役割グループを作成する](#step-3-create-a-role-group-for-each-agency)

[手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する](#step-5-create-an-ediscovery-case-for-intra-agency-investigations)

## <a name="before-you-set-up-compliance-boundaries"></a>コンプライアンスの境界を設定する前に

次の前提条件を満たす必要があります。 Azure Active Directory (Azure AD) 属性 (手順 1) は、ユーザーの OneDrive アカウント (手順 2) に正常に同期することができます。

- ユーザーには、Exchange Online のライセンスと SharePoint Online のライセンスが割り当てられている必要があります。

- ユーザーメールボックスのサイズは、少なくとも 10 MB でなければなりません。 ユーザーのメールボックスが 10 MB 未満の場合、エージェンシーの定義に使用される属性は、ユーザーの OneDrive アカウントに同期されません。

- コンプライアンスの境界と、検索アクセス許可フィルターを作成するために使用される属性には、Azure Active Directory (Azure AD) 属性をユーザーのメールボックスに同期させる必要があります。 使用する属性が同期されていることを確認するには、Exchange Online PowerShell で [ユーザー](https://docs.microsoft.com/powershell/module/exchange/get-user) コマンドレットを実行します。 このコマンドレットの出力は、Exchange Online と同期された Azure AD 属性を表示します。

## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a>手順 1: ユーザー属性を識別して、機関を定義する

最初の手順として、を使用する Azure AD 属性を選択して、その機関を定義します。 この属性は、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するように電子情報開示マネージャーを制限する検索アクセス許可フィルターを作成するために使用されます。 たとえば、Contoso 社が **Department** 属性の使用を決定したとします。 4番目のコーヒー子会社のユーザーのこの属性の値は  `FourthCoffee`  となり、Coho のユーザーの値はとなり `CohoWinery` ます。 手順4では、この  `attribute:value`  ペア (たとえば、 *Department: 4 thコーヒー*) を使用して、電子情報開示マネージャーが検索できるユーザーのコンテンツの場所を制限します。 
  
以下は、コンプライアンスの境界に使用できる Azure AD ユーザー属性の一覧です。
  
- Company

- CustomAttribute1-CustomAttribute15

- 部署

- 事業所

- C (2 桁の国コード) <sup>*</sup>

  > [!NOTE]
  > <sup>*</sup> この属性は、Exchange Online PowerShell で **ユーザー** コマンドレットを実行することによって返される CountryOrRegion プロパティにマップされます。 このコマンドレットは、ローカライズされた国名を返します。これは、2文字の国コードから変換されます。 詳細については、「CountryOrRegion [」コマンドレット](https://docs.microsoft.com/powershell/module/exchange/set-user) リファレンスの記事の「パラメーターの説明」を参照してください。

他のユーザー属性も使用できますが (特に Exchange メールボックスの場合)、上記の属性は OneDrive で現在サポートされているものだけです。
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a>手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる

次の手順では、Microsoft サポートに要求をファイルして、手順1で選択した Azure AD 属性を組織内のすべての OneDrive アカウントに同期させます。 この同期が行われると、手順1で選択した属性 (およびその値) がという名前の非表示の管理プロパティにマップされ `ComplianceAttribute` ます。 この属性を使用して、手順4で OneDrive の検索アクセス許可フィルターを作成します。
  
Microsoft サポートに要求を送信するときに、次の情報を含めます。
  
- 組織の既定のドメイン名

- Azure AD 属性の名前 (手順1から)

- サポート要求の目的に関する次のタイトルまたは説明: "コンプライアンスセキュリティフィルター用に、Azure AD での OneDrive for Business の同期を有効にする"。 これにより、要求を実装する電子情報開示エンジニアリングチームに、要求をルーティングすることができます。

エンジニアリングの変更が行われ、属性が OneDrive に同期されると、Microsoft Support は変更が行われたビルド番号と推定展開日を送信します。 通常、展開プロセスには、サポート要求を送信した後、4 ~ 6 週間かかります。
  
> [!IMPORTANT]
> この属性の変更を展開する前に、手順3から手順5までを完了できます。 ただし、コンテンツ検索を実行しても、属性の同期が展開されるまでは、検索アクセス許可フィルターで指定されている OneDrive アカウントからドキュメントは返されません。
  
## <a name="step-3-create-a-role-group-for-each-agency"></a>手順 3: 各エージェンシーの役割グループを作成する

次の手順では、組織の機関と連携するセキュリティ & コンプライアンスセンターで役割グループを作成します。 役割グループを作成するには、組み込みの電子情報開示マネージャー グループをコピーし、適切なメンバーを追加し、ニーズに当てはまらない可能性がある役割を削除することをお勧めします。 電子情報開示関連のロールの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。
  
役割グループを作成するには、[セキュリティ/コンプライアンス センター] の [**アクセス許可**] ページに移動し、コンプライアンスの境界と電子情報開示ケースを使用して調査を管理する各機関のチームそれぞれの役割グループを作成します。 
  
Contoso 社のコンプライアンス境界シナリオを使用して、4つの役割グループを作成し、それぞれに適切なメンバーを追加する必要があります。
  
- Fourth Coffee の電子情報開示マネージャー

- Fourth Coffee の調査担当者

- Coho Winery の電子情報開示マネージャー

- Coho Winery の調査担当者
  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a>手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する

各エージェンシーの役割グループを作成したら、次の手順として、各役割グループを特定のエージェンシーに関連付け、コンプライアンス境界自体を定義する検索アクセス許可フィルターを作成します。 各エージェンシーに対して1つの検索アクセス許可フィルターを作成する必要があります。 セキュリティアクセス許可フィルターの作成の詳細については、「 [Configure permissions filtering For Content Search](permissions-filtering-for-content-search.md)」を参照してください。
  
以下は、コンプライアンスの境界に使用される検索アクセス許可フィルターを作成するために使用される構文です。

```powershell
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_<ComplianceAttribute>  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'" -Action <Action >
```

コマンドの各パラメーターの説明を次に示します。
  
- `FilterName`: フィルターの名前を指定します。 フィルターが使用されているエージェンシーを説明または特定する名前を使用します。

- `Users`: 実行するコンテンツ検索アクションにこのフィルターを適用するユーザーまたはグループを指定します。 このパラメーターは、コンプライアンスの境界に対して、フィルターを作成しているエージェンシーの役割グループ (手順3で作成したもの) を指定します。 メモこれは複数値パラメーターであるため、1つまたは複数の役割グループをコンマで区切って含めることができます。

- `Filters`: フィルターの検索条件を指定します。 コンプライアンスの境界に対して、次のフィルターを定義します。 それぞれは、コンテンツの場所に適用されます。 

    - `Mailbox`: パラメーターで定義されている役割グループが検索できるメールボックスを指定し  `Users` ます。 コンプライアンスの境界の場合、  *ComplianceAttribute*  は、手順1と属性  *値*  で指定したものと同じであり、エージェンシーを指定します。 このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーにあるメールボックスのみを検索できます。たとえば、のように `"Mailbox_Department -eq 'FourthCoffee'"` なります。 

    - `Site`: パラメーターで定義されている役割グループが検索できる OneDrive アカウントを指定し `Users` ます。 OneDrive フィルターの場合は、実際の文字列を使用し  `ComplianceAttribute` ます。 これは、手順2で送信したサポート要求の結果として、手順1で識別した属性にマッピングされ、OneDrive アカウントに同期されます。 *Attributevalue*  はエージェンシーを指定します。 このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーの OneDrive アカウントのみを検索できます。たとえば、のように  `"Site_ComplianceAttribute -eq 'FourthCoffee'"` なります。

    - `Site_Path`: パラメーターで定義されている役割グループが検索できる SharePoint サイトを指定し  `Users` ます。 *SharePointURL* は、役割グループのメンバーが検索できる機関内のサイトを指定します。 例: `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`。 `Site`とフィルターは、 `Site_Path` **-または** 演算子によって接続されていることに注意してください。

     > [!NOTE]
     > パラメーターの構文には、 `Filters` *フィルターリスト* が含まれています。 フィルターリストは、メールボックスフィルターと、コンマで区切られたサイトフィルターを含むフィルターです。 前の例では、コンマが **Mailbox_ComplianceAttribute** と **Site_ComplianceAttribute** であることに注意 `-Filters "Mailbox_<ComplianceAttribute>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq '<AttributeValue>' -or Site_Path -like '<SharePointURL>*'"` してください。 コンテンツ検索の実行中にこのフィルターが処理されると、フィルターリストから1つのメールボックスフィルターと1つのサイトフィルターという2つの検索アクセス許可のフィルターが作成されます。 フィルターリストを使用する代わりに、各エージェンシーに対して2つの異なる検索アクセス許可フィルターを作成することもできます。1つは、メールボックス属性に対する検索アクセス許可フィルターと、サイト属性用の1つのフィルターです。 どちらの場合も、結果は同じになります。 フィルターリストを使用するか、別の検索アクセス許可のフィルターを作成することは、優先度の高いものです。

- `Action`: フィルターが適用されるコンプライアンス検索アクションの種類を指定します。 たとえば、は、  `-Action Search` パラメーターで定義された役割グループのメンバーが `Users` コンテンツ検索を実行するときにのみフィルターを適用します。 この場合、検索結果をエクスポートするときに、フィルターは適用されません。 コンプライアンスの境界の場合は、を使用して、  `-Action All` すべての検索操作にフィルターが適用されるようにします。 

    コンテンツ検索アクションの一覧については、「 [Configure permissions filtering For Content search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)」の「new-compliancesecurityfilter」セクションを参照してください。

Contoso のコンプライアンスの境界シナリオをサポートするために作成される2つの検索アクセス許可フィルターの例を示します。 これらの例にはいずれもコンマ区切りのフィルター リストが含まれています。メールボックスとサイトのフィルターが同じ検索アクセス許可フィルターに含まれており、コンマで区切られています。
  
### <a name="fourth-coffee"></a>4番目のコーヒー

```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```

### <a name="coho-winery"></a>コーホーワイナリー

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-intra-agency-investigations"></a>手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する

最後の手順として、セキュリティ & コンプライアンスセンターで電子情報開示ケースを作成し、手順3で作成した役割グループをケースのメンバーとして追加します。 これにより、コンプライアンスの境界を使用する2つの重要な特徴が得られるようになります。
  
- ケースに追加された役割グループのメンバーのみが、セキュリティ & コンプライアンスセンターでそのケースを参照してアクセスできるようになります。 たとえば、4番目のコーヒーの捜査官の役割グループがケースの唯一のメンバーである場合、その4番目のコーヒー eDiscovery Managers 役割グループ (または他の任意の役割グループのメンバー) のメンバーは、ケースを表示またはアクセスできません。

- ケースに割り当てられた役割グループのメンバーが、そのケースに関連付けられている検索を実行すると、それらは、手順4で作成した検索アクセス許可フィルターによって定義された、エージェンシー内のコンテンツの場所のみを検索できます。

ケースを作成してメンバーを割り当てるには、次のようにします。

1. セキュリティ & コンプライアンスセンターの **電子** 情報開示または **高度な電子情報開示** ページに移動し、ケースを作成します。

2. 電子情報開示ケースの一覧で、作成したケースの名前をクリックします。

3. [**このケースの管理**] ページの [**役割グループの管理**] で、[追加] アイコン [追加] をクリックし ![ ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add** ます。

    ![電子情報開示ケースのメンバーとして役割グループを追加する](../media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. 役割グループの一覧で、手順3で作成した役割グループの1つを選択し、[ **追加**] をクリックします。

5. [**このケースの管理**] ポップアップで [**保存**] をクリックして変更を保存します。

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a>複数地域環境でのコンテンツの検索とエクスポート

また、検索アクセス許可フィルターを使用すると、エクスポート用にコンテンツをルーティングする場所を制御したり、 [SharePoint 複数地域環境](https://go.microsoft.com/fwlink/?linkid=860840)でコンテンツの場所を検索するときに検索できるデータセンターを制御したりすることもできます。
  
- **検索結果をエクスポートする:** 特定のデータセンターから Exchange メールボックス、SharePoint サイト、および OneDrive アカウントから検索結果をエクスポートすることができます。 これは、検索結果のエクスポート元となるデータセンターの場所を指定できることを意味します。

    **New-compliancesecurityfilter** または **new-compliancesecurityfilter** コマンドレットに **Region** パラメーターを使用して、エクスポートがルーティングされるデータセンターを作成または変更します。
  
    |**パラメーターの値**|**データセンターの場所**|
    |:-----|:-----|
    |NAM  <br/> |北米 (データセンターは米国)  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN <br/> |カナダ|
    |||

- **コンテンツ検索をルーティングする:** SharePoint サイトと OneDrive アカウントのコンテンツ検索をサテライトデータセンターにルーティングできます。 これは、検索を実行するデータセンターの場所を指定できることを意味します。

    **Region** パラメーターに次のいずれかの値を使用して、SharePoint サイトと OneDrive アカウントを検索するときに検索が実行されるデータセンターの場所を制御します。 
  
    |**パラメーターの値**|**SharePoint のデータセンタールーティング場所**|
    |:-----|:-----|
    |NAM  <br/> |電源  <br/> |
    |EUR  <br/> |ヨーロッパ  <br/> |
    |APC  <br/> |アジア太平洋  <br/> |
    |CAN  <br/> |電源  <br/> |
    |AUS  <br/> |アジア太平洋  <br/> |
    |KOR  <br/> |組織の既定のデータセンター  <br/> |
    |GBR  <br/> |ヨーロッパ  <br/> |
    |JPN  <br/> |アジア太平洋  <br/> |
    |IND  <br/> |アジア太平洋  <br/> |
    |語頭  <br/> |電源  <br/> |
    |も  <br/> |ヨーロッパ |
    |BRA  <br/> |北米データセンター |
    |||

   検索アクセス許可フィルターに **Region** パラメーターを指定しない場合、組織のプライマリ SharePoint 地域が検索されます。 検索結果は、最も近いデータセンターにエクスポートされます。

   概念を簡単にするために、 **Region** パラメーターは、SharePoint および OneDrive でコンテンツを検索するために使用されるデータセンターを制御します。 Exchange コンテンツ検索はデータセンターの地理的な場所によってバインドされていないため、Exchange のコンテンツを検索する場合には適用されません。 また、同じ **Region** パラメーター値は、エクスポートがルーティングされるデータセンターを示す場合もあります。 このことは、多くの場合、地理 boarders 間でのデータの移動を制御するために必要になります。

> [!NOTE]
> 上級電子情報開示を使用している場合、 **region** パラメーターはデータのエクスポート元となる地域を制御しません。 データは、組織のプライマリデータセンターからエクスポートされます。 また、SharePoint および OneDrive でのコンテンツの検索は、データセンターの地理的な場所に拘束されません。 すべてのデータセンターが検索されます。 高度な電子情報開示の詳細については、「 [Microsoft 365 の高度な電子情報開示ソリューションの概要](overview-ediscovery-20.md)」を参照してください。

ここでは、コンプライアンスの境界に対して検索アクセス許可のフィルターを作成するときに **Region** パラメーターを使用する例を示します。 この場合は、4つ目のコーヒー子会社が北米に配置されており、Coho がヨーロッパにあることを前提としています。 
  
```powershell
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```

複数地域環境でコンテンツを検索してエクスポートする場合は、次の点に注意してください。
  
- Exchange メールボックスの検索は、**Region** パラメーターにより制御されません。 メールボックスを検索すると、すべてのデータセンターが検索されます。 検索アクセス許可フィルターを作成または変更するときに、Exchange メールボックスの検索対象となる範囲を制限するには、 **Filters** パラメーターを使用します。 

- 電子情報開示マネージャーが複数の SharePoint 地域を検索する必要がある場合は、検索アクセス許可フィルターで、SharePoint サイトまたは OneDrive アカウントが配置されている地域を指定するために、その電子情報開示マネージャーに対して使用する別のユーザーアカウントを作成する必要があります。 この設定の詳細については、「 [コンテンツ検索](content-search.md#searching-for-content-in-a-sharepoint-multi-geo-environment)」の「SharePoint の複数地域環境でコンテンツを検索する」を参照してください。

- SharePoint および OneDrive でコンテンツを検索する場合、 **Region** パラメーターは、電子情報開示マネージャーが電子情報開示の調査を行うプライマリまたはサテライトの場所を検索します。 電子情報開示マネージャーが、検索アクセス許可フィルターで指定されている地域外の SharePoint および OneDrive サイトを検索すると、検索結果は返されません。

- 検索結果をエクスポートすると、すべてのコンテンツの場所 (Exchange、Skype for Business、SharePoint、OneDrive、およびコンテンツ検索ツールを使用して検索できるその他のサービスを含む) からのコンテンツが、 **Region** パラメーターで指定されたデータセンター内の Azure ストレージの場所にアップロードされます。 これにより、管理された境界を越えてコンテンツをエクスポートすることを許可しないことで、組織のコンプライアンスを実現できます。 検索アクセス許可フィルターで地域が指定されていない場合、コンテンツは組織のプライマリデータセンターにアップロードされます。

- 既存の検索アクセス許可フィルターを編集して、次のコマンドを実行し、地域を追加または変更することができます。

    ```powershell
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```

## <a name="using-compliance-boundaries-for-sharepoint-hub-sites"></a>SharePoint ハブサイトのコンプライアンス境界の使用

[SharePoint ハブサイト](https://docs.microsoft.com/sharepoint/dev/features/hub-site/hub-site-overview) は、多くの場合、電子情報開示のコンプライアンスの境界と同じ地理的または省庁の境界に沿っています。 これは、ハブサイトのサイト ID プロパティを使用して、コンプライアンスの境界を作成できることを意味します。 これを行うには、SharePoint Online PowerShell で [get-spohubsite](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spohubsite#examples) コマンドレットを使用してハブサイトの SiteId を取得し、次にその値を department ID プロパティに使用して、検索アクセス許可フィルターを作成します。

SharePoint ハブサイトの検索アクセス許可フィルターを作成するには、次の構文を使用します。

```powershell
New-ComplianceSecurityFilter -FilterName <Filter Name> -Users <User or Group> -Filters "Site_Departmentid -eq '{SiteId of hub site}'" -Action ALL
```

次に、Coho (コーホーワイナリー) エージェンシーのハブサイトの検索アクセス許可フィルターを作成する例を示します。

```powershell
New-ComplianceSecurityFilter -FilterName "Coho Winery Hub Site Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Site_Departmentid -eq '44252d09-62c4-4913-9eb0-a2a8b8d7f863'" -Action ALL
```

## <a name="compliance-boundary-limitations"></a>コンプライアンス境界の制限

電子情報開示ケースを管理する場合、およびコンプライアンスの境界を使用する調査を行う場合は、次の制限事項に注意してください。
  
- 検索を作成して実行するときに、機関以外のコンテンツの場所を選択することができます。 ただし、検索のアクセス許可フィルターがあるため、これらの場所からのコンテンツは、検索結果に含まれません。

- コンプライアンスの境界は、電子情報開示ケースの保留リストには適用されません。 つまり、ある機関の電子情報開示マネージャーが、保留中の別の機関にユーザーを配置することができます。 ただし、電子情報開示マネージャーが保留にされているユーザーのコンテンツの場所を検索する場合は、コンプライアンスの境界が適用されます。 つまり、電子情報開示マネージャーは、ユーザーを保留にすることはできても、ユーザーのコンテンツの場所を検索することはできません。

    また、保留リストは、機関のコンテンツの場所にのみ適用されます。

- 検索アクセス許可のフィルターは、Exchange のパブリックフォルダーには適用されません。

## <a name="more-information"></a>詳細情報

- メールボックスのライセンスが解除されているか、削除されている場合、Azure AD 属性はメールボックスと同期されなくなります。 メールボックスが削除されたときにホールドが設定されていた場合でも、メールボックスが削除される前に、Azure AD 属性が最後に同期された時点に基づいて、メールボックスに保持されたコンテンツは、コンプライアンス境界または検索アクセス許可フィルターの対象となります。 

    また、メールボックスのライセンスが解除されているか、削除されている場合、ユーザーのメールボックスと OneDrive アカウントの間の同期は停止します。 OneDrive アカウントのコンプライアンス属性の最後にスタンプされた値は、有効のままです。

- コンプライアンス属性は、ユーザーの Exchange メールボックスから、7日ごとに OneDrive アカウントに同期されます。 前述したように、この同期は、ユーザーが Exchange Online と SharePoint Online の両方のライセンスを割り当てられており、ユーザーのメールボックスが少なくとも 10 MB の場合にのみ発生します。

- ユーザーのメールボックスと OneDrive アカウントの両方に対して実装されたコンプライアンス境界および検索アクセス許可のフィルターが適用されている場合は、ユーザーのメールボックスを削除しないで、OneDrive アカウントを削除しないことをお勧めします。 言い換えると、ユーザーのメールボックスを削除した場合は、そのユーザーの OneDrive アカウントも削除する必要があります。

- ユーザーが複数の OneDrive アカウントを所有しているような状況 (従業員を返すなど) があります。 このような場合、Azure AD のユーザーに関連付けられているプライマリ OneDrive アカウントのみが同期されます。

- コンプライアンスの境界および検索アクセス許可のフィルターは、Exchange、OneDrive、SharePoint のコンテンツにスタンプされている属性と、このスタンプされたコンテンツの次のインデックス作成によって異なります。 

- `-not()`コンテンツベースのコンプライアンス境界には、除外フィルター (検索アクセス許可フィルターでの使用など) を使用することをお勧めしません。 最近更新された属性を持つコンテンツがインデックス付けされていない場合、除外フィルターを使用しても予期しない結果が発生する 

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**検索アクセス許可フィルターを作成および管理できるユーザー (New-ComplianceSecurityFilter と Set-ComplianceSecurityFilter コマンドレットを使用)**
  
検索アクセス許可のフィルターを作成、表示、および変更するには、セキュリティ & コンプライアンスセンターの組織の管理役割グループのメンバーである必要があります。
  
**電子情報開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、どのようにして1つのエージェンシーでコンテンツを検索しますか?**
  
電子情報開示マネージャーは、検索を特定のエージェンシーに制限するパラメーターを検索クエリに追加できます。 たとえば、組織で **CustomAttribute10** プロパティを指定してエージェンシーを区別する場合、次のものを検索クエリに追加して、特定のエージェンシーのメールボックスと OneDrive アカウントを検索することができます  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>` 。
  
**検索アクセス許可フィルターでコンプライアンス属性として使用されている属性の値が変更された場合はどうなりますか。**
  
検索アクセス許可フィルターで使用される属性の値が変更された場合に、コンプライアンスの境界を適用するには最大3日かかります。 たとえば、Contoso 社のシナリオでは、第4のコーヒーエージェンシーのユーザーが Coho (コーホーワイナリー) エージェンシーに転送されるとします。 その結果、ユーザーオブジェクトの **Department** 属性の値が、"4 *thコーヒー* " から " *cohowinery*" に変更されます。 このような状況では、4番目のコーヒー eDiscovery および投資家が、属性が変更された後、そのユーザーのために3日間、検索結果を取得します。 同様に、Coho の電子情報開示マネージャーと調査担当者がユーザーの検索結果を取得するまで最大3日かかります。
  
**電子情報開示マネージャーは、2つの異なるコンプライアンス境界からのコンテンツを表示できますか。**
  
はい。この操作は、両方の機関に可視性を持つ役割グループに電子情報開示マネージャーを追加することによって、Exchange メールボックスを検索するときに実行できます。 ただし、SharePoint サイトと OneDrive アカウントを検索している場合、電子情報開示マネージャーは、省庁が同じ地域または地理的な場所にある場合にのみ、異なるコンプライアンス境界でコンテンツを検索できます。 **注:** サイトのこの制限は、SharePoint のコンテンツを検索することはできません。また、OneDrive は地理的な場所によってはバインドされていません。
  
**検索アクセス許可のフィルターは、電子情報開示のケース保持、Microsoft 365 の保持ポリシー、DLP に対して機能しますか?**
  
いいえ、現時点ではできません。
  
**コンテンツのエクスポート先を制御する地域を指定したが、その地域に SharePoint 組織が存在しない場合、SharePoint を検索することはできますか?**
  
検索アクセス許可フィルターで指定されている地域が組織内に存在しない場合は、既定の地域が検索されます。
  
**組織内で作成できる検索アクセス許可のフィルターの最大数はいくつですか。**
  
組織で作成できる検索アクセス許可フィルターの数に制限はありません。 ただし、検索アクセス許可フィルターが 100 個以上ある場合、検索のパフォーマンスに影響を与えます。 組織内の検索アクセス許可フィルターの数を可能な限り小さくするには、Exchange、SharePoint、および OneDrive のルールを可能な限り1つの検索アクセス許可フィルターにまとめるフィルターを作成します。
