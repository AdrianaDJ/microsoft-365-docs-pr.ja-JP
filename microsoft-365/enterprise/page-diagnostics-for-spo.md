---
title: SharePoint Online のページ診断ツールを使用する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: Sharepoint Online のページ診断ツールを使用して、事前に定義されたパフォーマンス条件のセットに対して SharePoint Online モダンポータルと従来の発行ページを分析します。
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696223"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>SharePoint 用ページ診断ツールを使用する

この記事では、 **sharepoint 用ページ診断ツール** を使用して、事前に定義されたパフォーマンス基準のセットに対して sharepoint Online モダンおよび従来のサイトページを分析する方法について説明します。

SharePoint 用のページ診断ツールをインストールするには、次の方法があります。

- **Microsoft Edge** [(エッジ内線番号)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **クロム** [(クロム拡張機能)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>バージョン **2.0.0** 以降では、従来のサイトページに加えて、モダンページのサポートが含まれています。 使用しているツールのバージョンがわからない場合は、バージョン **情報** のリンクまたは省略記号 (...) を選択して、バージョンを確認できます。 ツールを使用するとき**は、常に最新バージョンに更新**してください。

SharePoint 用ページ診断ツールは、新しい Microsoft Edge (https://www.microsoft.com/edge) と Chrome のブラウザー拡張機能であり、SharePoint Online の最新ポータルと従来の発行サイト ページの両方を分析します。 このツールは、SharePoint Online に対してのみ機能し、SharePoint システムページでは使用できません。

解析された各ページに対して、定義済みのルールセットに対してページがどのように表示されるかを示すレポートを生成し、テストの結果が基準値の範囲外にある場合に詳細情報を表示します。 SharePoint Online 管理者と設計者は、このツールを使用して、パフォーマンスの問題のトラブルシューティングを行ったり、発行前に新しいページを最適化することができます。

ページ診断ツールは、SharePoint サイトページのみを分析するように設計されています。これは、 *allitems* や *sharepoint .aspx*などのシステムページではありません。 システムページまたはその他のサイト以外のページでツールを実行しようとすると、そのページの種類に対してツールを実行できないことを示すエラーメッセージが表示されます。

![SharePoint ページ上で実行する必要がある](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

このツールでは、[ライブラリまたはシステムページの評価] に値がないため、このエラーは発生しません。 このツールを使用するには、SharePoint サイトページに移動してください。 SharePoint ページでこのエラーが発生した場合は、マスターページを確認して、SharePoint メタタグが削除されていないことを確認してください。

ツールに関するフィードバックを提供するには、ツールの右上隅にある省略記号を選択してから、[ [フィードバックを提供](https://go.microsoft.com/fwlink/?linkid=874109)する] を選択します。

![フィードバックを送信](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>SharePoint 用のページ診断ツールをインストールする

このセクションのインストール手順は、Chrome ブラウザーと Microsoft Edge ブラウザーの両方で機能します。

> [!IMPORTANT]
> Microsoft では、SharePoint 用ページ診断ツールによって分析されたデータやページのコンテンツは読み取られません。また、個人情報、web サイト、またはダウンロード情報は収集されません。 ツールによって Microsoft に記録される唯一の情報は、テナント名、失敗したルールの数、およびツールが実行された日時です。 この情報は Microsoft によって使用され、モダンポータルと発行サイトの使用傾向と一般的なパフォーマンスの問題をより深く理解しています。

1. **Microsoft edge** [(エッジエクステンション)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)または**chrome** [(クロム拡張機能)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)用の SharePoint 用のページ診断ツールをインストールします。 ストアの [説明] ページで提供されるユーザーのプライバシーポリシーを確認してください。 このツールをブラウザーに追加すると、次のアクセス許可に関する通知が表示されます。

    ![拡張機能のアクセス許可](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    この通知が表示されるのは、ページには、web パーツおよびページのカスタマイズに応じて、SharePoint の外部にある場所のコンテンツが含まれる可能性があるためです。 これは、ツールが実行されているアクティブな SharePoint タブでのみ [開始] ボタンがクリックされたときに、要求と応答を読み取ることを意味します。 この情報は、web ブラウザーによってローカルにキャプチャされ、ツールの [_ネットワークトレース_] タブの [ **JSON へのエクスポート**] または [ **har へのエクスポート**] ボタンで利用できます。**情報は、Microsoft によって送信または取得されることはありません。** ( [こ](https://go.microsoft.com/fwlink/p/?linkid=857875)のツールでは、Microsoft のプライバシーポリシーにアクセスできます)。

    [ _ダウンロードの管理_ ] アクセス許可は、ツールの **JSON へのエクスポート** 機能の使用に適用されます。 結果に Url が含まれており、PII (個人を特定できる情報) として分類できるため、組織の外部で JSON ファイルを共有する前に、会社のプライバシーガイドラインに従ってください。
1. Incognito または InPrivate モードでこのツールを使用する場合は、お使いのブラウザーの手順に従います。
    1. Microsoft Edge で、[ **拡張子** ] に移動するか、URL バーに「 _edge://extensions_ 」と入力して、拡張機能の **詳細** を選択します。 [拡張機能の設定] で、[ **InPrivate で許可**] のチェックボックスをオンにします。
    1. Chrome で、[ **拡張子** ] に移動するか、URL バーに「 _chrome://extensions_ 」と入力して、拡張機能の **詳細** を選択します。 [内線番号] の設定で、[ **allow In Incognito**] のスライダーを選択します。
1. 確認したい sharepoint Online の SharePoint サイトページに移動します。 ページ上のアイテムの "遅延読み込み" が許可されています。このため、ツールは自動的に停止されません (これは、すべてのページ読み込みシナリオに対応するように設計されています)。 コレクションを停止するには、[ **停止**] を選択します。 データ収集を停止する前に、ページの読み込みが完了していることを確認してください。または、部分的なトレースのみをキャプチャします。
1. 拡張機能のツールバーボタンをクリックします。 ![SharePoint ロゴのページ診断](../media/page-diagnostics-for-spo/pagediag-icon32.png) ツールを読み込むと、次の拡張子ポップアップウィンドウが表示されます。

    ![ページ診断ツールのポップアップ](../media/page-diagnostics-for-spo/pagediag-Landing.png)

[ **開始** ] を選択して、分析のためのデータの収集を開始します。

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>ページ診断 (SharePoint) ツールに表示される内容

1. ツールの右上隅にある省略記号 ([...]) をクリックして、次のリンクを検索します。
   1. 「 **その他の技術** 情報」リンクには、この記事へのリンクを含む、このツールに関する一般的なガイダンスと詳細情報が記載されています。
   1. [ **フィードバック** の送信] リンクを使用する _と、SharePoint サイトとコラボレーションユーザーの音声_ サイトへのリンクを利用できます。
   1. **About**リンクには、現在インストールされているツールのバージョンと、ツールのサードパーティの通知への直接リンクが含まれています。  
1. **関連付け ID、SPRequestDuration、Sprequestduration**、**ページ読み込み時間**、および**URL**の詳細は情報で、いくつかの目的に使用できます。

    ![ページ診断の詳細](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID** は、Microsoft サポートを使用している場合に、特定のページの追加の診断データを収集できる重要な要素です。
   - **Sprequestduration** は、SharePoint がページを処理するのに要した時間です。 構造ナビゲーション、大きい画像、多くの API 呼び出しは、すべての期間を長くすることができます。
   - **Spiislatency** は、SharePoint Online がページの読み込みを開始するまでにかかる時間 (ミリ秒単位) です。 この値には、web アプリケーションが応答するのにかかる時間は含まれません。
   - **Page load time** は、応答がブラウザーで受信されてレンダリングされた時点までの、要求の時間からページによって記録された時間の合計です。 この値は、ネットワークの待機時間、コンピューターのパフォーマンス、ブラウザーがページを読み込むためにかかる時間など、さまざまな要因の影響を受けます。
   - **ページの URL** (Uniform resource Locator) は、現在のページの web アドレスです。

1. [ [**診断テスト**](#how-to-use-the-diagnostic-tests-tab) ] タブでは、分析結果が3つのカテゴリに表示されます。 **対処は必要ありません**。 **改善の機会** と **注意が必要**です。 各テスト結果は、次の表に示すように、これらのカテゴリのいずれかのアイテムによって表されます。

    |カテゴリ  |色  |説明  |
    |---------|---------|---------|
    |**アテンションが必要** |赤 |テスト結果は、基準値の範囲外にあり、ページのパフォーマンスに影響を与えます。 修復ガイダンスに従います。|
    |**向上したオポチュニティ** |黄 |テスト結果は基準値の範囲外になり、パフォーマンスの問題に寄与する可能性があります。 テスト固有の条件が適用される場合があります。|
    |**操作は不要** |緑 |テスト結果はテストのベースライン値の範囲内にあります。|

    ![ページ診断](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. [ [**ネットワークトレース**](#how-to-use-the-network-trace-tab) ] タブには、ページのビルド要求と応答に関する詳細が表示されます。

## <a name="how-to-use-the-diagnostic-tests-tab"></a>[診断テスト] タブの使用方法

Sharepoint のモダンポータルページまたは従来の発行サイトページを、SharePoint ツールのページ診断を使用して分析する場合、結果を基準値と比較し、[ **診断テスト** ] タブに表示する定義済みのルールを使用して、結果が分析されます。特定のテストのルールでは、2つの特定のパフォーマンス特性の違いに応じて、

「 **改善の機会** 」または「 **要注意** 」のカテゴリに表示されるテスト結果は、推奨されるプラクティスに照らして見直す必要のある領域を示し、結果に関する追加情報を表示するために選択できます。 各アイテムの詳細には、テストに関連する適切なガイダンスに直接移動する [ _詳細情報_ ] リンクが含まれています。 [ **アクションなし** ] カテゴリに表示されるテスト結果は、関連付けられたルールに準拠しており、選択したときに追加の詳細が表示されないことを示します。

[診断テスト] タブの情報には、ページの設計方法は示されませんが、ページのパフォーマンスに影響を与える可能性がある要因は強調表示されます。 ページの機能やカスタマイズによっては、ページのパフォーマンスへの影響が避けられる場合があります。影響が大きい場合は、問題が発生しているかどうかを確認する必要があります。

赤または黄色の結果は、データが頻繁に更新される web パーツを示している場合もあります。 たとえば、企業ニュースは1秒ごとに更新されませんが、ユーザーの全体的な動作を向上させるキャッシュ要素を実装するのではなく、1秒ごとにカスタム web パーツが作成されることがよくあります。 Web パーツをページに含める際には、使用可能な各パラメーターの値を評価して、その目的に応じて適切に設定されていることを確認することによって、パフォーマンスへの影響を軽減するための簡単な方法があることを念頭に置いてください。

>[!NOTE]
>発行機能が有効になっていない従来のチームサイトでは、CDNs を使用できません。 これらのサイトでこのツールを実行すると、CDN テストは失敗し、無視される可能性がありますが、残りのすべてのテストが適用されます。 SharePoint 発行機能の追加機能を使用すると、ページの読み込み時間が長くなる可能性があるため、CDN 機能を許可するだけで有効にすることはできません。

>[!IMPORTANT]
>テストルールは定期的に追加および更新されるため、最新バージョンのツールを参照して、現在のルールおよびテスト結果に含まれる特定の情報の詳細を確認してください。 拡張機能を管理することにより、バージョンを確認することができます。また、拡張機能を使用すると、更新プログラムが利用可能かどうかを確認できます。

## <a name="how-to-use-the-network-trace-tab"></a>[ネットワークトレース] タブの使用方法

[ **ネットワークトレース** ] タブには、ページのビルドおよび SharePoint から受信した応答の両方の要求に関する詳細情報が表示されます。

1. **赤としてフラグが付けられたアイテムの読み込み時刻を検索**します。 各要求と応答は、次の遅延指標を使用して、ページ全体のパフォーマンスに影響を示すように色分けされています。
    - 緑: \< 500ms
    - 黄: 500-1000 ミリ秒
    - 赤: \> 1000 ミリ秒

    ![ネットワークトレース](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    上記の図では、赤の項目が既定のページに関連しています。 ページが \< 1000 ミリ秒 (1 秒未満) で読み込まれない限り、常に赤で表示されます。

2. **テストアイテムの読み込み時間**。 アイテムはブラウザーによって既にキャッシュされているため、時間やカラーインジケーターが表示されない場合があります。 この問題を正しくテストするには、ページを開き、ブラウザーのキャッシュをクリアしてから [ **開始** ] をクリックします。これにより、ページの読み込みが強制的に "コールド" され、最初のページ読み込みが実際に反映されるようになります。 これは、ページ上でキャッシュされているアイテムを特定するのに役立つように、"ウォーム" ページ読み込みと比較する必要があります。

3. **関連する詳細情報を他のユーザーと共有して、問題の調査に役立てることができ**ます。 ツールで提供される詳細または情報を開発者や技術サポート担当者と共有するには、[ **JSON へのエクスポート** ] をクリックします (上記の図を参照)。 これにより、JSON ファイルビューアーを使用して、結果をダウンロードできるようになります。

    プレビュー機能を使用することを選択した場合、[ *HAR* へのエクスポート] が有効になっている場合、エクスポートの種類は **har へのエクスポート**として表示されます。

    ![ネットワークトレース](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> これらの結果には Url が含まれており、PII (個人を特定できる情報) として分類することができます。 その情報を配布する前に、組織のガイドラインに従っていることを確認してください。

## <a name="engaging-with-microsoft-support"></a>Microsoft サポートへの協力

サポートが直接実行される場合にのみ使用する必要がある **Microsoft サポートレベルの機能** が含まれています。 この機能を利用することによって、サポートチーム契約を伴わずに使用してもメリットはありません。また、ページのパフォーマンスが大幅に遅くなる可能性があります。 この機能をツールで使用するときに、追加情報がサービスのログに追加されるため、追加情報はありません。

変更は表示されません。ただし、有効になっていることが通知され、ページのパフォーマンスが2-3 倍になり、パフォーマンスが大幅に低下します。 これは特定のページとアクティブなセッションにのみ関連しています。 このため、これは慎重に使用し、サポートを積極的に参加させる必要があります。

### <a name="to-enable-the-microsoft-support-level-feature"></a>Microsoft サポートレベル機能を有効にするには

1. SharePoint 用のページ診断ツールを開きます。
2. キーボードで、ALT + **Shift + L**キーを押します。 これにより、[ **サポートログを有効にする** ] チェックボックスが表示されます。
3. チェックボックスをオンにし、[ **開始** ] をクリックしてページを再度読み込み、詳細ログを生成します。

    ![サポートオプションが有効](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    CorrelationID (ツールの上部に表示されている) を確認し、それをサポート担当者に提供して、診断セッションに関する追加情報を収集できるようにする必要があります。

## <a name="related-topics"></a>関連項目

[SharePoint Online のパフォーマンスをチューニングする](tune-sharepoint-online-performance.md)

[Office 365 のパフォーマンスをチューニングする](tune-microsoft-365-performance.md)

[SharePoint のモダン エクスペリエンスにおけるパフォーマンス](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[コンテンツ配信ネットワーク](content-delivery-networks.md)

[SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)
