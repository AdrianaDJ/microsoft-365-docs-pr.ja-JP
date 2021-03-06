---
title: 通信コンプライアンス
description: Microsoft 365 での通信コンプライアンスについて
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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: a3e51463f85e05c223bf9a88555f18f66f1f2057
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071985"
---
# <a name="communication-compliance-in-microsoft-365"></a>Microsoft 365 での通信コンプライアンス

コミュニケーションへの準拠とは、組織内で不適切なメッセージを検出、取得、および処理できるようにすることで、コミュニケーションリスクを最小限にするために役立つ、Microsoft 365 の内部内部リスクソリューションです。 定義済みおよびカスタムのポリシーを使用すると、ポリシーの一致に関する内部通信と外部通信をスキャンして、指定したレビュー担当者がそれらを調査できるようにすることができます。 レビューアーは、スキャンされた電子メール、Microsoft Teams、Yammer、または組織内のサードパーティの通信を調査し、適切なアクションを実行して組織のメッセージ標準に準拠していることを確認できます。

Microsoft 365 のコミュニケーションコンプライアンスポリシーは、コンプライアンスと、次のような内部通信および外部通信に関連する最新の課題に対処するのに役立ちます。

- スキャンする通信チャネルの種類の増加
- メッセージデータの増加量
- 法規制の適用と罰金のリスク

さらに、IT 管理者とコンプライアンス管理チームとの間での職務の切り分けが必要になることがあります。 通信コンプライアンスは、ポリシーの構成と、メッセージの調査およびレビューを分離することをサポートします。 たとえば、組織の IT グループは、通信コンプライアンスの役割のアクセス許可、グループ、ポリシー、およびレビュー担当者を設定して、メッセージの選別、レビュー、および軽減処置を行うことができます。

コミュニケーションのコンプライアンスの概要については、「microsoft の技術情報」[チャネル](https://www.youtube.com/user/OfficeGarageSeries)の「 [microsoft 365 ビデオ」の「workplace の嫌がらせを検出し、コミュニケーションに関するコンプライアンス](https://youtu.be/z33ji7a7Zho)」を参照してください。

## <a name="scenarios-for-communication-compliance"></a>情報コンプライアンスのシナリオ

コミュニケーションコンプライアンスポリシーを使用して、組織内のメッセージをいくつかの重要なコンプライアンス分野で確認することができます。

- **企業ポリシー**

    ユーザーは、ビジネス関連のすべての通信において、許容できる使用、倫理的な標準、その他の企業ポリシーに準拠している必要があります。 通信コンプライアンスポリシーによってポリシーの一致が検出され、これらの種類のインシデントを軽減するための是正措置を行うことができます。 たとえば、組織内のユーザーのコミュニケーションをスキャンして、嫌がらせや不適切または不快な言葉の使用など、人的リソースに関する潜在的な問題について調べることができます。

- **リスク管理**

    組織は、インフラストラクチャと企業ネットワークシステム全体に分散されたすべての通信を担当します。 コミュニケーションコンプライアンスポリシーを使用して法的な危険とリスクを特定して管理することにより、企業の運用に影響を与えるリスクを最小限に抑えることができます。 たとえば、組織内のメッセージをスキャンして、今後の買収、合併、利益開示、再編成、指導チームの変更など、機密プロジェクトに関する承認されていない通信を行うことができます。

- **法令遵守**

    ほとんどの組織では、通常の運用手順の一部として、何らかの種類の法令遵守標準に準拠する必要があります。 これらの規則では、多くの場合、組織にとって適切な種類の監督または監視プロセスを実装する必要があります。 金融業界の規制当局 (FINRA) ルール3110は、組織が、ユーザーのコミュニケーションや、それが関与する企業の種類をスキャンするための監視手順を実施する必要があることを示しています。 別の例としては、組織内でブローカーディーラーとの通信を確認する必要がある場合があります。これは、潜在的なマネーロンダリング、インサイダー取引、談合、または違法行為を防ぐためです。 コミュニケーションコンプライアンスポリシーを使用すると、組織は企業の通信をスキャンしてレポートするためのプロセスを提供することで、これらの要件を満たすことができます。 金融機関のサポートの詳細については、「 [US バンキングおよびキャピタルマーケット向けの重要なコンプライアンスとセキュリティに関する考慮事項](../solutions/financial-services-secure-collaboration.md)」を参照してください。

## <a name="new-enhancements"></a>新しい拡張機能

Microsoft 365 の通信コンプライアンスは、メッセージングプラットフォームにおけるコンプライアンスの問題に対処するために役立ついくつかの重要な機能を提供します。

- インテリジェントなカスタマイズ可能テンプレート
- 柔軟な修復ワークフロー
- 対応につながるインサイト

![コミュニケーションコンプライアンスのホームページ](../media/communication-compliance-home.png)

### <a name="intelligent-customizable-templates"></a>インテリジェントなカスタマイズ可能テンプレート

コミュニケーションのコンプライアンスにおけるインテリジェントにカスタマイズ可能なテンプレートを使用すると、コンピューターの学習を適用して、組織内の通信違反をインテリジェントに検出することができます。

- **カスタマイズ可能な事前構成テンプレート** : 新しいポリシーテンプレートは、最も一般的なコミュニケーションのリスクに対処するのに役立ちます。 事前に定義された防御対策と不快感を持つ言葉、機密情報、および規制コンプライアンステンプレートを使用して、初期ポリシーの作成とフォローによる更新がより迅速になりました。
- **新しい machine learning サポート** : 組み込みの脅威、嫌がらせ、冒涜、およびイメージ [分類子](classifier-get-started-with.md) は、スキャンされたメッセージの誤検知を減らすために役立ち、調査および修復プロセス中にレビュー担当者の時間を節約できます。
- 改良された **条件ビルダー** : ポリシーの構成をポリシーウィザードで統合された1つの環境に簡素化することで、ポリシーの条件の適用方法についての混乱を減らすことができました。

### <a name="flexible-remediation-workflows"></a>柔軟な修復ワークフロー

組み込みの修復ワークフローを使用すると、組織内のポリシーが一致するメッセージをすばやく識別し、アクションを実行することができます。 次の新機能により、調査および修復アクティビティの効率が向上します。

- **柔軟な修復のワークフロー** : 新しい修復ワークフローは、メッセージを他のレビュー担当者にエスカレートし、ポリシーが一致するユーザーに電子メール通知を送信するための新しいオプションを含む、ポリシーの一致に対するアクションを迅速に実行するのに便利です。
- **会話スレッド** : 元のメッセージとすべての関連付けられた返信メッセージによってメッセージが視覚的にグループ化されるようになったため、調査および修復アクション中にコンテキストが改善されました。
- **キーワードの強調表示** : メッセージテキストの表示において、ポリシーの条件に一致する用語が強調表示されることで、レビュー担当者がポリシーの通知を素早く特定し修復するのに役立ちます。
- **完全に一致した重複データの検出** : 通信コンプライアンスポリシーの正確な用語をスキャンするだけでなく、重複を検出するためのグループに類似した用語とメッセージを作成することで、レビュープロセスを高速化できます。
- **新しいフィルター** : 送信者、受信者、日付、ドメインなど、複数のフィールドのメッセージフィルターを使用して、ポリシーの警告を調査および修復します。
- **向上したメッセージビュー** : 新しいメッセージソース、テキスト、注釈の各ビューで、調査と修復のアクションがより速くなりました。 修復操作を行うときに、メッセージの添付ファイルが完全なコンテキストを提供するように表示されるようになりました。
- **[ユーザー履歴] ビュー** : 過去の通知やポリシーの一致状況のエスカレーションなどのすべてのユーザーメッセージの修復機能が表示されるようになりました。これで、修復ワークフロープロセス中に、レビュー担当者に詳細なコンテキストが提供されるようになりました。 ユーザーのポリシー一致の最初の回または繰り返しのインスタンスがアーカイブされ、簡単に表示できるようになりました。
- **検出されたパターンの通知 (プレビュー)** : 多くの嫌がらせおよび中の印刷操作は、時間の経過とともに発生し、ユーザーによる同じ動作のインスタンスの繰り返しを伴います。 アラートの詳細に表示される新しいパターンが検出された通知は、これらのアラートとこの種の動作に注意を向けることができます。

### <a name="actionable-insights"></a>対応につながるインサイト

警告、ポリシーの一致、アクション、および傾向の新しい対話型のダッシュボードを使用すると、組織内の保留と解決済みの警告の状態をすばやく表示できます。

- **予防的なインテリジェント警告** : 緊急の注意が必要なポリシーの一致に関する警告には、重要度別に並べ替えられた保留アイテムと、指定された校閲者に送信された新しい自動メール通知についての新規ダッシュボードが含まれます。
- **対話型のダッシュボード** : 新規ダッシュボードには、ポリシーの一致、保留中の解決済みアクション、ユーザーおよびポリシーの傾向が表示されます。
- **監査サポート** : ポリシーおよびレビュー活動の完全なログは、Microsoft 365 コンプライアンスセンターから簡単にエクスポートして、監査レビュー要求のサポートに役立てることができます。

## <a name="integration-with-microsoft-365-services"></a>Microsoft 365 サービスとの統合

通信コンプライアンスポリシーにより、複数の通信チャネル間でメッセージをスキャンおよびキャプチャし、コンプライアンスの問題をすばやく確認して修復することができます。

- **Microsoft teams** : パブリックおよびプライベートの [microsoft teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) チャネルおよび個人チャットのチャット通信は、スタンドアロンチャネルソースとして、または他の microsoft 365 サービスとの通信コンプライアンスでサポートされています。 通信コンプライアンスポリシーで監督するユーザーとグループを選択するときには、個別のユーザー、配布グループ、または特定の Microsoft Teams チャネルを手動で追加する必要があります。
- **Exchange online** : Microsoft 365 組織の [exchange online](https://docs.microsoft.com/Exchange/exchange-online) でホストされているすべてのメールボックスは、スキャン対象となります。 通信コンプライアンスポリシーの条件に一致する電子メールと添付ファイルは、監視とコンプライアンスレポートですぐに使用できます。 Exchange Online はオプションのソースチャネルとなり、通信コンプライアンスポリシーでは不要になりました。
- **Yammer** : [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page) のプライベート メッセージとパブリック コミュニティの会話は、コミュニケーション ポリシーでサポートされています。 Yammer はオプションのチャネルであり、メッセージと添付ファイルのスキャンをサポートするためには、[ネイティブ モード](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)に設定されている必要があります。
- **Skype For Business online** : 通信コンプライアンスポリシーでは、 [Skype for business Online](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)でのチャット通信と関連付けられた添付ファイルのスキャンをサポートしています。
- **サードパーティのソース** : Microsoft 365 組織のメールボックスにインポートされたデータについて、 [サードパーティ](archiving-third-party-data.md) 製のソースからのメッセージをスキャンできます。 コミュニケーションコンプライアンスでは、インスタント Bloomberg など、いくつかの一般的なプラットフォームへの接続がサポートされます。

通信コンプライアンスポリシーのメッセージングチャネルのサポートの詳細については、「 [サポートされる通信の種類](communication-compliance-feature-reference.md#supported-communication-types)」を参照してください。

## <a name="workflow"></a>ワークフロー

コミュニケーションコンプライアンスは、内部ポリシーおよび規制コンプライアンス要件への準拠に関連する一般的な問題点に対処するのに役立つ情報を示します。 フォーカスポリシーテンプレートと柔軟なワークフローを使用すると、実用的な洞察を使用して、検出されたコンプライアンスの問題を迅速に解決できます。

Microsoft 365 での通信コンプライアンスに関するコンプライアンスの問題を特定し、解決するには、次のワークフローを使用します。

![コミュニケーション コンプライアンスのワークフロー](../media/communication-compliance-workflow.png)

### <a name="configure"></a>構成

このワークフローステップでは、コンプライアンス要件を識別し、適切なコミュニケーションコンプライアンスポリシーを構成します。 ポリシーテンプレートは、新しいコンプライアンスポリシーをすばやく構成するだけでなく、要件が変更されたときにポリシーを変更したり更新したりするための最適な方法です。 たとえば、組織内のすべてのユーザーのポリシーを構成する前に、少人数のユーザー グループのコミュニケーションに関する攻撃的な言葉や嫌がらせのポリシーをすばやくテストしたい場合があります。

>[!Important]
>既定では、全体管理者は通信コンプライアンス機能にアクセスできません。 通信コンプライアンス機能のアクセス許可を有効にするには、「 [組織で通信のコンプライアンスを利用できるよう](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)にする」を参照してください。

Microsoft 365 コンプライアンス センターでは、次のポリシー テンプレートから選ぶことができます。

- **不快感または脅迫** 的な言葉: 組み込みの分類子を使用して、不適切または不快感を与える可能性があるコンテンツを自動的に検出するポリシーを、このテンプレートを使用してすばやく作成できます。
- **機密情報** : このテンプレートを使用して、定義された機密情報の種類またはキーワードを含む通信をスキャンするポリシーを作成し、重要なデータがアクセスを許可されていない人と共有されないようにします。
- **法令遵守** : このテンプレートを使用して、規制基準に関連した標準的な財務情報への参照がないかどうか、通信を監視するポリシーを作成します。
- **カスタムポリシー** : このテンプレートを使用して、組織内で監視および確認する特定の通信チャネル、個々の検出条件、およびコンテンツの量を構成します。

### <a name="investigate"></a>調査

この手順では、コミュニケーション コンプライアンス ポリシーに適合するとして検出された問題を掘り下げます。 この手順には、Microsoft 365 コンプライアンスセンターで使用可能な次のアクションが含まれています。

- **警告** : メッセージがポリシーの条件に一致すると、アラートが自動的に生成されます。 通知ごとに、状態、重要度、検出時刻、および高度な電子情報開示ケースが割り当てられているかどうか、およびその状態を確認できます。 新しい通知が [通信コンプライアンスのホーム] ページと [ **通知** ] ページに表示され、重要度の順に一覧表示されます。
- **問題の管理** : 各アラートについて、メッセージで検出された問題の修正に役立つ調査アクションを実行できます。
- **ドキュメントのレビュー** : 問題の調査中に、メッセージの複数のビューを使用して、検出された問題を適切に評価できます。 ビューには、会話の概要、テキストのみ、注釈付き、および詳細ビューが含まれます。
- **ユーザーアクティビティ履歴の確認** : ユーザーメッセージアクティビティの履歴と、過去の通知やエスカレーションなどの修復アクションをポリシー一致について表示します。
- **フィルター** : 送信者、受信者、日付、件名などのフィルターを使用して、確認するメッセージの通知をすばやく絞り込むことができます。

### <a name="remediate"></a>修復する

次の手順では、次のオプションを使用して、調査した通信コンプライアンスの問題を修復します。

- **解決** : 問題を確認した後、アラートを解決して修復できます。 アラートを解決すると、保留中のアラート キューからアラートが削除され、アクションは一致するポリシーの解決済みキューのエントリとして保持されます。 警告を誤検知としてマークした後、警告についてユーザーに通知を送信した後、または警告の新しいケースを開いた後に、アラートが自動的に解決されます。
- **メッセージにタグを付ける** : 問題の解決策の一環として、検出されたメッセージを準拠しているもの、準拠していないもの、または組織のポリシーおよび基準に関連するものとしてタグ付けすることができます。 タグ付けは、エスカレーション用としてまたは他の内部レビュープロセスの一部としてポリシーの警告をフィルター処理するのに役立ちます。
- **ユーザーに通知** する: 多くの場合、ユーザーが誤って、または誤って通信コンプライアンスポリシーに違反しています。 通知機能を使用して、ユーザーに警告通知を送信することで、問題を解決することができます。
- **別のレビュー担当者にエスカレーションする** : 問題を解決するために他のレビュー担当者からの情報が必要になる場合があります。 解決プロセスの一環として、メッセージの問題を組織内の他の分野のレビュー担当者にエスカレーションできます。
- **誤検知としてマーク付けする** : コンプライアンス ポリシーの一致として誤って検出されたメッセージが、確認プロセスに送られることがあります。 これらの種類の通知を誤検知としてマークし、問題を自動的に解決することができます。
- **Teams でメッセージを削除する (プレビュー)** : 不適切なメッセージが、Microsoft Teams チャネルまたは個人およびグループのチャットメッセージに表示されなくなります。 削除された不適切なメッセージは、ポリシー違反についてメッセージが削除されたことを示す通知に置き換えられます。
- **調査対象のエスカレーション** : 最も重大な状況では、通信コンプライアンス情報を組織内の他のレビュー担当者と共有する必要がある場合があります。 コミュニケーション コンプライアンスは他の Microsoft 365 コンプライアンス機能と緊密に統合されており、エンド ツー エンドのリスク解決に役立ちます。 調査のためにケースをエスカレーションすることで、Microsoft 365 の高度な電子情報開示へのケースのデータの転送と管理を行うことができます。 Advanced eDiscovery は、組織の内部および外部の調査に対応するコンテンツを保持、収集、確認、分析、エクスポートするためのエンド ツー エンドのワークフローを提供します。 これにより、法務チームは訴訟ホールド通知ワークフロー全体を管理できます。 Advanced eDiscovery の詳細については、「[Advanced eDiscovery in Microsoft 365の概要](overview-ediscovery-20.md)」を参照してください。

### <a name="monitor"></a>監視

通信コンプライアンスポリシーによって識別されたコンプライアンスの問題を追跡および管理することは、ワークフロープロセス全体に及びます。 通知が生成され、調査と修復アクションが実装されている場合は、既存のポリシーで確認と更新を行う必要があり、新しいポリシーを作成する必要があります。

- **監視とレポート** : 統合監査ログに記録された通信コンプライアンスダッシュボードウィジェット、エクスポートログ、およびイベントを使用して、コンプライアンスの状況を継続的に評価し、改善します。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

- 計画の情報については、「 [Plan for communication コンプライアンス](communication-compliance-plan.md)」を参照してください。
- [Contoso 社のケーススタディ](communication-compliance-case-study.md)を参照して、Microsoft Teams、Exchange Online、Yammer の通信で不快な言葉を監視するための通信コンプライアンスポリシーをすばやく構成した方法を確認します。
- Microsoft 365 組織の通信コンプライアンスを構成するには、「 [microsoft 365 の通信コンプライアンスを構成](communication-compliance-configure.md)する」を参照してください。
