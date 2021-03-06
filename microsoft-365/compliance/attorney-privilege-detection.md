---
title: 高度な電子情報開示で、弁護士クライアント特権の検出を設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 上級電子情報開示ケースのコンテンツを確認するときに、権限のあるコンテンツのマシン学習ベースの検出を使用するには、「弁護士クライアント特権検出モデル」を使用します。
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358043"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>高度な電子情報開示で、弁護士クライアント特権の検出を設定する

電子情報開示プロセスのレビューフェーズの主な重要な側面は、権限のあるコンテンツのドキュメントをレビューすることです。 Advanced eDiscovery は、このプロセスをより効率的にするために、権限のあるコンテンツの機械学習ベースの検出を行います。 この機能は *、"委任状-クライアント特権の検出*" と呼ばれます。

## <a name="how-does-it-work"></a>どのような仕組みなのか。

委任状の特権の検出が有効になっている場合、レビューセット内のすべてのドキュメントは、レビューセット内のデータを [分析](analyzing-data-in-review-set.md) するときに、弁護士クライアント特権検出モデルによって処理されます。 このモデルでは、次の2つのことを確認できます。

- 権限のあるコンテンツ–モデルでは、機械学習を使用して、ドキュメントに実際の法律上の内容が含まれている可能性を判断します。

- 参加者–弁護士クライアント特権検出の設定の一環として、組織の弁護士の一覧を提出する必要があります。 これを行うと、検出モデルはドキュメントの参加者と弁護士のリストを比較し、ドキュメントに 1 人以上の弁護士の参加者がいるかどうかを判断します。

このモデルでは、すべてのドキュメントに対して次の3つのプロパティが生成されます。

- **AttorneyClientPrivilegeScore:** ドキュメントが実際に有効である可能性。スコアの値は **0** から **1**です。

- **Hasattorney:** ドキュメントの参加者のいずれかが弁護士リストに含まれている場合、このプロパティは **true** に設定されます。それ以外の場合、値は **false**になります。 組織が弁護士リストをアップロードしていない場合も、値は **false** に設定されます。

- **IsPrivilege:****AttorneyClientPrivilegeScore**の値がしきい値を超える場合、*または*ドキュメントに弁護士の参加者がいる場合は、このプロパティを**true**に設定します。それ以外の場合、値は**false**に設定されます。

次のスクリーンショットに示すように、これらのプロパティ (および対応する値) は、レビューセット内のドキュメントのファイルメタデータに追加されます。

![ファイルメタデータに表示される、委任状のクライアント権限のプロパティ](../media/AeDAttorneyClientPrivilegeMetadata.png)

これら3つのプロパティは、レビューセット内でも検索できます。 詳細については、「 [review set でデータを照会する](review-set-search.md)」を参照してください。

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>弁護士クライアント特権検出モデルを設定する

弁護士クライアントの特権検出モデルを有効にするには、組織でそれを有効にしてから、弁護士リストをアップロードする必要があります。

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>手順 1: 弁護士クライアント特権の検出を有効にする

組織内の電子情報開示管理者 (電子情報開示マネージャーの役割グループの電子情報開示管理者サブグループのメンバー) であるユーザーは、高度な電子情報開示ケースでそのモデルを利用できるようにする必要があります。

1. セキュリティ & コンプライアンスセンターで、[ **電子情報開示 > Advanced ediscovery**] に移動します。

2. [ **高度な電子情報開示** ホーム] ページの [ **設定** ] タイルで、[ **グローバル分析設定の構成**] をクリックします。

   ![[実験的な機能の構成] を選択します。](../media/AeDExperimentalFeatures.png)

3. [ **分析設定** ] タブで、[ **弁護士-クライアント特権設定の管理**] を選択します。

4. **[弁護士/依頼人特権]** ポップアップ ページで、トグルを使用して機能をオンにし、**[保存]** を選択します。

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>手順 2: 弁護士の一覧をアップロードする (オプション)

事前に説明されている弁護士と法務担当者のための電子メールアドレスの一覧をアップロードすることをお勧めします。これまでに説明し **た、弁護士** および **権限** のあるユーザー権限検出モデルを十分に活用するには、組織で働いている弁護士および法務担当者の電子メールアドレスの一覧をアップロードすることをお勧めします 

弁護士側の特権検出モデルで使用する弁護士リストをアップロードするには、次のようにします。

1. .csvファイル (見出し行なし) を作成し、適切な各人のメール アドレスを別々の行に追加します。 このファイルをローカル コンピューターに保存します。

2. [ **高度な電子情報開示** ホーム] ページの [ **設定** ] タイルで、[ **実験的な実験機能を構成する**] を選択してから、[ **弁護士-クライアント特権設定の管理**] を選択します。

   [ **委任状-クライアント権限** ] ページが表示され、 **弁護士クライアント特権検出** トグルがオンになっています。

   ![委任状-クライアント特権のポップアップページ](../media/AeDUploadAttorneyList.png)

3. [ **参照** ] を選択し、手順1で作成した .csv ファイルを見つけて選択します。

4. [ **保存** ] を選択して、弁護士リストをアップロードします。

## <a name="use-the-attorney-client-privilege-detection-model"></a>弁護士クライアント特権検出モデルを使用する

このセクションの手順に従って、レビューセットのドキュメントに対して、弁護士クライアント特権検出を使用します。

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>手順 1: 弁護士クライアント特権検出モデルを使用してスマートタググループを作成する

レビュー プロセスで弁護士/依頼人特権の検出結果を確認する主な方法の 1 つは、スマート タグ グループを使用することです。 スマート タグ グループは、弁護士/依頼人特権の検出結果を示し、スマート タグ グループ内のタグの横に、結果をインラインで表示します。 これにより、ドキュメントのレビュー中に潜在的な権限のあるドキュメントをすばやく識別できます。 また、スマート タグ グループ内のタグを使用して、ドキュメントに特権付き、または特権なしのタグを付けることもできます。 スマートタグの詳細については、「 [Advanced eDiscovery でスマートタグを設定](smart-tags.md)する」を参照してください。

1. 手順1で分析したドキュメントを含むレビューセットで、[ **レビューセットの管理** ] を選択し、[ **タグの管理**] を選択します。
 
2. [ **タグ**] で、[ **グループの追加** ] の横にあるプルダウンを選択し、[ **スマートタググループの追加**] を選択します。

   ![[スマートタググループの追加] を選択します。](../media/AeDCreateSmartTag.png)

3. [**スマートタグのモデルを選択**します] ページで、[**弁護士-クライアント権限**] の横にある **[選択]** を選択します。

   " **弁護士-クライアント" 特権** という名前のタググループが表示されます。 これには、モデルによって生成される結果に対応する、 **正** と **負**の2つの子タグがあります。

   ![弁護士-クライアント特権スマートタググループ](../media/AeDAttorneyClientSmartTagGroup.png)

3. 確認には、必要に応じて、タググループとタグの名前を変更します。 たとえば、 **正** の値を **Privileged** に、 **負の値** を **特権を持たない**名前に変更できます。

### <a name="step-2-analyze-a-review-set"></a>手順 2: レビューセットを分析する

レビューセット内のドキュメントを分析する場合は、弁護士クライアント特権検出モデルも実行され、対応するプロパティ (「 [操作方法](#how-does-it-work) 」で説明されています) がレビューセットのすべてのドキュメントに追加されます。 レビューセットでのデータの分析の詳細については、「 [Advanced eDiscovery でデータを分析セットに分析する](analyzing-data-in-review-set.md)」を参照してください。

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>手順 3: スマートタググループを使用して権限のあるコンテンツを確認する

レビューセットを分析し、スマートタグを設定したら、次の手順でドキュメントをレビューします。 モデルでドキュメントが潜在的な特権を持っていると判断された場合、 **タグ付けパネル** 内の対応するスマートタグは、弁護士クライアント特権検出によって生成される次の結果を示します。

- ドキュメントに有効なコンテンツが含まれている場合は、対応するスマートタグ (この例では既定の**肯定**タグ) の横にラベル**リーガルコンテンツ**が表示されます。

- 組織の委任状リストに含まれている参加者がドキュメントにある場合、対応するスマートタグ (この場合は、既定の**正数**タグ) の横にラベル**弁護士**が表示されます。

- ドキュメントのコンテンツが実際には法律上、弁護士リストに含まれ *て* いる可能性があるコンテンツがある場合、 **法的コンテンツ**  と **弁護士** の両方のラベルが表示されます。 

ドキュメントに法律上の正当なコンテンツが含まれていないか、または弁護士リストからの参加者が含まれていないことがモデルによって判断された場合は、タグ付けパネルにラベルは表示されません。

たとえば、次のスクリーンショットは2つのドキュメントを示しています。 最初のものには、実際には法律上、法律の一覧に含まれている参加者が存在するコンテンツが含まれています。 2番目には、ラベルは表示されません。

![弁護士および法的コンテンツラベルを含むドキュメント](../media/AeDTaggingPanelLegalContentAttorney.png)

![ラベルなしのドキュメント](../media/AeDTaggingPanelNegative.png)

ドキュメントに権限のあるコンテンツが含まれているかどうかを確認したら、適切なタグでドキュメントにタグを付けます。
