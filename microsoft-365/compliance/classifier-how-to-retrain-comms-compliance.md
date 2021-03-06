---
title: コミュニケーションコンプライアンスで分類子を再トレーニングする方法 (プレビュー)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: コミュニケーションコンプライアンスの trainable 分類子にフィードバックを提供する方法について説明します。
ms.openlocfilehash: 1466c211e3a4958f58a7c1f1a6a5a77bed881d60
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132355"
---
# <a name="how-to-retrain-a-classifier-in-communications-compliance-preview"></a>コミュニケーションコンプライアンスで分類子を再トレーニングする方法 (プレビュー)

Microsoft 365 trainable クラシファイアは、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。このツールを使用して、さまざまな種類のコンテンツを確認できます。 トレーニングを受けた後、それを使用して、Office の秘密度ラベル、通信コンプライアンスポリシー、および保持ラベルポリシーのアプリケーションの項目を識別できます。

この記事では、カスタムの trainable 分類子のパフォーマンスを向上させる方法、およびその他のフィードバックを提供することによって事前に学習した分類子について説明します。

分類子のさまざまな種類の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-learn-about.md)」を参照してください。

## <a name="permissions"></a>アクセス許可

Microsoft 365 コンプライアンスセンターで分類子にアクセスするには、次のようにします。

- 分類子を教育するには、コンプライアンス管理者ロールまたはコンプライアンスデータ管理者が必要です。

次のシナリオでは、分類子を使用するために、以下のアクセス許可を持つアカウントが必要になります。

- コミュニケーションコンプライアンスポリシーのシナリオ: Insider リスク管理管理者、監督レビュー管理者 

## <a name="overall-workflow"></a>全体的なワークフロー

> [!IMPORTANT]
> 分類子を条件として使用するコンプライアンスソリューションにフィードバックを提供します。 **分類子を条件として使用する通信コンプライアンスポリシーがない場合は、ここで停止してください。**

分類子を使用する際には、作成する分類の精度を高めることができます。 これを行うには、一致していると判断されたアイテムに対して行われた分類の品質を評価します。 分類子に対して30の評価を行うと、そのフィードバックが取得され、自動的に retrains ます。

分類子の再トレーニングの全体的なワークフローの詳細については、「分類の再 [トレーニングのプロセスフロー](classifier-learn-about.md#retraining-classifiers)」を参照してください。

> [!NOTE]
> 分類子は、retrained する前に、既に公開され、使用中である必要があります。

## <a name="how-to-retrain-a-classifier-in-communication-compliance-policies-preview"></a>コミュニケーションコンプライアンスポリシー (プレビュー) で分類子を再トレーニングする方法

1. 分類子を条件として使用する通信コンプライアンスポリシーを開き、[ **保留中** ] リストから特定されたアイテムの1つを選択します。
2. 省略記号を選択して、 **分類を改善**します。
3. [ **詳細なフィードバック** ] ウィンドウで、アイテムが真陽性の場合は、[ **一致**] を選択します。  アイテムが誤検知の場合は、そのアイテムが誤ってカテゴリに含まれている場合は、[ **一致しない**] を選択します。
4. アイテムにより適した別の分類子がある場合は、[ **その他の trainable 分類子の候補** リスト] から選択できます。 これにより、他の分類子がアイテムを評価するようになります。

> [!TIP]
> 複数のアイテムを選択して、コマンドバーに [ **詳細なフィードバックを提供** する] を選択することにより、複数のアイテムに対してフィードバックを同時に提供することができます。

5. [ **フィードバックの送信** ] を選択して、の評価を送信し、 `match` 分類された `not a match` 他の trainable 分類子を提案します。 フィードバックの30個のインスタンスを分類子に提供した場合、その結果は自動的に再トレーニングされます。 再トレーニングには1-4 時間かかることがあります。 分類子は、1日に2回だけ retrained することができます。

> [!IMPORTANT]
> この情報は、テナント内の分類子に送られるので、 **Microsoft には戻りません**。

6.  **Microsoft 365 コンプライアンスセンター**で [**データ分類**] ページを開きます。
7. **Trainable 分類子 (プレビュー)** を開きます。
8. コミュニケーションコンプライアンスポリシーで使用されていた分類子が、[ **トレーニング** ] の見出しの下に表示されます。

![再トレーニングの状態の分類子](../media/classifier-retraining.png)

9. 再トレーニングが完了したら、分類子を選択して、[再トレーニングの概要] を開きます。

![分類子の再トレーニング結果の概要](../media/classifier-retraining-overview.png)

10. 推奨されるアクションと、分類子の retrained および現在公開されているバージョンの予測比較を確認します。
11. 再トレーニングの結果に問題がなければ、[ **再公開**] を選択します。
12. 再トレーニングの結果に満足できない場合は、コミュニケーションコンプライアンスインターフェイスの分類子に対して追加のフィードバックを提供し、別の再トレーニングサイクルを開始するか、または何も実行しないで、現在公開されている分類子の現在のバージョンを引き続き使用できます。 

## <a name="details-on-republishing-recommendations"></a>おすすめ候補の再発行の詳細

Retrained 分類子を再発行したり、さらに再トレーニングを提案したりする際の推奨事項を以下に示します。 これには、trainable 分類子のしくみについて、さらに深く理解する必要があります。

再トレーニングの後は、フィードバック付きのアイテムと、分類子の学習に使用されたアイテムの両方で、分類子のパフォーマンスを評価します。 

- 組み込みモデルでは、分類子のトレーニングに使用されるアイテムは、モデルを構築するために Microsoft によって使用されるアイテムです。
- カスタムモデルの場合、分類子の元のトレーニングで使用されたアイテムは、テストおよびレビュー用に追加したサイトのものです。

Retrained と発行された分類子の両方のアイテムセットのパフォーマンス番号を比較して、再発行が改善されたかどうかに関する推奨事項を提示します。 

## <a name="see-also"></a>関連項目

- [Trainable 分類子 (プレビュー) について](classifier-learn-about.md)
- [SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
