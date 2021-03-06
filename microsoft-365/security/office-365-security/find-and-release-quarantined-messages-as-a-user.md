---
title: ユーザーとして検疫済みメッセージを検索して解放する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: ユーザーは、ユーザーに配信されるべきであった検疫済みメッセージを Exchange Online Protection (EOP) で表示して管理する方法を学ぶことができます。
ms.openlocfilehash: 48c727c442ee6f861499f1a72c687f7b3457c594
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130853"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>EOP のユーザーとして検疫済みメッセージを検索して解放する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online のメールボックスを使用している Microsoft 365 組織または Exchange Online のメールボックスを使用していないスタンドアロンの Exchange Online Protection (EOP) 組織では、危険な可能性があるメッセージまたは不要なメッセージは検疫済みメッセージとして保留されます。 詳細については、「[EOP での検疫](quarantine-email-messages.md)」を参照してください。

ユーザーは、自分が受信者で、スパムまたはバルク メールとして検疫された検疫済みメッセージを表示、解放、削除することができます。 2020 年 4 月以降、ユーザーは、自分が受信者である検疫済みフィッシング メッセージ (高確度フィッシング詐欺メッセージを除く) を表示または削除できます。 検疫されたメッセージをセキュリティ/コンプライアンス センターで表示および管理するか、(管理者がこの設定を構成している場合) [エンド ユーザーのスパム通知を](use-spam-notifications-to-release-and-report-quarantined-messages.md)します。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- セキュリティ/コンプライアンス センターを開くには、<https://protection.office.com> へ移動します。 検疫ページを直接開くには、<https://protection.office.com/quarantine> にアクセスします。

- 管理者は、どれ程の期間メッセージを保持してから完全に削除するかを設定できます (スパム対策ポリシー)。 検疫期間が切れたメッセージは回復できません。 詳細については、「[EOP でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

- 管理者は、スパム対策ポリシーで[ エンドユーザー スパム通知を有効にする](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)こともできます。 ユーザーは、スパム検疫メッセージをこれらの通知から直接リリースできます。 ユーザーは、フィッシング検疫メッセージ (高精度のフィッシング詐欺メッセージではありません) をこれらの通知から直接確認することができます。 詳細については、「[EOP でのエンドユーザースパム通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)」を参照してください。

- 高確度フィッシング、マルウェアとして検疫されるか、メール フロー ルール (別名: トランスポート ルール) により検疫されたメッセージは、管理者のみが管理でき、ユーザーに表示されません。 詳細については、「[EOP の管理者として検疫済みのメッセージやファイルを管理する](manage-quarantined-messages-and-files.md)」を参照してください。

- メッセージを移動して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。

## <a name="view-your-quarantined-messages"></a>検疫済みメッセージを表示する

1. セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[レビュー]** \> **[検疫]** の順に移動します。

2. 使用できる列見出しをクリックすると、結果を並べ替えることができます。 **[列の変更]** をクリックして、最大で 7 列まで表示できます。 既定値にはアスタリスク (<sup>\*</sup>) が付いています。

   - **[受信日時]**<sup>\*</sup>
   - **[送信者]**<sup>\*</sup>
   - **[件名]**<sup>\*</sup>
   - **[検疫の理由]**<sup>\*</sup>
   - **[解放済み?]**<sup>\*</sup>
   - **[ポリシーの種類]**<sup>\*</sup>
   - **[有効期限]**<sup>\*</sup>
   - **[受信者]**
   - **[メッセージ ID]**
   - **[ポリシー名]**
   - **[サイズ]**
   - **[方向]**

   完了したら、**[保存]** をクリックして、**[既定値に設定]** をクリックします。

3. 結果をフィルター処理するには、**[フィルター]** をクリックします。 使用できるフィルターは次のとおりです。

   - **[期限切れ日時]**: 検疫の期限が切れるタイミングでメッセージをフィルター処理します。
     - **[今日]**
     - **[今後 2 日間]**
     - **[今後 7 日間]**
     - **[カスタム]**: **[開始日]** と **[終了日]** を入力します。

   - **[受信日時]**: **[開始日]** と **[終了日]** を入力します。

   - **[検疫の理由]**:
     - **[バルク]**
     - **[スパム]**
     - **フィッシング**

   - **ポリシーの種類**: 次のポリシーの種類ごとに、メッセージをフィルター処理します。
     - **フィッシング対策ポリシー**
     - **ホストされているコンテンツ フィルター ポリシー** (スパム対策ポリシー)

   フィルターをクリアするには、**[クリア]** をクリックします。 フィルターのポップアップを非表示にするには、**[フィルター]** をもう一度クリックします。

4. **[結果の並べ替え]** (既定では **[メッセージ ID]** ボタン) および対応する値を使用して、特定のメッセージを検索します。 ワイルドカードはサポートされていません。 次の値に基づいて検索できます。

   - **[メッセージ ID]**: メッセージのグローバル一意識別子。 一覧でメッセージを選択すると、表示される **[詳細]** ポップアップ ウィンドウに **[メッセージ ID]** 値が表示されます。 管理者は、[メッセージ追跡](message-trace-scc.md)を使用して、メッセージとそれに対応する [メッセージ ID] 値を検索できます。

   - **[送信者のメール アドレス]**: 単一の送信者のメール アドレス。

   - **ポリシー名**: メッセージのポリシー名全体を使用します。 この検索では大文字と小文字は区別されません。

   - **[受信者のメール アドレス]**: 単一の受信者のメール アドレス。

   - **[件名]**: メッセージの件名全体を使用します。 この検索では大文字と小文字は区別されません。

   検索条件を入力したら、![[更新] ボタン](../../media/scc-quarantine-refresh.png) **[更新]** をクリックすると、結果がフィルター処理されます。

特定の検疫済みメッセージを見つけたら、そのメッセージを選択して詳細を表示し、処理を実行します (メッセージの表示、解放、ダウンロード、または削除など)。

### <a name="export-message-results"></a>メッセージ結果をエクスポートする

1. 目的のメッセージを選択し、**[結果のエクスポート]** をクリックします。

2. ブラウザー ウィンドウを開いたままにするように警告する確認メッセージで、**[はい]** をクリックします。

3. エクスポートの準備ができたら、.csv ファイルに名前を付けて、ダウンロード場所を選択できます。

### <a name="view-quarantined-message-details"></a>検疫済みメッセージの詳細を表示する

一覧でメール メッセージを選択すると、**[詳細]** ポップアップ ウィンドウにメッセージに関する次の詳細が表示されます。

- **[メッセージ ID]**: メッセージのグローバル一意識別子。

- **[送信者のアドレス]**

- **[受信日時]**: メッセージを受信した日時。

- **[件名]**

- [**検疫の理由**]: メッセージが [**迷惑メール**]、[**バルク メール**]、または [**フィッシング**] として識別されたかを表示します。

- **[受信者]**: メッセージに複数の受信者が含まれている場合は、**[メッセージのプレビュー]** か **[メッセージ ヘッダーを表示]** をクリックして受信者の完全な一覧を表示する必要があります。

- **[有効期限]**: 検疫からメッセージが自動的に完全に削除される日時。

- **[解放済み]**: メッセージが解放されたすべてのメール アドレス (ある場合)。

- **[未解放]**: メッセージがまだ解放されていないすべてのメール アドレス (ある場合)。

### <a name="take-action-on-quarantined-email"></a>検疫済みメールを処理する

メッセージを選択すると、**[詳細]** ポップアップ ウィンドウに、そのメッセージに関してどんな操作を実行するかを選択するオプションが表示されます。

- **[メッセージの解放]**: 表示されるポップアップ ウィンドウで、**[メッセージを分析のために Microsoft に報告する]** かどうかを選択します。 これは既定で有効になっており、誤って検疫されたメッセージが誤検知として Microsoft に報告されます。

  完了したら、**[メッセージの解放]** をクリックします。

- **[メッセージ ヘッダーを表示]**: このリンクをクリックすると、メッセージ ヘッダー テキストが表示されます。 ヘッダー フィールドと値を詳しく分析するには、メッセージ ヘッダー テキストをクリップボードにコピーし、**[Microsoft メッセージ ヘッダー アナライザー]** を選択して、リモート接続アナライザーに移動します (このタスクを実行するために Microsoft 365 を閉じたくない場合は、右クリックして **[新しいタブで開く]** を選択します)。 メッセージ ヘッダーを [Microsoft メッセージ ヘッダー アナライザー] セクションのページに貼り付け、**[ヘッダーを分析]** を選択します。

- **[メッセージのプレビュー]**: 表示されるポップアップ ウィンドウで、次のいずれかのオプションを選択します。
  - **[ソースを表示]**: すべてのリンクが無効になったメッセージ本文の HTML バージョンを表示します。
  - **[テキスト表示]**: プレーン テキストでメッセージ本文を表示します。

- **[メッセージをダウンロード]**: 表示されるポップアップ ウィンドウで、**[このメッセージをダウンロードするリスクを理解しています]** を選択して、メッセージのローカル コピーを .eml 形式で保存します。

- **[検疫から削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除されます。

完了したら、**[閉じる]** をクリックします。

メッセージを解放も削除もしないと、既定の検疫保持期間が経過した後に削除されます。

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>複数の検疫済みメール メッセージを処理する

一覧で複数の検疫済みメッセージを選択すると (最大 100)、**[一括処理]** ポップアップ ウィンドウが表示され、次の操作を実行できます。

- **[メッセージの解放]**: このオプションは、**[特定の受信者にメッセージを解放する]** を選択できない点以外は単一のメッセージを解放する場合と同様です。**[すべての受信者にメッセージを解放する]** か **[他のユーザーにメッセージを解放する]** のみを選択できます。

- **[メッセージの削除]**: 表示される警告で **[はい]** をクリックすると、メッセージは直ちに削除され、元の受信者には送信されません。

完了したら、**[閉じる]** をクリックします。
