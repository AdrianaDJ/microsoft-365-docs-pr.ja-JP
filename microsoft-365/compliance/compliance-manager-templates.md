---
title: Microsoft コンプライアンスマネージャーの評価テンプレートを使用する
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft コンプライアンスマネージャーで評価を作成するためのテンプレートの使用方法と管理方法について説明します。 書式設定された Excel ファイルを使用してテンプレートを作成および変更します。
ms.openlocfilehash: cc3092e486e4f25fa1edad1ff64e638410cf3a63
ms.sourcegitcommit: ccbb405227880f40581c3cdfb974368a29d496f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48791813"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>コンプライアンスマネージャーの評価テンプレートを使用する

**この記事の内容****テンプレート** のしくみと、[評価テンプレート] ページから **それらを管理する方法に** ついて説明します。 新しいテンプレートを **作成** し、既存のテンプレートを **変更** し、 **テンプレートのデータを Excel で書式設定** し、テンプレート **レポート** をエクスポートする方法について説明します。

> [!IMPORTANT]
> 組織で使用できる評価テンプレートは、使用許諾契約によって異なります。 [詳細を確認](https://go.microsoft.com/fwlink/?linkid=2132371)します。

## <a name="templates-overview"></a>テンプレートの概要

テンプレートは、コンプライアンスマネージャーで評価を作成するためのフレームワークです。 これには、特定の製品を使用した証明書の要件を満たすためのコントロールが含まれています。 コンプライアンスマネージャーは、組織がデータの収集と使用を管理する国内、地域、および業界固有の要件に準拠するための包括的なテンプレートのセットを提供します。

## <a name="list-of-pre-built-templates-for-assessments"></a>評価用に作成済みテンプレートの一覧

コンプライアンスマネージャーには、さまざまな規制や規格に準拠するために役立つ評価を作成するためのテンプレートが用意されています。 コンプライアンスマネージャーによって提供される [テンプレートの一覧](compliance-manager-templates-list.md) を表示します。 新しいテンプレートが定期的に追加されるので、リストをよく確認してください。

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>[評価テンプレート] ページでのテンプレートの表示と管理

コンプライアンスマネージャーの [評価テンプレート] ページには、テンプレートと主要な詳細情報の一覧が表示されます。 リストには、コンプライアンスマネージャーによって提供されるテンプレートと、組織で変更または作成されたすべてのテンプレートが含まれています。 フィルターを適用して、証明書、製品の範囲、国、業種、作成者、および評価の作成にテンプレートが有効になっているかどうかに基づいて、テンプレートを検索できます。

行からテンプレートを選択して、[詳細] ページを表示します。 このページには、テンプレートの説明と、証明、スコープ、およびコントロールの詳細についての情報が記載されています。 このページから適切なボタンを選択して、評価を作成したり、テンプレートデータを Excel にエクスポートしたり、テンプレートを変更したりすることができます。

## <a name="creating-and-modifying-templates-overview"></a>テンプレートの作成と変更の概要

既存のテンプレートを変更したり、独自の新しいテンプレートを作成したりするには、特別に書式設定された Excel ワークシート ([例: download](https://go.microsoft.com/fwlink/?linkid=2124865)) を使用して必要なコントロールデータを組み立てます。 ワークシートを完成させた後、テンプレートを作成または変更する過程で、コンプライアンスマネージャーにインポートします。

> [!NOTE]
> スプレッドシートには、使用する必要がある特定の形式とスキーマがあります。また、コンプライアンスマネージャーに正しくインポートされません。 [書式設定の手順](#formatting-your-template-data-with-excel)は次のとおりです。

**必要な役割**

グローバル管理者またはコンプライアンス管理者の管理役割を持つユーザーのみがテンプレートを作成および変更できます。 [役割とアクセス許可](compliance-manager-setup.md#set-user-permissions-and-assign-roles)の詳細について説明します。

## <a name="create-a-new-template"></a>新しいテンプレートを作成する

独自の新しいテンプレート (カスタム評価の作成に使用) を作成するには、次の手順を実行します。

1. コンプライアンスマネージャーの [ **評価テンプレート** ] ページに移動します。
2. [ **新しいテンプレートの作成** ] を選択します。 テンプレートの作成ウィザードが開きます。
3. 作成するテンプレートの種類を選択します。 この場合は、[ **カスタムテンプレートの作成** ] を選択し、[ **次へ** ] を選択します。
4. [ **ファイルのアップロード** ] 画面で、[ **参照** ] を選択して、必要なすべてのテンプレートデータを含む書式設定された Excel ファイルを検索してアップロードします ( [ファイルを適切に書式設定するための手順を](#formatting-your-template-data-with-excel)参照してください)。
5. ファイルに問題がない場合は、アップロードされたファイルの名前が表示されます。 [ **次** へ] を選択して続行します。 (ファイルを変更する必要がある場合は、[ **別のファイルをアップロード** する] を選択します)。
    - ファイルにエラーがある場合は、上部にエラーメッセージが表示されます。 ファイルを修正し、再度アップロードする必要があります。 スプレッドシートの書式が正しく設定されていない場合や、特定のフィールドに無効な情報がある場合は、エラーが発生します ( [書式設定の手順](#formatting-your-template-data-with-excel)を再度参照してください)。  
    
6. [ **レビューと終了** ] 画面には、向上したアクションとコントロールの数、およびテンプレートの最大スコアが表示されます。 承認の準備ができたら、[テンプレートの作成] を選択し **ます。** (変更する必要がある場合は、[ **戻る** ] を選択してください)。
7. 最後の画面で新しいテンプレートが作成されたことを確認します。 [ **完了** ] を選択してウィザードを終了します。
8. 新しいテンプレートの詳細ページが表示され、そこで評価を [作成](compliance-manager-assessments.md#create-your-own-custom-assessment)できます。

## <a name="formatting-your-template-data-with-excel"></a>Excel でテンプレートデータの書式を設定する

テンプレートの作成に使用する Excel スプレッドシートには、次の4つのタブが含まれています。これらは3つ必要です。

1. [テンプレート](#template-tab) (必須)
2. [Controlfamily](#controlfamily-tab) (必須)
3. [アクション](#actions-tab) (必須)
4. [次元](#dimensions-tab) (省略可能)

ワークシートにテンプレートデータを入力するときは、ワークシートに  **上記の順序でタブを含める必要があり** ます。そうしないと、データはテンプレートに正常にインポートされません。

##### <a name="template-tab"></a>[テンプレート] タブ

[ **テンプレート** ] タブが必要です。 このタブの情報は、テンプレートに関するメタデータを提供します。 必要な列が4つあります。 以下に示すように、列は、Excel シートの順序を保持する必要があります。 4つの列の **後** に独自の列を追加して、独自の次元を提供することができます。 その場合は、 [以下の手順](#dimensions-tab)を使用して、それらを [ **ディメンション** ] タブに追加してください。

- **title** : これはテンプレートのタイトルで、一意である必要があります。 独自のテンプレートやコンプライアンスマネージャーテンプレートを含む、コンプライアンスマネージャーの他のテンプレートと名前を共有することはできません。

- **製品** : これは必須のディメンションです。 テンプレートに関連付けられている製品を一覧表示します。

- **サーティフィケーション** : これは、テンプレートに使用している規制です。

- **inScopeServices** : これは、この評価が対応する製品内のサービスです (たとえば、製品として Office 365 を指定した場合、Microsoft Teams は、範囲内のサービスになる可能性があります)。 2つのセミコロンで区切られた複数のサービスを一覧表示できます。

> [!NOTE]
> **製品** および **証明書** のセルに挿入するデータは、スプレッドシートをインポートしてテンプレートを作成またはカスタマイズした後で編集することはできません。 また、同じ **製品/証明書** の組み合わせを持つ2つの評価をグループに含めることはできません。 同じ製品/証明書の組み合わせを持つ複数のテンプレートを使用できます。

##### <a name="controlfamily-tab"></a>ControlFamily タブ

[ **Controlfamily** ] タブが必要です。  このタブの必須の列は、サンプルスプレッドシートで提供される順序に従う必要があります。

- **controlName** : これは、証明書、標準、または規制からのコントロール名です。通常は ID の一種です。 コントロール名は、テンプレート内で一意である必要があります。 スプレッドシートに同じ名前を持つ複数のコントロールを設定することはできません。

- **controlfamily** : コントロールの広範なグループを識別する、controlfamily の単語または語句を指定します。 ControlFamily は、一意である必要はありません。スプレッドシートに複数回表示することができます。 同じ controlFamily を複数のテンプレートに表示することもできますが、相互に関係はありません。 各 controlFamily は、少なくとも1つのコントロールにマップする必要があります。

- **controltitle** : コントロールのタイトルを指定します。 ControlName は参照コードですが、タイトルは一般的に規制で見られるリッチテキスト形式です。

- **controldescription** : コントロールの説明を入力します。

- **Controlactiontitle** : これは、このコントロールに関連付けるアクションのタイトルです。 複数のアクションを追加するには、2つのセミコロンで区切ってスペースを空けないようにします。 リストに含まれるすべてのコントロールには少なくとも1つのアクションが必要であり、アクションが存在する必要があります (つまり、同じスプレッドシートの [ **Actions** ] タブに表示されているアクション、別のテンプレートに存在するアクション、または Microsoft によって作成されたアクション) を一覧表示できます。 異なるコントロールは同じアクションを参照できます。

##### <a name="actions-tab"></a>[操作] タブ

[ **Actions** ] タブが必要です。  組織によって管理される改善アクションを指定します。これは、コンプライアンスマネージャーに既に存在する Microsoft のアクションではありません。 このタブに必要な列は、サンプルスプレッドシートで提供される順序に従う必要があります。

- **Actiontitle** : アクションのタイトルです。必須のフィールドです。 指定するタイトルは一意である必要があります。 **重要** : 既に存在するアクション (別のテンプレートなど) を参照し、その後の列でその要素のいずれかを変更すると、それらの変更は他のテンプレートの同じアクションに反映されます。

- **implementationType** : この必須フィールドに、次の3つの実装の種類のいずれかを一覧表示します。
    - 組織のシステム、資産、データ、および人員の機密性、整合性、および可用性を保護するために、ユーザーとプロセスによって実装される **運用** アクション (例: セキュリティの認識とトレーニング)
    - **技術的** な処置: 情報システムのハードウェア、ソフトウェア、またはファームウェアコンポーネントに含まれるテクノロジとメカニズムを使用して、組織のシステムとデータの機密性、整合性、可用性を保護します (例: 多要素認証)
    - **ドキュメント** -文書化されたポリシーと手順によって実装されるアクション組織のシステム、資産、データ、および人員の機密性、整合性、および可用性を保護するために必要な制御を確立し、定義します (例: 情報セキュリティポリシー)

- **actionscore** : この必須フィールドで、アクションの数値スコア値を指定します。 この値は、1 ~ 99 の範囲の整数であることが必要です。0、null、または空白にすることはできません。 数値が大きいほど、コンプライアンスの姿勢が向上します。 次の図は、コンプライアンスマネージャーがコントロールをスコアする方法を示しています。

![コンプライアンスマネージャーコントロールのポイント値](../media/compliance-score-action-scoring.png "コンプライアンスマネージャーコントロールのポイント値")

- **Actiondescriptiontitle** : これは、説明のタイトルです。必須です。 この説明タイトルでは、複数のテンプレートで同じアクションを実行し、各テンプレートで異なる説明を表示することができます。  このフィールドを使用すると、説明で参照されているテンプレートを明確にすることができます。 ほとんどの場合、このフィールドに作成するテンプレートの名前を入れることができます。

- **actiondescription** : アクションの説明を入力します。 太字のテキストやハイパーリンクなどの書式を適用することができます。 これは必須フィールドです。

- **ディメンション-アクションの目的** : これは省略可能なフィールドです。 これを含める場合は、ヘッダーに "dimension-" プレフィックスを含める必要があります。 ここに含めるディメンションは、コンプライアンスマネージャーのフィルターとして使用され、コンプライアンスマネージャーの [アクションの詳細] ページに表示されます。

##### <a name="dimensions-tab"></a>[ディメンション] タブ

[ **次元** ] タブはオプションです。 ただし、既に作成したテンプレートに存在しない場合、または Microsoft のテンプレートでディメンションを参照する場合は、ここで指定する必要があります。 このタブの列を次に示します。

- **Dimensionkey** : リストとして "product"、"証明書"、"アクションの目的"
- **Dimensionvalue** : 例: Office 365、HIPPA、予防的、検出

既存のディメンションを表示するには、[ **テナントの管理** ] に移動し、[ **ディメンション** ] タブを選択します。また、既存のテンプレートをエクスポートすると、エクスポートされたスプレッドシートには、テンプレートで使用されているすべてのディメンションが一覧表示される [ **ディメンション** ] タブが表示されます。

## <a name="modify-a-template"></a>テンプレートを変更するには

コントロールを追加したり、改善アクションを追加または削除したりするなど、作成済みのテンプレートを変更する必要がある場合があります。 このプロセスは、テンプレートの作成プロセスに似ていますが、書式設定された Excel ファイルをテンプレートデータと共にアップロードします。

ただし、既存のテンプレートデータに加えた変更を使用してファイルに書式を設定することに注意する必要がある特定の詳細があります。 **保持する既存のデータが上書きされないように、これらの手順を慎重に確認することをお勧めします。**

### <a name="template-modification-process-steps"></a>テンプレート変更プロセスの手順

テンプレートを変更するには、次の手順を実行します。

1. [ **評価テンプレート** ] ページで、変更するテンプレートを選択します。これにより、詳細ページが表示されます。
2. [ **Excel へのエクスポート** ] を選択します。 すべてのテンプレートデータを含む Excel ファイルがダウンロードされます。 ファイルをローカルコンピューターに保存します。
3. [次の手順に従って、Excel ファイルを変更](#formatting-your-excel-file-to-modify-a-template)して、テンプレートを変更してください。
4. Excel ファイルに変更を加えたら、ファイルを保存します。
5. テンプレートの詳細ページで、[ **テンプレートの変更** ] を選択して変更ウィザードを開始します。 
6. [ **ファイルのアップロード** ] 画面で、[ **参照** ] を選択して、Excel ファイルを検索してアップロードします。
7. ファイルに問題がない場合は、次の画面に、アップロードされたファイルの名前が表示されます。 [ **次** へ] を選択して続行します (ファイルを変更する必要がある場合は、[ **別のファイルをアップロード** する] を選択します)。
    - ファイルに問題がある場合は、上部にエラーメッセージが表示されています。 ファイルを修正し、再度アップロードする必要があります。 スプレッドシートの書式が正しく設定されていない場合や、特定のフィールドに無効な情報がある場合は、エラーが発生します。

8. [ **レビューと終了** ] 画面には、向上したアクションとコントロールの数、およびテンプレートの最大スコアが表示されます。 承認の準備ができたら、[ **次へ** ] を選択します。
9. 最後の画面で、テンプレートが変更されたことを確認します。 [ **完了** ] を選択してウィザードを終了します。

これで、テンプレートに加えた変更が含まれるようになります。 この変更されたテンプレートを使用する評価には、保留中の更新が表示されるようになったため、評価に対する更新を承諾して、テンプレートに加えられた変更を反映する必要があります。 [評価の更新](compliance-manager-assessments.md#accepting-updates-to-assessments)に関する詳細をご覧ください。

> [!NOTE]
> 英語以外の言語でコンプライアンスマネージャーを使用している場合は、Excel にテンプレートをエクスポートするときに、一部のテキストが英語で表示されることがわかります。 コントロールで認識されるようにするには、アクションのタイトル (向上アクションと Microsoft アクションの両方) が英語である必要があります。 アクションタイトルを変更する場合は、ファイルが正しくインポートされるように、そのタイトルを必ず英語で記述してください。

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Excel ファイルの書式を設定してテンプレートを変更する

以下のセクションに移動すると、必要な手順をすばやく見つけることができます。

- [メインテンプレートの属性を編集する](#edit-the-main-template-attributes)
- [改善アクションを追加する](#add-an-improvement-action)
- [改善アクションの情報を編集する](#edit-an-improvement-actions-information)
- [改善アクションの名前を変更する](#change-an-improvement-actions-name)
- [改善アクションを削除する](#remove-an-improvement-action)
- [コントロールを削除する](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>メインテンプレートの属性を編集する

[ **テンプレート** ] タブでは、[ **タイトル** ] 列、 **inScopeServices** 列、および追加したその他の列の内容を編集できます。 ただし、[ **製品** ] 列または [ **証明書** ] 列の内容を編集することはできません。

#### <a name="add-an-improvement-action"></a>改善アクションを追加する

1. [ **操作** ] タブに移動します。既存のアクションの下にある最初の空の行の必須フィールドに情報を追加します。
2. [ **Controlfamily** ] タブに移動します。向上アクションがマップされているコントロールを含む行を検索します。 その行の **Controlactiontitle** 列に新しいアクションを追加します (このフィールド内の複数のアクションは、2つのセミコロンで区切って、スペースを空けないようにしてください)。
3. スプレッドシートを保存します。

#### <a name="edit-an-improvement-actions-information"></a>改善アクションの情報を編集する

改善アクションの情報は、 *タイトルを除き* 変更できます。 列 B 以降の任意のセルを編集することができます。その後、テンプレートにファイルをインポートすると、そのテンプレートの改善アクションに更新されたデータが含まれるようになります。

この操作を行うと、コンプライアンスマネージャーが新しい改善アクションになると見なされるため、 **Actiontitle** (列 A) を編集することはできません。 改善アクションの名前を変更する場合は、次の手順に従ってください。

#### <a name="change-an-improvement-actions-name"></a>改善アクションの名前を変更する

改善アクションの名前を変更する必要がある場合は、既存の名前を新しい名前に置き換えるように、スプレッドシートで明示的に指定する必要があります。 次の手順を実行します。

1. スプレッドシートの [ **Actions** ] タブで、列 a の後に新しい列をスプレッドシートに追加します。
2. 列 B のこの新しい列で、行 1: **Oldactiontitle** にヘッダーを入力します。
3. 列 A の内容をコピーして、列 B に貼り付けます。これにより、変更する必要がある既存の改善アクションのタイトルが列 B に配置されます。
4. 列 A、 **Actiontitle** で、古い名前を削除して、改善アクションの新しい名前に置き換えます。

アクションのタイトルは、向上アクションと Microsoft アクションに対して、コントロールで参照されているときに認識されるように、英語で記述する必要があることに注意してください。

#### <a name="remove-an-improvement-action"></a>改善アクションを削除する

ワークシートの行から向上したアクションを削除しても、編集中のテンプレートからアクションが削除 **されることはありません** 。 代わりに、以下のプロセスに従います。

1. [ **Actions** ] タブで、列 a として新しい列を挿入し、行番号1の見出し行に " **操作** " と入力します。
2. 削除する改善アクションの行で、その行の列 A に **Delete** を置きます。
3. この改善アクションがコントロールによって参照されていないことを確認してください。 [ **Controlfamily** ] タブに移動して、列 F ( **controlactiontitle** ) の向上アクションのタイトルを検索します。
4. [ **Controlactiontitle** ] 列に改善されたアクションが見つかったら、それを削除します。
5. スプレッドシートを保存します。

スプレッドシートをテンプレートにインポートして戻すと、そのアクションはテンプレートから削除されます。 アクションをテンプレートから削除しても、アクションが完全に削除されるわけではありません。 そのアクションは、別のテンプレートで引き続き参照できます。

コントロールで参照されている最新の改善アクションを削除している場合は、コントロールを削除する必要があります。

#### <a name="remove-a-control"></a>コントロールを削除する

コントロールを削除するには、上記の説明に従って、改善アクションを削除するのと同じ手順を実行します。 [ **Controlfamily** ] タブで、[ **操作** ] 列を追加し、削除するコントロールの横に [ **削除** ] を入力します。

## <a name="export-a-template"></a>テンプレートをエクスポートする

テンプレートのすべてのデータを含む Excel ファイルをエクスポートすることができます。 テンプレートを変更するには、テンプレートをエクスポートする必要があります。これは、 [変更プロセス](#modify-a-template)で編集およびアップロードする Excel ファイルです。

テンプレートをエクスポートするには、テンプレートの詳細ページに移動して、[ **Excel にエクスポート** ] ボタンを選択します。

コンプライアンスマネージャーテンプレートから拡張したテンプレートをエクスポートする場合、エクスポートされたファイルには、テンプレートに追加した属性のみが含まれることに注意してください。 エクスポートされたファイルには、Microsoft が提供する元のテンプレートデータは含まれません。 このようなレポートを取得するには、 [評価レポートをエクスポート](compliance-manager-assessments.md#export-an-assessment-report)する手順を参照してください。