---
title: 通信コンプライアンスのアラートを調査して修復する
description: Microsoft 365 の通信コンプライアンスアラートを調査および修復します。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: f214c1fcfa8a68695ca0c32a9807972a71ba7612
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087162"
---
# <a name="investigate-and-remediate-communication-compliance-alerts"></a>通信コンプライアンスのアラートを調査して修復する

通信コンプライアンスポリシーを構成した後は、ポリシー条件に一致するメッセージの問題に関する Microsoft 365 コンプライアンスセンターでの通知の受信を開始します。 ここにあるワークフローの手順に従って、アラートの問題を調査して修復します。

## <a name="investigate-alerts"></a>通知の調査

ポリシーによって検出された問題を調査するための最初の手順は、Microsoft 365 コンプライアンスセンターの通信コンプライアンスアラートを確認することです。 通知のグループ化をどのように表示するかによって、通知をすばやく調査するのに役立つ、コミュニケーションコンプライアンスソリューションの領域がいくつかあります。

- [**通信コンプライアンスポリシー] ページ**: [https://compliance.microsoft.com](https://compliance.microsoft.com) Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインするときに、[**通信コンプライアンス**] を選択して [通信コンプライアンス **ポリシー** ] ページを表示します。 このページには、Microsoft 365 組織に対して構成されている通信コンプライアンスポリシーと、推奨ポリシーテンプレートへのリンクが表示されます。 一覧に表示される各ポリシーには、確認が必要なアラートの数、エスカレーションされたアイテムの数、およびポリシーの現在の状態が含まれます。 ポリシーのどれかを選択すると、ポリシーに一致しているすべての保留中警告が表示されます。特定の通知を選択して、ポリシーの詳細ページを開き、修復アクションを開始します。
- **アラート**: **Communication compliance**  >  ポリシーの一致によってグループ化されたアラートの過去30日間が表示されるように、[通信コンプライアンス **アラート** に移動します。 このビューでは、重要度順に並べ替えられているほとんどの通知を生成している通信コンプライアンスポリシーをすばやく確認できます。 修復操作を開始するには、アラートに関連付けられているポリシーを選択して、[ **ポリシーの詳細** ] ページを起動します。 [ **ポリシーの詳細** ] ページでは、 **概要** ページでアクティビティの概要を確認し、[ **保留中** ] ページで通知メッセージを確認して操作することができます。または、 **解決** されたページでクローズされた通知の履歴を確認できます。
- **レポート** **: コミュニケーションコンプライアンスレポートに移動** して、  >  **Reports** コミュニケーションコンプライアンスレポートウィジェットを表示します。 各ウィジェットは、通信コンプライアンスアクティビティおよび状態の概要を提供します。これには、ポリシーの一致と修復アクションに関する深い洞察へのアクセスが含まれます。

### <a name="using-filters"></a>フィルターの使用

次に、メッセージを並べ替えて、簡単に通知を調べられるようにしてください。 [ **ポリシーの詳細** ] ページでは、複数のメッセージフィールドに対して複数レベルのフィルターがサポートされています。これにより、ポリシーが一致するメッセージをすばやく調査して確認するのに役立ちます。 フィルター処理は、構成された各ポリシーの保留中アイテムと解決済みアイテムに利用できます。 ポリシーのフィルタークエリの構成や、特定のポリシーで使用するカスタムフィルタークエリおよびカスタムフィルタークエリの構成または保存も可能です。 フィルター用のフィールドを構成すると、特定のフィルター値に対して構成可能な警告メッセージキューの上部に、フィルターフィールドが表示されます。

フィルターとフィールドの詳細の一覧については、「機能リファレンス」の「 [filters](communication-compliance-feature-reference.md#filters) 」を参照してください。

#### <a name="to-configure-a-filter"></a>フィルターを構成するには

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. Microsoft 365 コンプライアンスセンターで、[通信の **コンプライアンス**] に移動します。

3. [ **ポリシー** ] タブを選択し、調査対象のポリシーを選択して、ダブルクリックして [ **ポリシー** ] ページを開きます。

4. [ **ポリシー** ] ページで、[ **保留中** ] または [ **解決済み** ] タブのいずれかを選択して、フィルター処理するアイテムを表示します。

5. [ **フィルター** ] コントロールを選択して、[ **フィルター** の詳細] ページを開きます。

6. これらの通知のフィルターを有効にするには、1つ以上のチェックボックスをオンにします。 *日付*、*送信者*、*件名/タイトル*、*分類子* など、さまざまなフィルタから選択できます。

7. 選択したフィルターを既定のフィルターとして保存する場合は、[ **既定値として保存**] を選択します。 このフィルターを保存済みのフィルターとして使用する場合は、[ **完了**] を選択します。

8. 選択したフィルターをフィルタークエリとして保存する場合は、少なくとも1つのフィルター値を構成した後で、[クエリコントロールを **保存** する] を選択します。 フィルタークエリの名前を入力し、[ **保存**] を選択します。 このフィルターは、このポリシーに対してのみ使用でき、[**フィルター** の詳細] ページの [**保存されたフィルタークエリ**] セクションに一覧表示されます。

    ![コミュニケーションコンプライアンスフィルターの詳細コントロール](../media/communication-compliance-filter-detail-controls.png)

### <a name="using-near-and-exact-duplicate-analysis"></a>準重複分析と完全重複分析の使用

通信コンプライアンスポリシーでは、追加の構成手順を使用せずに、メッセージを自動的にスキャンし、準重複または完全重複にグループ化します。 このビューでは、類似したメッセージを1つずつまたはグループとして簡単に操作できるため、レビューアーのメッセージ調査の負担を減らすことができます。 重複が検出されると、修復アクション ツールバーに **準重複** および/または **完全重複** コントロールが表示されます。  このビューは、near または exact の重複が見つからない場合は使用できません。

#### <a name="to-remediate-duplicates"></a>重複を修復するには

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. Microsoft 365 コンプライアンスセンターで、[通信の **コンプライアンス**] に移動します。

3. [ **ポリシー** ] タブを選択し、調査対象のポリシーを選択して、ダブルクリックして [ **ポリシー** ] ページを開きます。

4. [ **ポリシー** ] ページで、[ **保留中** ] または [ **解決済み** ] タブのいずれかを選択して、重複するメッセージを表示します。

5. [重複した場合 **] または** [ **完全** に重複した場合] コントロールを選択し、[重複の詳細] ページを開きます。

6. これらのメッセージの1つ以上のメッセージを修復アクションコントロールに選択します。

7. [ **解決**、 **通知**、 **エスカレート**、または **ダウンロード** ] を選択して、選択した重複するメッセージに既定のフィルターとしてアクションを適用します。

8. メッセージの修復アクションを完了したら、[ **閉じる** ] を選択します。

    ![コミュニケーションコンプライアンスの正確な複製コントロール](../media/communication-compliance-duplicates-controls.png)

## <a name="remediate-alerts"></a>アラートを修復する

警告または構成したフィルター処理を開始する場所に関係なく、次の手順では、通知の修復を実行します。 [ **ポリシー** または **警告** のページで、次のワークフローを使用して通知の修復を開始します。

### <a name="step-1-examine-the-message-basics"></a>手順 1: メッセージの基本を調べる

 場合によっては、メッセージがすぐに修復できることがソースまたは件名からわかることがあります。 メッセージが誤っているかポリシーに一致しない可能性があるため、誤検知として解決する必要があります。 **誤検知** コントロールを選択して、直ちに通知を解決して保留中通知キューから通知を削除します。 ソースまたは送信者の情報から、このような状況でのメッセージのルーティング方法や処理方法が既にわかる場合があります。 **タグ** を使用するか **エスカレート** コントロールの使用を検討して、該当するメッセージにタグを割り当てか、指定した校閲者にメッセージを送信します。

![コミュニケーションコンプライアンスの修復コントロール](../media/communication-compliance-remediation-controls.png)

### <a name="step-2-examine-the-message-details"></a>手順 2: メッセージの詳細を確認する

メッセージの基礎を確認したら、メッセージを開いて詳細を確認し、さらに修復処理を決定します。 メッセージを選択して、完全なメッセージヘッダーと本文情報を表示します。 正しい修正対策を決定するのに役立つさまざまなビューが利用できます。

- **ソースビュー**: このビューは、ウェブベースのメッセージングプラットフォームのほとんどで一般的に見られる標準的なメッセージビューです。 ヘッダー情報は標準スタイルで書式設定され、メッセージ本文は埋め込まれたグラフィックファイルとワードラップテキストをサポートします。
- **テキストビュー**: テキストビューには、メッセージの行番号付きのテキストのみのビューが表示され、関連付けられた通信コンプライアンスポリシーに一致する用語について、メッセージおよび添付ファイルにキーワードが強調表示されます。 キーワードの強調表示を使用すると、長いメッセージや添付ファイルを目的の分野ですばやくスキャンするのに役立ちます。 場合によっては、強調表示されたテキストは、ポリシー条件に一致するメッセージの添付ファイルにのみ存在することがあります。 埋め込みファイルは表示されず、行番号は、複数の校閲者間で関連する詳細情報を参照するのに役立ちます。
- **ビューに注釈を付ける**: このビューでは、メッセージのビューに保存されているメッセージに、レビュー担当者が直接注釈を追加することができます。
- **ユーザー履歴**: ユーザー履歴ビューには、メッセージを送信するユーザーへの通信コンプライアンスポリシーにより生成された他のすべての警告が表示されます。
- **メッセージ詳細ビュー**: メッセージメタデータおよび構成情報の詳細ビュー。
- **検出されたパターンの通知 (プレビュー)**: 時間の経過とともに嫌がらせや、さまざまな作業が行われ、ユーザーによって同じ動作が繰り返し出現するインスタンスが含まれます。 検出された *パターン* の通知は、アラートの詳細に表示され、アラートに注意を促します。 パターンの検出はポリシーごとに行われ、少なくとも2つのメッセージが送信者から同じ受信者に送信された場合の過去30日間の動作を評価します。 調査担当者とレビューアーは、この通知を使用して、必要に応じてアラートを評価する反復動作を識別できます。

    ![コミュニケーションコンプライアンスメッセージビューコントロール](../media/communication-compliance-message-views.png)

### <a name="step-3-decide-on-a-remediation-action"></a>手順 3: 修復アクションを決定する

通知のメッセージの詳細を確認したので、いくつかの修復アクションを選択できます。

- **解決策**: [ **解決** ] コントロールを選択すると、 **保留中の通知** キューからメッセージがすぐに削除され、そのメッセージに対して他の操作を実行することはできません。 [ **解決** 方法] を選択することで、通知は基本的には分類されずに閉じられるので、さらにアクションを再開することはできません。 解決されたすべてのメッセージは、[ **解決済み** ] タブに表示されます。
- **誤** 検知: メッセージレビューワークフローの任意の時点で、メッセージを誤検知としていつでも解決できます。 誤検知は、通知が操作不可能であったこと、または警告が誤って通知プロセスによって生成されたことを意味します。 メッセージを再度開くことはできず、すべての偽の正のメッセージが [ **解決済み** ] タブに表示されます。
- **電力の自動処理 (プレビュー)**: 電力の自動化フローを使用して、通知メッセージのプロセスタスクを自動化します。 既定では、ユーザーがメッセージ通知を持つユーザーの通知プロセスを自動化するために使用できる *通信コンプライアンスアラート* フローテンプレートがある場合、通信コンプライアンスには Notify manager が含まれます。 通信のコンプライアンスでの Power 自動フローの作成および管理の詳細については、「 [コミュニケーションコンプライアンス機能リファレンス](communication-compliance-feature-reference.md#power-automate-flows-preview) 」を参照してください。
- [**タグ**]: 組織のポリシーおよび標準に関連するメッセージを、*準拠* しているか、準拠してい *ない* か、または *疑わしい* としてタグ付けします。 タグの追加、およびコメントのタグ付けは、エスカレーションに関するポリシーの通知や、他の内部レビュープロセスの一部としてのフィルター処理に役立てることができます。 タグ付けが完了したら、メッセージを解決して、保留中のレビューキューから移動することもできます。
- **通知**: 通知コントロールを使用し **て、カスタム** 通知テンプレートを通知に割り当て、ユーザーに警告通知を送信できます。 [ **通信コンプライアンスの設定** ] 領域で構成されている適切な通知テンプレートを選択し、[ **送信** ] を選択して、メッセージを送信したユーザーに通知を送信し、問題を解決します。
- **エスカレート**: **エスカレート** コントロールを使用して、組織内の他の誰がメッセージを確認する必要があるかを選択できます。 コミュニケーションコンプライアンスポリシーに構成されたレビュー担当者の一覧から、メッセージ通知の追加のレビューを求める電子メール通知を送信することを選択します。 指定されたレビュー担当者は、電子メール通知のリンクを使用して、確認のためにエスカレーションされたアイテムに直接アクセスできます。
- **調査のためのエスカレーション**: **調査管理のためにエスカレート** を使用すると、単一または複数のメッセージに対して新しい [高度な電子情報開示ケース](overview-ediscovery-20.md) を作成できます。 新しいケースには名前とメモを指定し、ポリシーに一致するメッセージを送信したユーザーは、保管担当者ケースとして自動的に割り当てられます。 ケースを管理するために追加のアクセス許可は必要ありません。 ケースを作成しても、メッセージの新しいタグは解決または作成されません。 修復プロセス中に高度な電子情報開示ケースを作成する場合は、合計100メッセージを選択できます。 通信コンプライアンスによって監視されるすべての通信チャネル内のメッセージがサポートされています。 たとえば、ユーザーに対して新しい高度な電子情報開示ケースを開くときに、Microsoft Teams チャット、25 Exchange Online 電子メールメッセージ、および 25 Yammer メッセージを50選択することができます。
- **分類の向上 (プレビュー)**: 分類子の種類の一致から作成されたアラートは、組織内の誤検知を最小限に抑えるためにフィードバックを必要とする場合があります。 向上した **分類** 管理を使用して、通信コンプライアンスの分類が有効かどうかについてのフィードバックを提供するか、またはこの種類の一致に対して他の trainable 分類子を提案します。 分類子が *一致* しているかどうか、または一致して *いない* ことを確認するか、または今後、この種類の通知アクティビティに関連付ける他の trainable 分類子を提案することができます。

    1. 通知リストからメッセージを選択します。
    2. 省略記号を選択して、[ **分類の強化**] を選択します。
    3. [ **詳細な分類子] フィードバック** ウィンドウで、アイテムが真陽性の場合は [ **一致**] を選択します。  アイテムが誤検知として誤ってカテゴリに含まれていた場合は、[ **一致しない**] を選択します。
    4. アイテムにより適した別の分類子がある場合は、[ **他の trainable 分類子の提案** ] リストからその分類子を選択します。 このフィードバックは、他の分類子をトリガーしてアイテムを評価します。

    > [!TIP]
    > 複数のアイテムを選択して、コマンドバーに [ **詳細なフィードバックを提供** する] を選択することにより、複数のアイテムに対してフィードバックを同時に提供することができます。

    5. [**フィードバックの送信**] を選択して、一致する分類では **なく****一致** の評価を送信し、他の trainable 分類子を提案します。 フィードバックの30インスタンスを分類子に提供した場合、その結果は自動的に retrains れます。 再トレーニングは、完了するのに1-4 時間かかる場合があります。 分類子は、1日に2回だけ retrained することができます。

    > [!IMPORTANT]
    > この情報は、テナント内の分類子に送られるので、 **Microsoft には戻りません**。

    コミュニケーションへの準拠のための再トレーニング分類子の詳細については、「通信のコンプライアンス」の記事の「 [分類子を再トレーニングする方法](classifier-how-to-retrain-comms-compliance.md) 」を参照してください。

    ![通信のコンプライアンス向上の分類](../media/communication-compliance-improve-classifier.png)

- **Teams でのメッセージの削除**: **teams** でのメッセージの削除コントロールを使用して、Microsoft Teams チャネルおよび1:1 およびグループチャットからの通知で識別された不適切なメッセージやコンテンツをブロックすることができます。 削除されたメッセージとコンテンツは、ブロックされていることと、その削除に適用されるポリシーを表示するポリシーヒントに置き換えられます。 受信者は、ポリシーヒントにリンクを表示して、適用可能なポリシーとレビュープロセスについて詳しく調べます。 送信者は、ブロックされたメッセージとコンテンツのポリシーヒントを受け取りますが、ブロックされたメッセージの詳細と、削除に関するコンテキストの内容を確認できます。

    ![Microsoft Teams からメッセージを削除する](../media/communication-compliance-remove-teams-message.png)

### <a name="step-4-determine-if-message-details-should-be-archived-outside-of-communication-compliance"></a>手順 4: 通信のコンプライアンスの外部でメッセージの詳細をアーカイブする必要があるかどうかを判断する

メッセージを別のストレージソリューションにアーカイブする必要がある場合は、メッセージの詳細をエクスポートまたはダウンロードできます。 **ダウンロード** コントロールを選択すると、自動的に選択したメッセージを Microsoft 365 の外部のストレージに保存できる ZIP ファイルに追加します。
