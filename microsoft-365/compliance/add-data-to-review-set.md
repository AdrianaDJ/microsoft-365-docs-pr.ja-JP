---
title: 検索結果をレビュー セットに追加する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: 高度な電子情報開示ケースのレビューセットに検索結果またはこれらの検索結果のサンプルを追加する方法について説明します。
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919979"
---
# <a name="add-search-results-to-a-review-set"></a>検索結果をレビュー セットに追加する

検索結果に問題がなければ、検索結果を確認して分析する準備ができたら、それらをレビューセットに追加することができます。 元のデータをレビューセットにコピーすると、テーマの検出、ほぼ重複した検出、電子メールスレッドの識別などの高度な分析ツールを提供することにより、レビューと分析のプロセスも容易になります。 Microsoft 以外の365データソースのデータをレビューセットに追加して、Microsoft 365 から収集したデータに加えて、そのデータを確認できるようにすることもできます。

検索結果をレビューセットに追加すると (ケースのレビューセットが [ **レビューセット** ] タブに一覧表示されます)、次のことが起こります。

- 検索が再度実行されます。 つまり、レビューセットにコピーされる実際の検索結果は、検索が最後に実行されたときに返された推定結果とは異なる場合があります。

- 検索結果内のすべてのアイテムは、live サービスの元のデータソースからコピーされ、Microsoft クラウド内のセキュリティ保護された Azure ストレージの場所にコピーされます。

- すべてのアイテム (コンテンツおよびメタデータを含む) は再インデックス化であり、ケースデータの確認時に、レビューセット内のすべてのデータが完全に検索可能になります。 ケース調査時にレビューセット内のデータを検索すると、データのインデックスが作成されると、完全検索と高速検索が行われます。

- [Microsoft 暗号化テクノロジ](encryption.md)を使用して暗号化され、検索結果で返される電子メールメッセージに添付されるファイルは、電子メールメッセージと添付ファイルがレビューセットに追加されたときに復号化されます。 解読されたファイルをレビューして、レビューセットでクエリを実行できます。 暗号化された電子メール添付ファイルをレビューセットに追加するには、RMS の復号化の役割が割り当てられている必要があります。 詳細については、「 [Microsoft 365 電子情報開示ツールの解読](ediscovery-decryption.md)」を参照してください。

レビューセットにデータを追加するには、[ **検索** ] タブで検索をクリックしてから、ポップアップページの [ **レビューセットに結果を追加** する] をクリックします。

既存のレビューセットに追加したり、新しいレビューセットを作成したりすることができます。  新しい校閲セットに追加する場合は、名前を指定して [ **追加** ] をクリックすると、フライアウトページが表示されます。

![レビューセットを選択してコレクションオプションを構成する](../media/AeD_AddToReviewSet.png)

レビューセットへのデータの追加は、時間のかかるプロセスです。 このプロセスには、Microsoft 365 の元のデータソースからのアイテムの収集 (たとえば、メールボックスやサイトから)、それらを Azure ストレージの場所 (このコピープロセスは、 *取り込み* とも呼ばれます) にコピーしてから、アイテムのインデックスを再作成することが含まれます。 [ **ジョブ** ] タブまたは [ **検索** ] タブで進行状況を追跡するには、[[ **レビューするデータを確認セットに追加しまし** た] 列の状態を監視します。 レビューセット処理が完了した後で、ケースの [ **検査セット** ] タブをクリックし、[レビュー] セットをクリックして、レビューセットのデータのフィルター、確認、タグ付け、エクスポートのプロセスを開始します。

## <a name="define-options-to-scope-your-collection-for-review"></a>レビューのためにコレクションのスコープを設定するオプションを定義する

既存または新しいレビューセットに検索のコンテンツを追加する場合、レビューのためにコンテンツを収集する方法について、次のオプションを使用できます。

- **Sharepoint からバージョンを含める (ベータ版)** : このオプションを使用すると、コレクションのバージョンの制限と検索パラメーターに従って、sharepoint ドキュメントのすべてのバージョンのコレクションを有効にできます。 このオプションを選択すると、レビューセットに追加されるアイテムのサイズが大幅に増加します。

- **会話の取得オプション** : レビューセットに追加されたアイテムは、スレッド化された会話に対して有効になっており、前後の会話のコンテキストでコンテンツを確認するのに役立ちます。 詳細については、「 [Advanced eDiscovery で会話をレビュー](conversation-review-sets.md)する」を参照してください。

- **モダン添付ファイルの取得を有効** にする: 詳細なレビューのためにモダン添付ファイルまたはリンクファイルをコレクションに含めるには、このオプションを使用します。 モダン添付ファイルに関連する検索可能なプロパティの詳細については、「 [Advanced 電子情報開示のドキュメントメタデータフィールド](document-metadata-fields-in-Advanced-eDiscovery.md)」を参照してください。

## <a name="add-a-sample-to-a-review-set"></a>レビューセットにサンプルを追加する

すべてをレビューセットに追加する前に、検索結果をより詳細に検証する場合は、すべてを追加するのではなく、検索結果のサンプルをレビューセットに追加できます。

サンプルをレビューセットに追加するには、[ **検索** ] タブで検索をクリックして、フライアウトページの [ **サンプル** ] をクリックします。 [ **サンプリングパラメーター** ] ページで、次のいずれかのオプションを選択します。

- [ **信頼度レベル%** と **信頼区間%** ]-レビューセットに追加されるアイテムは、設定した統計パラメーターによって決まります。 通常、結果のサンプリング時に信頼度と間隔を使用する場合は、ドロップダウンボックスで指定します。 それ以外の場合は、既定の設定を使用します。

- **ランダムサンプル%** -レビューセットに追加されるアイテムは、検索によって返されるアイテムの総数に対する、指定されたパーセンテージのランダムな選択に基づいています。

前のオプションの1つを選択して構成した後、そのサンプルを追加するレビューセットを選択し、[ **送信** ] をクリックします。 この場合も、[ **ジョブ** ] タブまたは [ **検索** ] タブで進捗状況を追跡するには、[[ **レビューするデータをレビューセットに追加しまし** た] 列の状態を監視します。

## <a name="optical-character-recognition"></a>光学式文字認識

検索結果をレビューセットに追加すると、Advanced eDiscovery の光学式文字認識 (OCR) 機能によって画像からテキストが自動的に抽出されます。また、画像テキストには、校閲セットに追加されるデータが含まれています。 抽出されたテキストは、校閲セットの選択したイメージファイルのテキストビューアーに表示できます。 これにより、画像内のテキストをさらにレビューおよび分析できます。 OCR は、圧縮されていないファイル、電子メールの添付ファイル、および埋め込み画像の場合にサポートされます。 OCRでサポートされている画像ファイル形式のリストについては、[「高度なeDiscoveryでサポートされているファイルタイプ」](supported-filetypes-ediscovery20.md#image)をご覧ください。

Advanced eDiscovery で作成するケースごとにOCR機能を有効にする必要があります。 詳細については、「 [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr)」を参照してください。
