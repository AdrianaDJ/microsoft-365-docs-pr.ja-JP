---
title: Microsoft 365 コンプライアンスの新機能
f1.keywords:
- NOCSH
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: コンプライアンスセンターに新しい新しいソリューションを追加したり、フィードバックに基づいて既存の機能を更新したり、最新のドキュメントを展開したりすることができるかどうかにかかわらず、Microsoft 365 は、変更されたコンプライアンスの状況を常に把握するのに役立つ情報を用意しています。 今月の内容を確認してください。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d4583e5216a369801c48a47b488a35fc4e62b37
ms.sourcegitcommit: 95b85a1fdf43e3f0839483fa22e279262703f15f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2020
ms.locfileid: "49407341"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 コンプライアンスの新機能

Microsoft [365 コンプライアンスセンター](microsoft-365-compliance-center.md)に新しいソリューションを追加するか、フィードバックに基づいて既存の機能を更新するか、または最新のドキュメントをロールアウトするかどうかにかかわらず、microsoft 365 は常に変化するコンプライアンスの状況に対応しています。 Microsoft 365 コンプライアンスの新機能については、次をご覧ください。 

> [!NOTE]
> 一部のコンプライアンス機能は、お客様のさまざまなスピードでロールアウトされます。 機能がまだ表示されていない場合は、 [対象のリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)に追加してみてください。


> [!TIP]
> 他の管理センターでは何が起こっているのでしょうか。 次の記事をご覧ください。<br>[Microsoft 365 管理センターの新機能](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 管理センターの新機能](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender の新機能](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
また、 [microsoft 365 ロードマップ](https://www.microsoft.com/en-us/microsoft-365/roadmap) を参照して、起動された、展開中の、開発中である、キャンセルされた、または既にリリースされた microsoft 365 の機能について説明します。

## <a name="october-2020"></a>2020 年 10 月

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[CJK 言語サポート](ediscovery-cjk-support.md)。 高度な電子情報開示では、一括言語 (簡体字中国語、繁体字中国語、日本語、韓国語を含む) という2バイト文字セット言語をサポートするようになりました。 これらは、いくつかの高度なレビューセットシナリオで使用できます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- [ラベルの範囲](sensitivity-labels.md#label-scopes)。 機密ラベルの作成時に、ラベルの範囲を定義するための新しいオプションが表示されます。 このオプションを使用すると、ファイルと電子メール、コンテナー (SharePoint サイトやチームなど)、またはその両方に対して、ラベルを構成できます。
- [動的コンテンツマーキング](sensitivity-labels-office-apps.md#dynamic-markings-with-variables)。 機密ラベルのコンテンツマーキングを構成する場合は、 `${Item.Label}` `${Item.Location}` ヘッダー、フッター、またはウォーターマークのテキスト文字列などの動的な変数を使用できるようになりました。

## <a name="september-2020"></a>2020 年 9 月

### <a name="spotlight-compliance-manager"></a>スポットライト: コンプライアンスマネージャー

今年 Ignite に発表されたコンプライアンススコアは、 [コンプライアンスマネージャー](compliance-manager.md)として再ブランディングされています。 このリリースでは、Service Trust Portal のコンプライアンスマネージャーの前のホームから移行を完了し、Microsoft 365 コンプライアンスセンターでエンドツーエンドのコンプライアンス管理ソリューションを導入しました。

コンプライアンスマネージャーが組織によるコンプライアンスの管理を簡単にする方法については、以下のビデオを参照してください。
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>高度な監査

- 監査ログの新しい10年間の保持は、長期間の調査をサポートし、規制、法律、および内部の義務に対応するのに役に立ちます。
- [3 つ](advanced-audit.md#access-to-crucial-events-for-investigations)の新しい重要なイベント。 次の新しいイベントを使用すると、潜在的な違反を調査し、危害の範囲 (Send、SearchQueryInitiatedExchange、および SearchQueryInitiatedSharePoint) を判断するのに役立ちます。

### <a name="communication-compliance"></a>通信コンプライアンス

- [役割グループが更新されました](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)。 コミュニケーションコンプライアンス役割グループが、insider リスク管理ソリューションで利用可能な役割グループ構造と一致するようになりました。
- [レポートダッシュボード](communication-compliance-feature-reference.md#reports-preview)。 すべての通信コンプライアンスレポートを表示するための一元的な場所。 レポートウィジェットは、通信コンプライアンスアクティビティの状態の全体的な評価に最も一般的に必要な洞察の概要を提供します。
- [パワー自動化フロー](communication-compliance-feature-reference.md#power-automate-flows-preview) 通知とユーザーのタスクを自動化するフローを設定し、ユーザーが通知をトリガーしたときに管理者に通知します。
- ["分類の改善" 修復アクション](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)。 Trainable 分類子に一致するアイテムが含まれていると、組織内の誤検知を最小限に抑えるためにフィードバックによる恩恵を受けることができます。 [ **分類の向上** ] オプションを使用すると、検出されたアイテムが関連する通信コンプライアンスポリシーで構成された分類子と一致するかどうかをフィードバックできます。 その他の分類子を提案して、そのアイテムに関連付けて将来の通知の一致精度を向上させることもできます。

### <a name="data-connectors"></a>データコネクタ

- [新しいサードパーティのデータコネクタ](archiving-third-party-data.md#third-party-data-connectors)。 Globanet から14個のコネクタを含む新しいデータコネクタが25個、Telemessage から8個。
- [物理バッジコネクタ](import-physical-badging-data.md)。 社員の生の物理アクセスイベントや、組織のバッジ生成された物理的なアクセスに関する警告など、物理的なバッジのデータをインポートします。 例には、建物、サーバールーム、またはデータセンターへのエントリが含まれます。 物理 badworkflowdata は、組織内の悪意のあるアクティビティやデータの盗難から組織を保護するために、insider リスク管理ソリューションで使用できます。

### <a name="insider-risk-management"></a>インサイダー リスクの管理

- [Microsoft Teams の統合](insider-risk-management-settings.md#microsoft-teams-preview)。 チームの統合が insider のリスク設定でオンになっている場合は、個々のケースに関連するデータを安全に共有および保存するなどのタスクに関して、他の関係者と連携して共同作業を行うことができます。
- [パワー自動化フロー](insider-risk-management-settings.md#power-automate-flows-preview) ユーザー、警告、およびケースの情報を取得して関係者や他のアプリと共有したり、ケースメモへの投稿などの操作を自動化したりするなど、ケースやユーザーの重要なタスクを自動化するためのフローを設定します。
- [アクティビティ エクスプローラー](insider-risk-management-alerts.md#activity-explorer-preview)。 通知を確認するときに利用可能アクティビティエクスプローラーには、各アラートにドリルダウンするための包括的な分析ツールが用意されています。 検出された問題のあるアクティビティのタイムラインをすばやく確認し、アラートに関連するすべてのリスクアクティビティを特定してフィルター処理します。

### <a name="retention-policies-and-retention-labels"></a>アイテム保持ポリシーと保持ラベル

- [Yammer のサポート](retention-policies-yammer.md)。 アイテム保持ポリシーを使用して、Yammer コミュニティのメッセージとプライベートメッセージを保持および削除できるようになりました。
- [Teams 会議のレコーディングにラベルを適用](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings)します。 自動ラベル付けポリシーを作成するときは、キーワードクエリエディターを使用して、ユーザーの OneDrive アカウントまたは SharePoint に格納されているチームの会議のレコーディングを特定します。

### <a name="records-management"></a>レコード管理

[規制記録のサポート](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record)。 規制レコードとしてのラベルの分類により、ラベルが適用されるコンテンツに課される制限が増加し、ラベル自体に使用できる管理アクションが制限されます。 たとえば、コンテンツに適用された後は、グローバル管理者であっても、そのラベルを削除することはできません。 規制レコードに対して許可およびブロックされるアクションの詳細について[説明](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked)します。

### <a name="sensitivity-labels"></a>秘密度ラベル

[米国政府機関のお客様のサポート](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)。 機密ラベルは、GCC、GCC High、DoD の各お客様がサポートされるようになりました。これは、Azure Information Protection の統合されたラベル付きクライアントとスキャナーに対してのみサポートされます。

### <a name="trainable-classifiers"></a>トレーニング可能な分類子

新しい再トレーニング機能とフィードバック機能により、精度を向上させ、すべてのカスタム分類子と事前にトレーニングされた分類子に対して誤検知を最小限に抑えることができます。 このフローでは、アイテムが特定の分類子と一致するかどうかに関するフィードバックを提供し、アイテムに関連付けられた他の分類子を提案し、分類子を再トレーニングして一致精度を向上させることができます。

この新しい機能は、次の機能に含まれています。

> [!NOTE]
> すべての機能について、少なくとも30のフィードバック応答を提供する場合は、確認できる retrained バージョンの分類子を作成します。 改善された場合は、分類子を再発行することができます。

- [トレーニング可能な分類子](classifier-learn-about.md#retraining-classifiers)。 発行された分類子の精度を向上させるために、検出されたアイテムが分類子と一致するかどうかに関するフィードバックを提供できます。
- [通信のコンプライアンス](classifier-how-to-retrain-comms-compliance.md)。 [新しい **分類** の修復] アクションを使用すると、通信コンプライアンスアラートのアイテムが、通信コンプライアンスポリシーで構成された分類子と一致するかどうかをフィードバックできます。
- [コンテンツ エクスプローラー](classifier-how-to-retrain-content-explorer.md)。 Trainable 分類子に一致する電子メールメッセージにラベルを自動的に適用するために、保持の自動ラベル付けポリシーを設定する場合は、コンテンツエクスプローラーを使用してラベル付けされたアイテムを確認し、アイテムが分類子に一致しているかどうかのフィードバックを提供することができます。

## <a name="august-2020"></a>2020 年 8 月

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>スポットライト: Insider のリスクと通信コンプライアンスの更新

今月の公開プレビューには、いくつかの新機能と強化された機能があります。

**インサイダー リスクの管理**

- 6つの新しい [ポリシーテンプレート](insider-risk-management-policies.md#policy-templates)を確認してください。
    - 優先度の高いユーザーによるデータリーク
    - 不満のあるユーザーによるデータリーク
    - 一般的なセキュリティポリシー違反
    - ユーザーを出発することによるセキュリティポリシー違反
    - 優先度が高いユーザーによるセキュリティポリシー違反
    - 不満のあるユーザーによるセキュリティポリシー違反

- [エンドポイントの Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)との統合により、新しいセキュリティ違反ポリシーテンプレートから作成されたポリシーによって検出されたアクティビティのエンドポイント通知に対して microsoft defender のインポートとフィルター処理を行うことができます。 また、エンドポイント通知のトリアージの状態に関する Microsoft Defender に基づいて、セキュリティの警告を内部のリスク管理にインポートすることを選択できる、関連する [内部リスク設定](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) もあります。

    > [!NOTE]
    > エンドポイント統合 (新しいセキュリティポリシー違反テンプレートを含む) に Microsoft Defender を利用するには、組織で構成されたエンドポイントの Microsoft Defender を所有している必要があります。 [エンドポイントの Microsoft defender の高度な機能を構成](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)することにより、microsoft defender で insider のリスク管理統合を有効にする必要もあります。
 
- [ポリシーの作成](insider-risk-management-policies.md#create-a-new-policy)時にインジケーターのしきい値をカスタマイズします。
- [重要度ユーザーグループ](insider-risk-management-settings.md#priority-user-groups-preview)を設定して、役職、機密情報へのアクセスのレベル、リスク履歴などの要因に基づいて、アクティビティの詳細な調査が必要になるように組織内のユーザーを定義します。
- Office 365 Management Activity Api を使用して、内部者のリスクの [アラートの詳細](insider-risk-management-settings.md#export-alerts-preview) を組織が管理または集約するために使用する可能性がある他のアプリケーションに、insider のリスクデータをエクスポートします。
- 新しい [ドメイン設定](insider-risk-management-settings.md#domains-preview) を使用すると、特定のドメインでのアクティビティのリスクレベルを定義して制御することができます。

**通信コンプライアンス**

- [通知内のメッセージを確認](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)するときに、Microsoft Teams チャネル、1:1、およびグループチャットで不適切なメッセージを削除できるようになりました。 削除されたメッセージとコンテンツは、機密コンテンツによって削除されたことを示すポリシーヒントに置き換えられます。
- 新しい [通信の役割](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (9 月にリリースされる新しい通信コンプライアンスの役割グループにも含まれます)。
- [プライバシー](communication-compliance-feature-reference.md#privacy-preview)と[通知のテンプレート](communication-compliance-feature-reference.md#notice-templates)の設定を含む新しい通信コンプライアンス設定の機能。
- 成人、racy、および gory の画像を検出するための新しい [分類子](communication-compliance-feature-reference.md#classifiers) 。
- [通知内のメッセージを確認](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details)するときに表示される新しい ' パターンが検出された ' 通知により、ユーザーが同じ動作を繰り返し発生させるインスタンスについて知ることができます。

### <a name="sensitivity-labels"></a>秘密度ラベル

- 米国政府テナント (GCC、GCC-H、DoD) 向けの場合、秘密度ラベルが現在サポートされているのは、Azure Information Protection の統合ラベル付けクライアントおよびスキャナーのみです。 詳細については、[Azure Information Protection Premium の米国政府機関向けのサービスの説明](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)を参照してください。
- [セキュリティ & コンプライアンスセンターの PowerShell を使用](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies)して、ラベル付けされた管理センターで表示されるすべての設定を作成して構成できるようになりました。 これは、ラベル管理センターでは使用できない設定に対して PowerShell を使用することに加えて、機密ラベルと機密ラベルポリシーの作成と保守を完全にスクリプトで実行できることを意味します。

### <a name="records-management-content-overhaul"></a>レコード管理: コンテンツの見直し

展開手順を説明し、コンテンツをレコードとしてマークし、バージョン管理を記録する新しいドキュメント:

- [レコード管理の使用を開始する](get-started-with-records-management.md)
- [保持ラベルを使用してレコードを宣言する](declare-records.md)
- [SharePoint または OneDrive に保存されているレコードを更新するためにレコードのバージョン管理を使用する](record-versioning.md)

### <a name="retention-labels--policies"></a>保持ラベル & ポリシー

保持に関連する管理者アクティビティが記録され、監査ログで確認できるようになりました。 完全なリストについては、「[アイテム保持ポリシーと保持ラベルのアクティビティ](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)」を参照してください。

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [コレクションを校閲セットに追加](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)するときに、モダン添付ファイル ("クラウド添付ファイル" とも呼ばれる) と SharePoint ドキュメントのバージョンを含めることができます。
- 新しい [直接ダウンロード](export-documents-from-review-set.md)によるエクスポートの手順。ケースの内容をダウンロードするために Azure Storage Explorer を使用する必要がなくなります。


## <a name="july-2020"></a>2020 年7 月

### <a name="spotlight-on-help-docs"></a>ヘルプドキュメントのスポットライト

組織の機密データを保護および管理するために使用されるコンプライアンスソリューションを理解するために、ソリューションがこれらの目標を達成するためにどのように連携するかについての概要を示す2つの新しいランディングページを作成しました。これにより、関連するドキュメントへのリンクを使用してさらに進むことができます。

[Microsoft の microsoft Information Protection (365)](information-protection.md)<br>
[Microsoft 365 の Microsoft 情報ガバナンス](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>高度な電子情報開示: 状況には、非 custodial データソースを追加する

保管担当者に関連付けられていないケースにデータを追加します ( [非 custodial データソース](non-custodial-data-sources.md)として知られています)。 この非 wi-fi ダイヤルデータを保持する必要がある場合は、新しい高度なインデックス作成機能を使用することができます。

### <a name="data-connectors-hr-connector-enhancements"></a>データコネクタ: HR コネクタの拡張機能

(プレビュー)新しいバージョンの [HR コネクタ](import-hr-data.md) を使用すると、ジョブレベルの変更、業績評価、およびパフォーマンス向上計画に関連するデータをインポートできます。 このデータは、いくつかの [insider リスクポリシー](insider-risk-management-policies.md) で、関連するアクティビティを検出するために使用できます。

### <a name="retention-labels-new-support-for-email"></a>保持ラベル: 新しいサポート電子メール

メッセージがラベル付けされたときにに基づいてメールの保持を開始するための [保持ラベル](retention.md#retention-labels) を作成できるようになりました。 これは、アイテムの送信日時に基づいて保持される予定表アイテムには適用されません。

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>機密ラベル: 新機能と改善点

- (プレビュー)ラベルの暗号化設定を構成する場合は、 [二重のキー暗号化](encryption-sensitivity-labels.md#double-key-encryption) を使用してラベル付きファイルや電子メールを保護するための新しいオプションを探します。
- 機密ラベルを作成または削除したり、ラベルポリシーを作成、編集、または削除するときに、変更が1時間以内にすべてのユーザー、アプリ、およびサービスに同期されるようになりました。

## <a name="june-2020"></a>2020 年 6 月

### <a name="spotlight-new-data-connectors-hit-preview"></a>スポットライト: 新しいデータコネクタのヒットプレビュー

その他のサードパーティのソースから Microsoft 365 にデータをインポートするための約束を基にして、次の2つのデータコネクタのプレビューリリースを発表することを嬉しくしています。

- [Bloomberg メッセージ](archive-bloomberg-message-data.md)。 Bloomberg メッセージコラボレーションツールから金融サービスの電子メールデータをインポートおよびアーカイブします。 メールボックスに格納されたデータは、訴訟ホールド、コンテンツ検索、インプレースアーカイブ、監査、通信コンプライアンス、および保持ポリシーなどのコンプライアンス機能においてデータにアクセスして使用することができます。
- [氷チャット](archive-icechat-data.md)。 ICE チャットコラボレーションツールから金融サービスチャットデータをインポートおよびアーカイブします。 メールボックスに格納されたデータは、訴訟ホールド、電子情報開示、アーカイブ、監査、通信コンプライアンス、およびアイテム保持ポリシーなどのコンプライアンス機能のデータにアクセスして使用することができます。

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>コンプライアンススコア & コンプライアンスマネージャー: ヒットしたままにする

6月の更新プログラムには、 [コンプライアンススコア](compliance-score.md)における新しい評価のドリルダウンビューが含まれています。 進捗管理の監視、コンプライアンススコアから直接評価を追加、削除します。

コンプライアンススコアとコンプライアンスマネージャーの更新プログラムを常に最新の状態に保つ必要がありますか。 [コンプライアンススコアのリリースノート](compliance-score-release-notes.md)にブックマークを入れ、頻繁に確認します。

## <a name="may-2020"></a>2020 年 5 月

### <a name="spotlight-data-classification-is-officially-released"></a>スポットライト: データ分類は正式にリリースされています

データ分類、別名「[データを認識する](data-classification-overview.md)」、機能 (分析、コンテンツエクスプローラー、およびアクティビティエクスプローラー) はプレビューフェーズからの段階的なものであり、すべての組織が使用できます。 強力な洞察とツールを使用すると、組織全体のコンテンツに機密情報とラベル (保持と機密情報) がどのように使用されているかを検出し、評価するのに役立ちます。 機密情報が含まれている、またはラベルが適用されているコンテンツを確認し、Microsoft 365 の場所にまたがるラベルアクティビティを調査し、カスタムの機密情報の種類を作成するなどを行います。

ビデオツアーを実行する...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Trainable 分類子: 修正と機能

Trainable 分類子の拡張機能が向上する可能性があります。

- フィードバックに基づく修正: カスタム分類子をシード処理してトレーニングする場合は、SharePoint サイトの Url とフォルダーのパスを手動で入力する必要がなくなります。 サイトとフォルダーの事前設定リストから選択できるようになりました。
- 新機能: 機密ラベルを作成し、Office アプリの自動ラベル設定を構成するときに、trainable 分類子に一致するコンテンツに対してラベルを自動的に適用 (または推奨) することができます。 [詳細情報](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>通信のコンプライアンス: Yammer のサポートはこちらから

Yammer のプライベートメッセージとパブリックコミュニティの会話は、通信コンプライアンスポリシーでサポートされています。 Yammer はオプションのチャネルであり、メッセージと添付ファイルのスキャンをサポートするためには、[ネイティブ モード](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)に設定されている必要があります。

### <a name="data-loss-prevention-new-sharing-restriction"></a>データ損失防止: 新しい共有の制限

SharePoint または OneDrive のコンテンツを保護するように DLP ポリシーを設定する場合は、[コンテンツへのアクセスを制限する] アクションを構成して、[[リンクを持つすべて](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)のユーザー] オプションを使用してコンテンツへのアクセスを許可されたユーザーをブロックすることができるようになりました。

### <a name="insider-risk-management-tailor-your-alert-volume"></a>Insider リスク管理: 通知ボリュームを調整する

Insider リスクポリシーによって検出されたユーザーアクティビティには特定のリスクスコアが割り当てられ、それによってアラートの重要度 (低、中、高) が決定されます。 既定では、Microsoft 365 は、特定の量の低、中、高重要度の警告を生成しますが、新しい [通知ボリューム設定](insider-risk-management-settings.md#alert-volume)を使用すると、必要に応じて音量を増減することができます。

### <a name="pst-import-new-region-supported"></a>PST インポート: サポートされている新しい地域

ネットワークアップロードは、アラブ首長国連邦で利用可能になりました。

### <a name="sensitivity-labels-new-privacy-option"></a>機密ラベル: 新しいプライバシーオプション

ラベルの [サイトとグループの設定](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) を構成するときに、プライバシーオプションを [なし] に設定し、 **ユーザーがサイトにアクセスできるユーザーを選択** できるようにすることができます。 これは、機密ラベルを使用してコンテナー内のコンテンツを保護するが、ユーザーが自分でプライバシー設定を構成できるようにする場合に便利です。

## <a name="april-2020"></a>2020 年 4 月

### <a name="records-management-overhauland-a-new-addition"></a>レコード管理: 見直し...新しい追加

April には、レコード管理ソリューションへのいくつかの重要な更新が含まれています。

- 「Records management」セクションは、コンプライアンスセンターで完全に使用できるようになりました。 更新されたユーザーインターフェイスと機能を利用して、ファイル計画、保持ラベル、ラベルポリシー、イベント、および処分を行います。
- 廃棄に関しては、SharePoint および OneDrive のレコードの [廃棄の証明](disposition.md#disposition-of-records) も展開しました。 これで、自動または廃棄レビューの後に、それらの場所にあるアイテムのリストが表示されるようになりました。

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>機密ラベル: 自動ラベル付けポリシーのプレビュー

自動ラベル付けポリシーを使用すると、既に保存されている SharePoint および OneDrive ドキュメントに機密ラベルを自動的に適用することができます。また、既に保存されている電子メール (「送信中」という別名) と電子メールを送信または受信します。 このラベル付けは、アプリではなくサービスによって適用されるため、アプリユーザーの用途とバージョンについて心配する必要はありません。

この機能は、機密ラベルを作成するときに、[Office アプリの自動ラベル付け] 設定に既に含まれている既存のクライアント側のラベルを拡張します。 自動ラベル付けのオプションの違いと利点については、 [「更新さ](apply-sensitivity-label-automatically.md)れた記事」を参照してください。

## <a name="march-2020"></a>2020 年 3 月

### <a name="introducing-advanced-audit"></a>高度な監査の概要

[Microsoft 365 の高度な監査](advanced-audit.md) には、組織にフォレンジックおよびコンプライアンスの調査を支援する新しい監査機能が導入されています。 重要な点としては、監査ログの長期保存、カスタム監査ログの保持ポリシー、新しい *Mailitemsaccessed* されたメールボックス監査アクション、および新しいテナントレベルの調整制限の導入によって、組織は監査データにアクセスするための完全に割り当てられた帯域幅クォータを使用できます。

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>コンプライアンススコア & コンプライアンスマネージャー: 最新の機能強化のプレビュー

このプレビューリリースの主要な更新プログラムは次のとおりです。

- テンプレートを作成および変更するための簡略化されたプロセス
- テンプレートとアクションのバージョン管理通知とコントロール
- グループ間で共通のアクションを同期する
- 言語サポートは、簡体字中国語 (簡体字)、中国語 (繁体字)、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語 (ブラジル)、ロシア語、スペイン語に拡張されました。

[コンプライアンススコア](compliance-score.md)と[コンプライアンスマネージャー](compliance-manager-overview.md)の詳細情報

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>機密ラベル: SharePoint および OneDrive での Office ファイルへのラベル付けのサポート (プレビュー)

プレビューを有効にすると、ユーザーは web 上の Office に機密ラベルを適用することができます。 これにより、リボン上の [ **秘密度** ] ボタンと、適用されたラベル名がステータスバーに表示されるようになります。 また、デスクトップアプリを使用して、SharePoint または OneDrive にファイルをラベル付けして保存すると、Microsoft 365 は、そのラベルに暗号化設定が適用されている場合にこれらのファイルのコンテンツを処理できるようになります。 このような状況では、共同編集、電子情報開示、データ損失防止、検索、およびその他のコラボレーション機能もサポートされます。

[プレビューを有効にする方法について説明します。](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020 年 2 月

### <a name="insider-risk-management-is-officially-released"></a>Insider リスク管理が正式にリリースされている

ドラムロール (ご記入ください)<br>Insider リスク管理は、次のサブスクリプションを使用する組織で使用できるようになりました。

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (有料または試用版)
- Microsoft 365 Enterprise E3 サブスクリプションと [Microsoft E5 コンプライアンスアドオン](https://go.microsoft.com/fwlink/?linkid=2120432)

プレビューリリース後に、 [新しい役割グループ](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) と [ソリューションレベルの設定](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)を含むいくつかの改善を行いました。

そのため、ソリューションを使用するときにはフィードバックを残して、改善を続けられるようにしてください。

### <a name="records-management"></a>レコード管理

この新しいソリューションにより、すべてのレコード管理機能が1つの包括的な下に表示されます。 重要な点としては、SharePoint と OneDrive のレコードバージョン管理の導入やレコードの廃棄証明が挙げられます。

![Microsoft 365 コンプライアンスセンターのレコード管理ページ](../media/mcc-records-management-page.png)

[レコード管理についての詳細情報](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>ソリューションスポットライト: Facebook および Twitter のデータコネクタ

先月 [リリース](#just-launched) されたデータコネクタは、次のコネクタをテストするためのヘルプを探しています。

- [Facebook ビジネスページ](archive-facebook-data-with-sample-connector.md) Facebook のビジネスページのデータをインポートし、Microsoft 365 にアーカイブします。 レコード管理や電子情報開示などのコンプライアンスソリューションに役立ちます。
- [Twitter](archive-twitter-data-with-sample-connector.md)。 Twitter から Microsoft 365 にデータをインポートしてアーカイブします。 レコード管理や電子情報開示などのコンプライアンスソリューションに役立ちます。

これらのコネクタを設定して検証するときには、何がうまくいったのか、何ができなかったのか、また、操作を改善するためにできることについてのフィードバックをお寄せください。

## <a name="january-2020"></a>2020 年 1 月

待機が終了しています。 Microsoft 365 コンプライアンスセンターは、Microsoft 365、Office 365、Enterprise Mobility + Security (EMS)、および Windows 10 Enterprise プランを使用しているすべてのお客様が利用できることを嬉しくお勧めいたします。 セキュリティ & コンプライアンスセンターで管理していたすべてのデータやポリシーは、コンプライアンスセンターで利用できます。そのため、前後に移動する必要はありません。

> [!TIP]
> 最近プレビューした [新しいソリューション](#new-compliance-solutions) の一部、およびセキュリティ & コンプライアンスセンターからのコンプライアンス機能が Microsoft 365 で有効になっていることを示す [ロードマップ](#updated-compliance-solutions) については、先月の「更新」を参照してください。

[https://compliance.microsoft.com](https://compliance.microsoft.com)組織全体にわたるコンプライアンスを管理するためのワンストップショップのツアーを開始するには、今すぐにブックマークを作成してください。詳細については、[この記事を参照](microsoft-365-compliance-center.md)してください。

![Microsoft 365 コンプライアンスセンターのホームページ](../media/mcc-home-ga.png)

また、今月の新規および更新されたソリューションもリリースしました。 強調表示の概要は次のとおりです。

### <a name="now-in-preview"></a>現在はプレビュー

**Insider リスク管理 (プレビュー)**

これで、insider のリスク管理ソリューションが公開プレビューであることがわかります。 簡単に言うと、insider リスク管理は、次のような情報を提供することで、組織がインテリジェントに内部のリスクを特定し、アクションを実行できるようにします。

- ユーザーのプライバシーを確保するための匿名性制御。
- 内部の脅威 (データリークなど) を識別するネイティブおよびサードパーティの指標を使用したインテリジェントポリシーテンプレート。
- IT、人事、および法務チーム全体にわたる、統合されたエンドツーエンドの調査ワークフロー。

ご感想をお聞かせください。 ソリューションを使用している間に、フィードバックをお寄せください。これにより、一般的な可用性に至るまでのニーズを満たすことができるようになります。

[Insider リスク管理の詳細情報](insider-risk-management.md)

### <a name="just-launched"></a>開始したばかり

**通信コンプライアンス**

Graduating は、プレビュー段階から完全な可用性まで、コミュニケーションコンプライアンスは新しい insider リスクソリューションセットの主要なコンポーネントです。 この堅牢なソリューションにより、組織の標準に準拠していないメッセージの検出、調査、修復処理を行うためのワークフローを使用して、コミュニケーションリスクを最小限に抑えることができます。

プレビュー中のお客様からのフィードバックはすばらしいものでした。 開始、調査、修復処理の改善など、いくつかの機能強化が行われています。

[通信のコンプライアンスに関する詳細情報](communication-compliance.md)

![Microsoft 365 コンプライアンスセンターの [通信コンプライアンス] ページで、最初のカードの案内画面が表示されている](../media/mcc-communication-compliance-page-with-fre.png)

**データコネクタ**

以前は、Office 365 セキュリティ & コンプライアンスセンターの他の「インポート」機能とのスペースを共有しています。データコネクタは、Microsoft 365 コンプライアンスセンターで独自のホームになっています。 新しい [データコネクタ] ページを使用して、組織の人事 (HR) ファイルと、さまざまなサードパーティ製プラットフォーム (Facebook、LinkedIn、Twitter、インスタント Bloomberg など) のデータを Microsoft 365 組織のメールボックスにインポートおよびアーカイブします。 インポートされると、このデータは、電子情報開示、insider リスク管理、コミュニケーションコンプライアンス、監査、アイテム保持ポリシーなどを含む、いくつかのコンプライアンスソリューションで管理できます。

[データコネクタの詳細情報](archiving-third-party-data.md)

![Microsoft 365 コンプライアンスセンターのデータコネクタページ](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>注目すべき更新プログラム

**コンプライアンススコアの新しい評価テンプレート (プレビュー)**

常に努力していくことにより、絶えず進化するコンプライアンスに役立てられるようになり、コンプライアンススコアチームは新しい一連のテンプレートを提供し、最近の規制に対する組織のコンプライアンスを評価し、より効果的な制御を実装する方法に関するガイダンスを得ることができます。 次の新しいテンプレートが表示られるようになります。

- ISO/IEC 27701:2019
- カリフォルニア州消費者プライバシー法 (CCPA)
- ブラジルの一般データ保護法 (Lei Geral de Proteção de Dados-LGPD)
- SOC 1 タイプ2および SOC 2 タイプ2

[コンプライアンススコアテンプレートの詳細情報](compliance-score.md#templates)

## <a name="november--december-2019"></a>2019年12月 &

休日に加えて、Ignite でデモされていたすべての高度なコンプライアンスソリューションのロールアウトを開始しました。 ほとんどはプレビュー状態であるため、それをテストして、コンプライアンスセンターの右下でフィードバックカードを開いて、ご意見をお聞かせください。

![feedback](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>新しい近隣を理解する

新しい Microsoft 365 コンプライアンスセンターには、新しいソリューションに加えて、Office 365 セキュリティ & コンプライアンスセンターで熟知しているコンプライアンス機能が含まれています。 詳細については、さらに詳しく説明します。

#### <a name="new-compliance-solutions"></a>新しいコンプライアンスソリューション

*ソリューション* について疑問があるかもしれません。 クラウドがビジネスを遂行する方法によって革命になるにつれて、データの盗用や不正行為の新たな方法や、必要とされる新しい規制についても、このドアを開くことができます。 コンプライアンスソリューションは、これらの進化したコンプライアンス要件を管理するのに役立つ統合された機能の集合です。 ソリューションの機能には、ポリシー、警告、レポートなどの組み合わせが含まれることがあります。

ここでは、次のような新しいソリューションについて概要を説明します。 近日中に他のユーザーが閲覧できるようにしておきます。

> [!NOTE]
> これらのソリューションは、Microsoft 365 コンプライアンスセンターのみにあります。 Office 365 セキュリティ & コンプライアンスセンターで管理することはできません。
<br/>

|**新しいソリューション**|**説明**|**詳細情報**|
|:-----|:-----|:-----|
|Microsoft コンプライアンススコア (プレビュー) <br/>|コンプライアンス [マネージャー](compliance-manager-overview.md)を基にしたコンプライアンススコアは、よりシンプルでわかりやすい設計を備えたスタンドアロンの機能です。これにより、組織の法令遵守状況を理解し、改善することができます。 データ保護および規制標準に関するリスクを軽減するために、進行状況を測定するリスクベースのスコアを計算します。 <br/>|[Microsoft コンプライアンススコアの概要 (プレビュー)](compliance-score.md)|
|ソリューションカタログ (プレビュー) <br/>|ソリューションカタログは、コンプライアンスおよびリスク管理ソリューションの発見、学習、迅速な開始を行うためのワンストップショップです。 カタログは3つのコンプライアンスカテゴリに編成されており、それぞれにカテゴリを構成するソリューションに関する詳細が含まれています。 カテゴリには、情報保護 & ガバナンス、Insider リスク管理、検出 & 応答が含まれます。 <br/>|[ソリューションカタログの概要 (プレビュー)](microsoft-365-solution-catalog.md)|
|通信のコンプライアンス (プレビュー) <br/>|コミュニケーションへのコンプライアンスは、組織内の不適切なメッセージに対する修復アクションを検出、取得、および実行できるようにすることで、コミュニケーションリスクを最小限にするために役立つ、新しい insider リスク管理カテゴリに含まれています。 このソリューションでは、インテリジェントテンプレート、柔軟な修復ワークフロー、実践的な洞察など、いくつかの新しい拡張機能を導入することで、Office 365 の監督ポリシーの機能が拡張されています。 <br/>|[Microsoft 365 の通信コンプライアンス (プレビュー)](communication-compliance.md)|
|データ分類 (プレビュー) <br/>|新しいデータ分類ページには、組織全体のコンテンツに機密情報とラベル (保持と機密情報) がどのように使用されているかを検出して評価するのに役立つ、強力な洞察とツールが含まれています。 機密情報が含まれている、またはラベルが適用されているコンテンツを確認し、Microsoft 365 の場所にまたがるラベルアクティビティを調査し、カスタムの機密情報の種類を作成するなど、さまざまな内容を確認します。<br/>|[データ分類の概要 (プレビュー)](data-classification-overview.md)|
|トレーニング可能な分類子 (プレビュー) <br/>|この強力な新しいツールは、機械学習エンジンを使用して、規制文書や従業員契約書など、組織内のコンテンツのカテゴリを特定するのに役立ちます。 作成した分類子は、いくつかのコンプライアンスソリューションで使用して、関連するコンテンツを検出し、それを分類し、保護し、その他の情報を保持することができます。<br/>|[トレーニング可能な分類子の詳細 (プレビュー)](classifier-learn-about.md)|

#### <a name="updated-compliance-solutions"></a>コンプライアンスソリューションの更新

コンプライアンスのニーズに応じて Office 365 セキュリティ & コンプライアンスセンターを使用している場合は、一部の機能が新しい Microsoft 365 コンプライアンスセンターで有効になっていることを不思議に思うかもしれません。 新しい自宅を見つけるのに役立つクイックロードマップを次に示します。

> [!NOTE]
> 一部の機能は依然として Office 365 セキュリティ & コンプライアンスセンターでのみ利用できます。 しかし、Microsoft 365 コンプライアンスセンターでは、これらをプレビューするのは困難なので、更新プログラムを常にチューニングするように努力しています。 
<br/>

|**機能**|**Office 365 セキュリティ/コンプライアンス センター**|**Microsoft 365 コンプライアンス センター**|**詳細情報**|
|:-----|:-----|:-----|:-----|
|Advanced eDiscovery|電子情報開示 > の高度な電子情報開示 <br/> https://protection.office.com/advancedediscoverycases |電子情報開示 > の詳細 <br/> https://compliance.microsoft.com/advancedediscovery | [Microsoft 365 の高度な電子情報開示ソリューションの概要](overview-ediscovery-20.md) |
|ポリシーを通知する|通知 > 警告ポリシー <br/> https://protection.office.com/alertpolicies |現時点では、アラートポリシーは Office 365 セキュリティ & コンプライアンスセンターでのみ管理されます。 |[セキュリティ/コンプライアンス センターのアラート ポリシー](alert-policies.md) |
|アラート|通知 > 表示する通知 <br/> https://protection.office.com/viewalerts |アラート <br/> https://compliance.microsoft.com/compliancealerts |[通知の表示](alert-policies.md#viewing-alerts)|
|アーカイブ|情報ガバナンス > アーカイブ <br/> https://protection.office.com/archiving |情報ガバナンス > [アーカイブ] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[アーカイブ メールボックスの有効化](enable-archive-mailboxes.md)|
|監査ログ検索|検索 > 監査ログの検索 <br/> https://protection.office.com/unifiedauditlog |監査 <br/> https://compliance.microsoft.com/auditlogsearch | [セキュリティ/コンプライアンス センターで監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)|
|コンテンツ検索|検索 > コンテンツ検索 <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | コンテンツ検索 <br/> https://compliance.microsoft.com/contentsearch |[Office 365 のコンテンツを検索する](search-for-content.md) |
|データコネクタ|情報ガバナンス > サードパーティのデータをアーカイブする <br/> https://protection.office.com/nativeconnector | データコネクタ <br/> https://compliance.microsoft.com/connectorlanding |[サード パーティのデータをアーカイブする](archiving-third-party-data.md)|
|データ損失防止|データ損失防止 <br/> https://protection.office.com/datalossprevention |データ損失防止 <br/> https://compliance.microsoft.com/datalossprevention |[データ損失防止の概要](data-loss-prevention-policies.md)|
|データ主体要求 |データのプライバシー > データ主体要求 <br/> https://protection.office.com/dsrcases |データ主体要求 <br/> https://compliance.microsoft.com/datasubjectrequest |[DSR ケースツールを使用して GDPR データ主体要求を管理する](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|電子情報開示|電子情報開示 > 電子情報開示 <br/> https://protection.office.com/ediscoveryv1 |電子情報開示 > コア <br/> https://compliance.microsoft.com/classicediscovery |[eDiscovery ケースを管理する](ediscovery-cases.md) |
|イベント|レコード管理 > イベント <br/> https://protection.office.com/events |レコード管理 > [イベント] タブ <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[イベントの発生時に保持を開始する](event-driven-retention.md)|
|ファイル計画|レコード管理 > ファイル計画 <br/> https://protection.office.com/fileplan |レコード管理 > ファイル計画] タブ <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[ファイルプランを使用して保持ラベルを管理する](file-plan-manager.md)|
|PST ファイルのインポート|情報ガバナンス > PST ファイルのインポート <br/> https://protection.office.com/importV2 |情報ガバナンス > インポート] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[組織の PST ファイルのインポートの概要](importing-pst-files-to-office-365.md)|
|ラベルアクティビティエクスプローラー|情報ガバナンス > ラベルアクティビティエクスプローラー <br/> https://protection.office.com/labelexplorer |データ分類 > アクティビティエクスプローラータブ <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[ラベル付きコンテンツのアクティビティを表示する (プレビュー)](data-classification-activity-explorer.md)|
|保持ラベルとラベルポリシー |[ラベル] タブと [ラベルポリシー] タブ > の > 保持ラベルの分類 <br/> https://protection.office.com/retentionlabels |情報ガバナンス > ラベルとラベルポリシー] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | [保持ラベルの概要](retention.md)|
|アイテム保持ポリシー|情報ガバナンス > の保持 <br/> https://protection.office.com/retention |情報ガバナンス > [保持] タブ <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[アイテム保持ポリシーと保持ラベルの詳細](retention.md)|
|機密情報の種類|機密情報の種類 > 分類 <br/> https://protection.office.com/sensitivetypes |データ分類 > 機密情報の種類] タブ <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)|
|機密ラベルとラベルポリシー|[ラベル] タブと [ラベルポリシー] タブ > 機密ラベルの分類 > <br/> https://protection.office.com/sensitivity |情報保護 > ラベルとラベルポリシー] タブ <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[秘密度ラベルの詳細](sensitivity-labels.md) |
|サービス アシュアランス|サービス アシュアランス <br/> https://protection.office.com/serviceassurance/dashboard |現時点では、サービス保証のリソースには、Office 365 セキュリティ & コンプライアンスセンターのみがアクセスできます。 |[セキュリティ/コンプライアンス センターのサービス アシュアランス](service-assurance.md)|
|監督|監督 <br/> https://protection.office.com/supervisoryreviewv2 |通信コンプライアンス <br/> https://compliance.microsoft.com/supervisoryreview |[Microsoft 365 の通信コンプライアンス (プレビュー)](communication-compliance.md) |
