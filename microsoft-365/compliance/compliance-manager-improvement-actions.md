---
title: Microsoft コンプライアンスマネージャーでの改善アクションの割り当てと完了
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
description: Microsoft コンプライアンスマネージャーのコントロールで実装とテストを実行する方法について説明します。 作業の割り当て、ドキュメントの保存、レポートのエクスポートを行います。
ms.openlocfilehash: 99b08ca1336c3f347764230896af47fe1486d4b2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204446"
---
# <a name="assign-and-complete-improvement-actions-in-compliance-manager"></a>コンプライアンスマネージャーでの改善アクションの割り当てと完了

**この記事の内容** この記事では、改善アクションを伴う **コンプライアンスワークフローを管理** する方法について説明します。 実装とテスト、**更新プログラムの管理**、および**レポート**のエクスポートに対する**改善アクションを割り当てる**方法について説明します。

## <a name="manage-compliance-workflows-with-improvement-actions"></a>向上アクションを伴うコンプライアンスワークフローを管理する

改善アクションにより、コンプライアンスアクティビティを集中管理できます。 各改善アクションには、データ保護の規則および標準に沿った統合に役立つ詳細な実装ガイダンスが用意されています。 実装とテストの作業を実行するために、組織内のユーザーにアクションを割り当てることができます。 ドキュメント、メモ、およびレコードの状態の更新をアクション内に保存することもできます。

すべての改善アクションは、[改善アクション] ページに一覧表示されます。 [改善アクションの表示の](compliance-manager-setup.md#improvement-actions-page)詳細については、「」を参照してください。

## <a name="improvement-actions-details-page"></a>向上アクションの詳細ページ

各改善アクションには、現在の状態、関連する標準および規制要件、推奨される実装ガイダンスを示す詳細ページがあります。 [技術的なアクション](compliance-score-calculation.md#technical-and-non-technical-actions) には、実装のための適切なソリューションを実現する [ **今すぐ起動の開始** リンクが含まれています。 実装とテストのドキュメントは、改善アクションの詳細ページに直接添付できます。

向上アクションの詳細ページを表示するには、次の操作を行います。

1. 向上したアクションのページに移動します。
2. 目的の改善アクションの行を選択すると、[詳細] ページが開きます。

画面の右上隅にある上下矢印を選択すると、リスト内の次または前の改善アクションを簡単に表示できます。 [改善アクション] ページでリストをフィルター処理した場合は、上または下に移動して、そのフィルター処理されたリスト内の次のアイテムに移動します。

## <a name="assign-improvement-actions"></a>改善アクションを割り当てる

改善アクションで実装を開始するには、自分で作業を行ったり、別のユーザーに割り当てたりすることができます。 割り当てられた人物は次のようになります。

- ビジネス ポリシーの所有者
- IT 担当者
- タスクを実行する責任を持つ別の従業員

適切な担当者を特定したら、その作業を実行するために十分な [コンプライアンスマネージャーの役割](compliance-manager-setup.md#set-user-permissions-and-assign-roles) を持っていることを確認してください。 次に、次の手順に従って、改善アクションを割り当てます。

1. [改善アクションの詳細] ページで、画面の左上のセクション付近にある [ **状態の編集** ] を選択します。

2. [状態の編集] ウィンドウで、[ **担当者] ボックスを** 選択して、ユーザーの **候補** リストを表示します。 リストからユーザーを選択することも、そのユーザーの電子メールアドレスを入力することもできます。

3. [ **保存して閉じる**] を選択します。 割り当てられたユーザーには、改善アクションが割り当てられていることを示す電子メールが送信されます。これには、向上アクションへの直接リンクがあります。

割り当てられたユーザーは、推奨されるアクションを実行できます。

## <a name="perform-work-and-store-documentation"></a>作業およびストアのドキュメントを実行する

実装とテストに関連するファイルやメモは、「 **メモとドキュメント** 」のセクションに直接アップロードできます。 この環境は、セキュリティで保護された一元的なリポジトリで、コンプライアンスの標準および規制を満たすための制御の満足度を示すのに役立ちます。 読み取り専用アクセス権を持つユーザーは、このセクションの内容を読み取ることができます。 編集権限を持つユーザーのみが、ファイルのアップロードとダウンロード、およびメモの入力や編集を行うことができます。

「 **メモとドキュメント** 」のセクションには、アップロードしたドキュメント、実装メモ、テストメモ、および追加メモのフィールドが含まれています。

#### <a name="uploaded-documents"></a>アップロードされたドキュメント

- [ **ドキュメントの管理** ] を選択して、関連するファイルをアップロードします。
- [ドキュメントの管理] ポップアップウィンドウが開いたら、[ **ドキュメントの追加**] を選択し、システムからファイルを選択します。 許可されるファイルの種類:
    - ドキュメント (.doc、.xls、.ppt、.pdf、.pdf)
    - 画像 (.jpg、.png)
    - ビデオ (mkv)
    - 圧縮ファイル (.zip、rar)
- ウィンドウでファイルを解決したら、[ **閉じる**] を選択すると、添付ファイルが自動的に保存されます。 アップロードした **ドキュメント**の下にファイルが表示されます。
- ドキュメントをダウンロードまたは削除するには、ドキュメントのリストの下にある [ **ドキュメントの管理** ] を選択します。 フライアウトウィンドウで、ドキュメント行を選択して強調表示にし、[ **ダウンロード** ] または [ **削除**] を選択します。

#### <a name="implementation-notes-test-notes-and-additional-notes"></a>実装に関する注意事項、テストメモ、および追加メモ

- これら3つのフィールドのいずれかでメモを追加するには、これらのフィールドの下にある [ **実装メモの編集** ] を選択します。
- フライアウトウィンドウが開いたら、テキストフィールドに「notes」と入力し、[ **保存して閉じる**] を選択します。
- メモを編集するには、[ **実装メモの編集**] を選択して編集を行ってから、[ **保存して閉じる**] を選択します。

メモフィールドに文字数の制限はありません。 [改善アクションの詳細] ページで簡単に表示および編集できるように、ノートを短くすることをお勧めします。

## <a name="change-improvement-action-status"></a>改善アクションの状態の変更

各改善アクションの実装の状態と日付、およびテストの状態と日付を記録することができます。 [ **実装** ] および [ **テスト状態** ] フィールドは、割り当てられた人物だけでなく、編集権限を持つすべてのユーザーが編集できます。

改善アクションの状態を編集するには、詳細ページの左上のセクションで [ **状態の編集** ] を選択します。 利用可能なフィールドとステータスのオプションを以下に示します。

- **実装の状態**
    - **実装されて** いません-アクションはまだ実装されていません
    - **実装** 済み-アクションの実装
    - **代替実装** -他のサードパーティ製ツールを使用した場合や、Microsoft の推奨事項に含まれていないその他のアクションを実行した場合は、このオプションを選択します。
    - **計画** 済み-実装に対して計画されたアクション
    - **範囲外** –アクションが組織に関連せず、スコアに寄与しない
- **実装日**: 実装の状態が "実装" または "代替実装" の場合に選択できるようになります。
- **テストの状態**: 実装状態が "実装" または "代替実装" の場合に選択できます。
    - **評価されませんでし** た-アクションはテストされていません
    - **成功** した実装は、査定官によって確認されています。
    - **失敗したリスクが低い** -テスト失敗、低リスク
    - **失敗中の危険度** -テスト失敗、中程度のリスク
    - **高リスクの失敗** –テスト失敗、高リスク
    - **範囲外** –操作は評価の対象外で、スコアに寄与しない
- **テスト日**: 予定表ポップアップを切り替えて日付を選択する

グループ間で共通のアクションを同期します。 同じグループ内の2つの異なる評価が、自分が管理する改善アクションを共有する場合、アクションの実装の詳細またはステータスに対して行ったすべての更新は、グループ内の他の評価でも同じアクションに自動的に同期されます。 この同期によって、1つの改善アクションを実装し、複数の規制間でいくつかの要件を満たすことができます。

## <a name="assign-improvement-action-to-assessor-for-completion"></a>完了の評価を査定活動に割り当てる

作業を完了し、テストを実施して、証拠をアップロードした後、次の手順では、評価の評価に対する改善アクションを割り当てます。 査定官は、作業を検証し、ドキュメントを調べて、適切なテスト状態を選択します。

**テストの状態が "成功" に設定されている場合**は、処理が完了し、達成されたポイントが達成された数を示します。 次に、これらのポイントは、全体的なコンプライアンススコアの方向に数えられます。

**[テストの状態] が [失敗] に設定されている場合**: アクションは要件を満たしていないため、評価元は、追加の作業について適切なユーザーに割り当てることができます。

## <a name="accepting-updates-to-improvement-actions"></a>改善アクションへの更新の受け入れ

改善アクションに対して更新プログラムが利用可能になると、その名前の横に通知が表示されます。 更新を受け入れるか、または後で期限を延長することができます。

#### <a name="what-causes-an-update"></a>更新プログラムの原因

スコアリング、オートメーション、またはスコープに関連する変更がある場合に更新が行われます。 変更には、規制の変更に基づく改善アクションに関する新しいガイダンス、または製品の変更が含まれることがあります。 組織によって管理される改善アクションのみが更新通知を受信します。

#### <a name="where-youll-see-assessment-update-notifications"></a>評価の更新通知を表示する場所

向上アクションが更新されると、[改善アクション] ページと関連する評価の詳細ページに、 **保留中の更新プログラム** ラベルが表示されます。

向上アクションの詳細ページに移動し、上部のバナーで [ **更新の確認** ] ボタンを選択して、変更に関する詳細を確認し、更新を承諾または延期します。

#### <a name="review-update-to-accept-or-defer"></a>承諾または延期の更新を確認する

[改善アクションの詳細] ページの [ **レビューの更新** ] を選択すると、画面の右側にフライアウトウィンドウが表示されます。 フライアウトのウィンドウには、更新プログラムに関する重要な詳細情報が表示されます。これには、評価に影響するものや、スコアおよびスコープの変更があります。

[ **更新の許可** ] を選択して、改善アクションへのすべての変更を承諾します。 **許可された変更は永続的**です。

> [!NOTE]
> アクションの更新を受け入れる場合、このアクションの他のバージョンまたはインスタンスに対する更新を承諾していることもあります。 技術的なアクションについては、更新によってテナント全体が伝達され、非技術的なアクションについてはグループ全体が伝達されます。

[ **キャンセル**] を選択すると、この更新は改善アクションに適用されません。 ただし、更新を受け入れるまで、 **保留中の更新** 通知が引き続き表示されます。

**更新を受け付けることを推奨する理由**

更新を承認することで、ソリューションの使用に関する最新のガイダンスを把握し、適切な改善措置を講じて、認定の要件を満たしていることを確認できます。

**更新プログラムを延期する必要がある理由**

[改善] アクションを含む評価を完了している場合は、更新を承諾する前に、その評価の作業を完了しておく必要があります。 [更新プログラムの確認] ウィンドウで [ **キャンセル** ] を選択すると、後で更新を延期することができます。

## <a name="export-a-report"></a>レポートをエクスポートする

画面の左上隅にある [ **エクスポート** ] を選択して、すべての改善アクションと、[改善アクション] ページに表示されるフィルターカテゴリを含む Excel ワークシートをダウンロードします。