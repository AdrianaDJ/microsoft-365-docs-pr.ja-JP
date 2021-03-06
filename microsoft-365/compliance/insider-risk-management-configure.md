---
title: インサイダー リスクの管理の概要
description: 組織で insider リスク管理を構成します。
keywords: Microsoft 365、insider リスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 793f51146dc85dc1c6750e82301d0e1206187ad9
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558201"
---
# <a name="get-started-with-insider-risk-management"></a>インサイダー リスクの管理の概要

Insider リスク管理ポリシーを使用して、組織内のリスクの通知に対処するための、危険なアクティビティおよび管理ツールを特定します。 前提条件を設定して内部のリスク管理ポリシーを構成するには、次の手順を実行します。

>[!IMPORTANT]
>Microsoft 365 insider リスク管理ソリューションは、お客様がユーザーレベルで内部ガバナンスを促進できるようにするためのテナントレベルのオプションを提供します。 テナントレベルの管理者は、組織のメンバーに対してこのソリューションへのアクセスを提供するためのアクセス許可を設定し、Microsoft 365 コンプライアンスセンターでデータコネクタをセットアップして、関連データをインポートし、潜在的なリスクのあるアクティビティのユーザーレベル id をサポートすることができます。 お客様は、個人ユーザーの行動、文字、または業績に関連する大きなに関する洞察を管理者が計算して、組織内の他のユーザーが利用できるようにすることができます。 また、お客様は、個人のユーザーの行動、文字、または業績大きなに関連した、社内リスク管理サービスからの洞察だけではなく、自分の完全な調査を実施する必要があることを認識しています。 お客様は、Microsoft 365 insider リスク管理サービスを使用するだけで、個々のユーザーの識別やすべての修復アクションに関連する法律を含むすべての関連する機能やサービスを、すべての該当法規に準拠する責任があります。

組織内でのリスク管理に関して insider リスクポリシーがどのように役立つかの詳細については、「 [Microsoft 365 の「insider リスク管理](insider-risk-management.md)」を参照してください。

## <a name="subscriptions-and-licensing"></a>サブスクリプションとライセンス

Insider リスク管理を開始する前に、 [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) とアドオンを確認する必要があります。 Insider リスク管理にアクセスして使用するには、組織が次のいずれかのサブスクリプションまたはアドオンを所有している必要があります。

- Microsoft 365 E5 サブスクリプション (有料または試用版)
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 コンプライアンスアドオン
- Microsoft 365 E3 サブスクリプション + Microsoft 365 E5 Insider リスク管理アドオン
- Microsoft 365 A5 サブスクリプション (有料または試用版)
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 コンプライアンスアドオン
- Microsoft 365 A3 サブスクリプション + Microsoft 365 A5 Insider リスク管理アドオン

Insider リスク管理ポリシーに含まれるユーザーには、上記のいずれかのライセンスを割り当てる必要があります。

既存の Microsoft 365 Enterprise E5 プランを持っておらず、insider リスク管理を試みる場合は、既存のサブスクリプションに [microsoft 365 を追加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) するか、Microsoft 365 Enterprise E5 の [試用版にサインアップ](https://www.microsoft.com/microsoft-365/enterprise) してください。

## <a name="step-1-enable-permissions-for-insider-risk-management"></a>手順 1: insider リスク管理のアクセス許可を有効にする

>[!Important]
>役割グループを構成した後、組織全体で割り当てられているユーザーに役割グループのアクセス許可が適用されるまで、最大で30分かかる場合があります。

内部のリスク管理機能を管理するためのアクセス許可を構成するには、4つの役割グループが使用されます。 これらの構成手順を続行するには、テナント管理者が最初に **Insider リスク管理** または **Insider リスク管理管理者** 役割グループに割り当てる必要があります。 初期構成後に insider リスク管理機能にアクセスして管理するには、ユーザーは少なくとも1つの insider リスク管理役割グループのメンバーである必要があります。

コンプライアンス管理チームの構造に応じて、ユーザーを特定の役割グループに割り当て、さまざまな一連のインサイダー リスク機能を管理するオプションがあります。 Insider リスク管理を構成するときは、次の役割グループオプションから選択します。

| **役割グループ** | **ロール権限** |
| :---- | :---------------- |
| **Insider リスク管理** | この役割グループを使用して、単一グループで組織のインサイダー リスク管理を管理します。 指定された管理者、アナリスト、および調査担当者のすべてのユーザー アカウントを追加して、インサイダー リスク管理権限を 1 つのグループに構成できます。 この役割グループには、すべてのインサイダー リスク管理権限の役割が含まれています。 この構成は、insider リスク管理をすばやく開始するための最も簡単な方法であり、別のユーザーグループに対して定義された個別のアクセス許可を必要としない組織に適しています。|
| **Insider リスク管理管理者** | この役割グループは、最初に insider リスク管理を構成し、後で insider リスク管理者を定義済みグループに分離するために使用します。  この役割グループのユーザーは、インサイダー リスク管理ポリシー、グローバル設定、および役割グループの割り当てを作成、読み取り、更新、および削除できます。 |
| **Insider リスク管理アナリスト** | このグループを使用して、インサイダー リスク ケース アナリストとして機能するユーザーに権限を割り当てます。 この役割グループのユーザーは、すべてのインサイダー リスク管理アラート、ケース、および通知テンプレートにアクセスできます。 インサイダー リスク コンテンツ エクスプローラーにアクセスできません。 |
| **Insider リスク管理の調査官** | このグループを使用して、インサイダー リスク データ調査担当者として機能するユーザーに権限を割り当てます。 この役割グループのユーザーは、すべての insider リスク管理通知、ケース、通知テンプレート、およびコンテンツエクスプローラーにアクセスできます。 |

> [!NOTE]
> これらの役割グループは、現在、特権 Id 管理 (PIM) ではサポートされていません。 PIM の詳細については、「 [Privileged Identity Management で AZURE AD の役割を割り当てる](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-add-role-to-user)」を参照してください。

### <a name="add-users-to-an-insider-risk-management-role-group"></a>Insider リスク管理役割グループにユーザーを追加する

ユーザーを insider リスク管理役割グループに追加するには、次の手順を実行します。

1. [https://protection.office.com/permissions](https://protection.office.com/permissions)Microsoft 365 組織の管理者アカウントの資格情報を使用してサインインします。

2. セキュリティ &amp; /コンプライアンスセンターで、[ **アクセス許可**] に移動します。 Office 365 で役割を表示および管理するためのリンクを選択します。

3. ユーザーを追加する insider リスク管理役割グループを選択して、[ **役割グループの編集**] を選択します。

4. 左側のナビゲーションウィンドウで [ **メンバーの選択** ] を選択し、[ **編集**] を選択します。

5. [ **追加** ] を選択し、役割グループに追加するすべてのユーザーのチェックボックスをオンにします。

6. [**追加**] を選択し、[**完了**] を選択します。

7. [ **保存** ] を選択して、ユーザーを役割グループに追加します。 [ **閉じる** ] を選択して、手順を完了します。

## <a name="step-2-enable-the-audit-log"></a>手順 2: 監査ログを有効にする

インサイダー リスク管理は、ポリシーで構成されたユーザーの分析情報とアクティビティの監査ログを使用します。 監査ログは、内部者のリスク管理ポリシーに関連付けられているすべてのアクティビティ、またはポリシーが変更されたときに使用される概要です。

監査を有効にするための詳細な手順について [は、「監査ログの検索を有効または無効](turn-audit-log-search-on-or-off.md)にする」を参照してください。 監査を有効にすると、監査ログの準備中で、準備が完了してから数時間で検索を実行できるというメッセージが表示されます。 この操作は1回だけ実行する必要があります。 監査ログの使用の詳細については、「 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)」を参照してください。

## <a name="step-3-configure-prerequisites-for-templates"></a>手順 3: テンプレートの前提条件を構成する

ほとんどの insider リスク管理テンプレートには、関連するアクティビティ通知を生成するためにポリシーインジケーターに対して構成する必要がある前提条件があります。 組織に対して構成するポリシーに応じて、適切な前提条件を構成します。

### <a name="configure-microsoft-365-hr-connector"></a>Microsoft 365 HR コネクタを構成する

Insider リスク管理は、サードパーティのリスク管理および人事のプラットフォームからインポートされたユーザーデータとログデータのインポートをサポートしています。 Microsoft 365 人事 (HR) データコネクタを使用すると、ユーザーの終了日、最終雇用日、パフォーマンス向上プランの通知、パフォーマンスレビューアクション、およびジョブレベルの変更状態など、CSV ファイルから人事データを取得できます。 このデータは、インサイダー リスク管理ポリシーでアラート インジケーターを駆動するのに役立ち、組織で完全なリスク管理範囲を構成する上で重要な要素です。 組織に複数の HR コネクタを構成すると、insider リスク管理はすべての人事コネクタから指標を自動的に取得します。

次のポリシーテンプレートを使用する場合は、Microsoft 365 HR connector が必要です。

- ユーザーデータの盗難からの離脱
- ユーザーを出発することによるセキュリティポリシー違反
- 不満のあるユーザーによるセキュリティポリシー違反
- 不満のあるユーザーによるデータリーク

組織のための Microsoft 365 HR コネクタを構成する手順については、「 [hr データをインポートする](import-hr-data.md) ためのコネクタのセットアップ」を参照してください。 HR コネクタを構成した後、これらの構成手順に戻ります。

### <a name="configure-data-loss-prevention-dlp-policies"></a>データ損失防止 (DLP) ポリシーを構成する

Insider リスク管理では、重要度レベルの DLP 通知に関して、不必要な関係者に機密情報を意図的または偶発的に公開することを支援する DLP ポリシーの使用をサポートしています。 いずれかの **データリーク** テンプレートで insider リスク管理ポリシーを構成する場合は、ポリシーに特定の DLP ポリシーを割り当てる必要があります。

DLP ポリシーは、機密情報に関する高い重要度の DLP 通知に関する insider リスク管理のリスクスコアリングを有効にするユーザーを識別するのに役立ちます。また、組織での完全なリスク管理範囲の構成の重要な部分です。 Insider リスク管理および DLP ポリシーの統合と計画の考慮事項の詳細については、「 [insider リスク管理ポリシー](insider-risk-management-policies.md#general-data-leaks)」を参照してください。

>[!IMPORTANT]
>次のことを確認してください。
>
>- DLP および insider リスク管理ポリシーの両方でスコープ内ユーザーを理解し、適切に構成することにより、予想されるポリシーの適用範囲を生成します。
>- これらのテンプレートで使用されている insider リスク管理の DLP ポリシーの [ **インシデントレポート** ] 設定が、重要度の *高い* 通知に対して構成されていることを確認します。 Insider リスク管理警告は、[ **インシデントレポート** ] フィールドが *低* または *中* に設定されている DLP ポリシーから生成されません。

次のポリシーテンプレートを使用する場合は、DLP ポリシーが必要です。

- 一般的なデータリーク
- 優先度の高いユーザーによるデータリーク

組織の DLP ポリシーを構成する手順については、「 [dlp ポリシーの作成、テスト、およびチューニング](create-test-tune-dlp-policy.md) 」を参照してください。 DLP ポリシーを構成した後、これらの構成手順に戻ります。

### <a name="configure-priority-user-groups"></a>優先度ユーザーグループを構成する

Insider リスク管理には、重要な場所、高レベルのデータとネットワークアクセス、またはリスクの動作の過去の履歴を使用して、ユーザーに固有のリスクアクティビティを識別するのに役立つ、ポリシーへの優先ユーザーグループの割り当てのサポートが含まれています。 優先度のユーザーグループを作成し、ユーザーによって提供される固有の状況にグループヘルプのスコープポリシーを割り当てる。

次のポリシーテンプレートを使用する場合は、優先度ユーザーグループが必要です。

- 優先度が高いユーザーによるセキュリティポリシー違反
- 優先度の高いユーザーによるデータリーク

優先度ユーザーグループを作成するためのステップバイステップガイドについては、「 [insider リスク管理の設定](insider-risk-management-settings.md#priority-user-groups-preview) に関する概要」を参照してください。 優先度ユーザーグループを構成した後、これらの構成手順に戻ります。

### <a name="configure-physical-badging-connector-optional"></a>物理バッジコネクタを構成する (オプション)

Insider リスク管理は、物理的な制御およびアクセスプラットフォームからインポートされたユーザーデータとログデータのインポートをサポートしています。 物理バッジコネクタを使用すると、ユーザー id、アクセスポイント id、アクセス時刻と日付、アクセスの状態など、JSON ファイルから access データを取得できます。 このデータは、インサイダー リスク管理ポリシーでアラート インジケーターを駆動するのに役立ち、組織で完全なリスク管理範囲を構成する上で重要な要素です。 組織に複数の物理バッジコネクタを構成すると、insider リスク管理によって、すべての物理バッジコネクタからインジケーターが自動的にプルされます。 すべての insider リスクポリシーテンプレートを使用しているときに、他の内部者のリスク信号を補うために物理バッジ connector からの情報。

>[!IMPORTANT]
>Insider リスク管理ポリシーを使用して、ユーザーの出発および終了に関連するシグナルデータを物理コントロールおよびアクセスプラットフォームからのイベントデータで使用および関連付けます。また、Microsoft 365 HR コネクタも構成する必要があります。 Microsoft 365 HR コネクタを有効にせずに物理バッジを有効にした場合、insider のリスク管理ポリシーは、組織内のユーザーに対して許可されていない物理的アクセスのイベントのみを処理します。

組織の物理バッジを構成する手順については、「 [物理バッジのデータをインポートする](import-physical-badging-data.md) ためのコネクタの設定」を参照してください。 コネクタを構成した後、これらの構成手順に戻ります。

## <a name="step-4-configure-insider-risk-settings"></a>手順 4: insider のリスク設定を構成する

[Insider のリスク設定](insider-risk-management-settings.md) は、ポリシーの作成時に選択したテンプレートに関係なく、すべての内部のリスク管理ポリシーに適用されます。 設定は、すべてのインサイダー リスクの管理タブの 1 番上にある **Insider リスク設定** コントロールを使用して構成します。 これらの設定により、プライバシー、インジケーター、監視ウィンドウ、およびインテリジェントな検出がコントロールされます。

ポリシーを構成する前に、次の内部のリスク設定を定義します。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **insider リスク管理**] に移動し、任意のページの右上隅にある [ **insider のリスク設定**] を選択します。
2. [ **プライバシー** ] ページで、ポリシー通知のユーザー名を表示するためのプライバシー設定を選択します。
3. [ **インジケーター** ] ページで、すべての insider リスクポリシーに適用するアラートインジケーターを選択します。

    >[!IMPORTANT]
    >ポリシーで定義されているリスクの高い活動に関する警告を受信するには、1つ以上のインジケーターを選択する必要があります。

4. [ **ポリシー** の期間] ページで、ユーザーが insider のリスクポリシーの一致をトリガーしたときに有効になる [ポリシー](insider-risk-management-settings.md#policy-timeframes) の期間を選択します。
5. [ **インテリジェントな検出** ] ページで、insider リスクポリシーに対して次の設定を構成します。
    - [異常検出](insider-risk-management-settings.md#anomaly-detections)
    - [不快な言葉の検出](insider-risk-management-settings.md#offensive-language-detections)
    - [警告音量レベル](insider-risk-management-settings.md#alert-volume)
    - [エンドポイント警告状態の Microsoft Defender](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview)
    - [ドメインの設定](insider-risk-management-settings.md#domains-preview)
6. [ **通知のエクスポート** ] ページで、必要に応じて、Office 365 管理 api を使用して insider のリスクの通知情報をエクスポートできるようにします。
7. **手順 3** で作成していない場合は、[**優先度ユーザーグループ**] ページで、優先度ユーザーグループを作成し、ユーザーを追加します。
8. [ **Power 自動フロー** ] ページで、insider のリスクフローテンプレートからのフローを構成するか、新しいフローを作成します。 詳細な手順については、「 [insider リスク管理の設定に](insider-risk-management-settings.md#power-automate-flows-preview) 関する概要」を参照してください。
9. [ **優先度の高い資産] ページ** で、物理コントロールおよび物理バッジによってインポートされたアクセスプラットフォームからのデータを使用するように、優先度資産を構成します。 詳細な手順については、「 [insider リスク管理の設定に](insider-risk-management-settings.md#priority-physical-assets-preview) 関する概要」を参照してください。
10. **Microsoft teams** ページで、microsoft teams と insider リスク管理との統合を有効にして、ケースまたはユーザーのコラボレーションのためのチームを自動的に作成します。 詳細な手順については、「 [insider リスク管理の設定に](insider-risk-management-settings.md#microsoft-teams-preview) 関する概要」を参照してください。
11. [ **保存** ] を選択して、insider のリスクポリシーについてこれらの設定を有効にします。

## <a name="step-5-create-an-insider-risk-management-policy"></a>手順 5: insider リスク管理ポリシーを作成する

インサイダー リスク管理ポリシーには、ユーザーが割り当てられており、アラート用に構成されているリスク インジケーターの種類が定義されています。 アクティビティがアラートをトリガーする前に、ポリシーを構成する必要があります。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**ポリシー** ] タブを選択します。
2. [ **ポリシーの作成** ] を選択して、ポリシーウィザードを開きます。
3. [ **新しい insider リスクポリシー** ] ページで、以下のフィールドに入力します。
    - [**名前 (必須)**]: ポリシーのフレンドリ名を入力します。
    - **説明 (省略可能)**: ポリシーの説明を入力します。
    - **[ポリシーテンプレートの選択 (必須)]**: ポリシーによって監視されるリスク指標の種類を定義する [ポリシー](insider-risk-management-policies.md#policy-templates) テンプレートのいずれかを選択します。

    >[!IMPORTANT]
    >ほとんどのポリシーテンプレートには、関連するアラートを生成するためにポリシーに対して構成する必要がある前提条件があります。 適用可能なポリシーの前提条件を構成していない場合は、上記の **ステップ 3** を参照してください。

    >[!CAUTION]
    >2020年10月16日以降、電子メールテンプレートに不快な言葉を使用してポリシーを作成することはできなくなりました。 このテンプレートを使用するアクティブなポリシーは、2021年1月に完全に削除されるまで機能します。

4. [ **次** へ] を選択して続行します。
5. [ **ユーザー** ] ページで、選択したポリシーテンプレートに応じて、[ **ユーザーまたはグループの追加** ] または [ **優先度ユーザーグループの選択** ] を選択して、ポリシーに含めるユーザーまたは優先度ユーザーグループを定義します。 該当する場合は **、[すべてのユーザーおよびメールが有効なグループ** ] チェックボックスをオンにします (優先度のユーザーベースのテンプレートを選択していない場合)。 [ **次** へ] を選択して続行します。
6. [ **優先度を設定するコンテンツを指定する (オプション)** ] ページで、リスクスコアが増加した場合の優先度を設定するためのソースを割り当てることができます。 ただし、関連するコンテンツに組み込みまたはカスタムの機密情報の種類が含まれているか、またはこのページで優先度として指定されていない限り、一部のアクティビティで通知が生成されることはありません。
    - **Sharepoint サイト**: [ **Sharepoint サイトの追加** ] を選択し、優先度を設定する sharepoint 組織を選択します。 たとえば、 *"group1@contoso.sharepoint.com/sites/group1"* のようになります。
    - **機密情報の種類**: [ **機密性の高い情報** の種類を追加] を選択し、優先度を設定する感度の種類を選択します。 たとえば、 *"米国の銀行口座番号"* や *"クレジットカード番号*" などです。
    - [**秘密度ラベル**]: [**感度ラベルの追加**] を選択し、優先順位を設定するラベルを選択します。 たとえば、 *"Confidential* " や *"Secret"* などです。
7. [ **次** へ] を選択して続行します。
8. [**ポリシーインジケーターの選択**] ページに、[ **Insider リスク設定** 指標] ページで利用可能として定義した [インジケーター](insider-risk-management-settings.md#indicators)が表示され  >  **Indicators** ます。 ウィザードの開始時に *データリーク* テンプレートを選択した場合は、[ **dlp ポリシー** ] ドロップダウンリストから dlp ポリシーを選択して、ポリシーのトリガーインジケーターを有効にする必要があります。 ポリシーに適用するインジケーターを選択します。 これらの指標に対して既定のポリシーしきい値設定を使用しない場合は、[ **Microsoft が推奨する既定のしきい** 値を使用する] をオフにして、選択した各インジケーターのしきい値を入力します。 少なくとも1つの *Office* または *デバイス* インジケーターを選択した場合は、必要に応じて **リスクスコアブースター** を選択します。 リスクスコアブースターは、選択したインジケーターにのみ適用されます。

    >[!IMPORTANT]
    >このページのインジケーターを選択できない場合は、[ **Insider リスク管理** の  >  **設定**  >  ]**ポリシーの指標** ページで、すべてのポリシーに対して有効にするインジケーターを選択する必要があります。

9. [ **次** へ] を選択して続行します。
10. [**ポリシー** の期間] ページに、[ **Insider リスク設定** ポリシーのポリシー] タイムシートページにあるポリシーの [アクティブ化ウィンドウの条件](insider-risk-management-settings.md#policy-timeframes)が表示され  >  **Policy timeframes** ます。
11. [ **次** へ] を選択して続行します。
12. [ **レビュー** ] ページで、ポリシーに対して選択した設定を確認します。 [ **編集** ] を選択してポリシー値を変更するか、[ **Submit** ] を選択してポリシーを作成してアクティブ化します。

## <a name="next-steps"></a>次の手順

最初の insider リスク管理ポリシーを作成するための手順を完了すると、約24時間後にアクティビティインジケーターから通知を受信することが開始されます。 この記事の手順4のガイダンスまたは「 [新しい insider リスクポリシーの作成](insider-risk-management-policies.md#create-a-new-policy)」の手順に従って、必要に応じて追加のポリシーを構成します。

Insider リスクの通知と **通知ダッシュボード** の詳細については、「 [insider リスク管理の警告](insider-risk-management-alerts.md)」を参照してください。
