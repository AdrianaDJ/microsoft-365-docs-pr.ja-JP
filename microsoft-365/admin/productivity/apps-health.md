---
title: Microsoft プロダクティビティスコア-Microsoft 365 アプリの正常性
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Microsoft 365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Microsoft 365 Apps health-テクノロジエクスペリエンスの生産性スコアの詳細。
ms.openlocfilehash: a84e919ce01775b8791ed7a1992464e4f52c7234
ms.sourcegitcommit: a566ef236c85edfd566c8c3f859b80f9e5ce0473
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49562945"
---
# <a name="microsoft-365-apps-health--technology-experiences"></a>Microsoft 365 アプリの正常性–テクノロジエクスペリエンス

生産性スコアは、Microsoft 365 とそれをサポートするテクノロジエクスペリエンスを利用して、組織のデジタル変換に関する洞察を提供します。 組織のスコアは、人とテクノロジの実績を反映しており、組織と同じようなベンチマークと比較できます。 アプリの正常性カテゴリは、テクノロジエクスペリエンスの下にある測定値の一部です。 詳細については、「 [生産性スコアの概要」](productivity-score.md) と「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。

## <a name="why-your-organization39s-microsoft-365-apps-health-score-matters"></a>組織&#39;Microsoft 365 アプリの正常性スコアが重要である理由

組織の生産性は、正常なアプリケーション環境に依存します。 最新バージョンの Microsoft 365 アプリを実行しているデバイスは、推奨チャネルでより安全になり、組織内のユーザーが Microsoft 365 の機能を最大限に活用できるようになります。

## <a name="how-we-calculate-the-microsoft-365-apps-health-score"></a>Microsoft 365 アプリの正常性スコアを計算する方法

Microsoft 365 アプリの正常性スコアを計算するには、各更新プログラムチャネルのデバイスの数を測定します。 また、デバイスでサポートされているバージョンが実行されているかどうか、および Microsoft 365 アプリの最新のリリースを確認します。

ここでは、このカテゴリの主要な指標が含まれている経験について、主な洞察を提供しています。 次に、スコアを計算するために、以下のセクションで詳細なスコアリングフレームワークを使用します。

### <a name="primary-insight"></a>主要な洞察

プライマリ洞察は、更新された推奨チャネルで Microsoft 365 アプリを実行しているデバイスから計算されます。

:::image type="content" source="../../media/appshealth-primary.png" alt-text="Microsoft 365 アプリの表示が主に可視化されています。":::

このことを考慮した情報には、Microsoft 365 アプリチャネル、ビルド、デバイス上で実行されているバージョンがあります。

1. **ヘッダー:**  推奨される更新プログラムチャネルのデバイスのパーセンテージを示します
1. **本文:**  推奨される更新プログラムチャネルでデバイスを実行することにより、最新の更新プログラムを取得し、デバイス上の現在のバージョンを実行する方法について詳しく説明します。
1. **視覚エフェクト (現在の状態):**
    - 青の色の部分が、推奨される更新されたチャネルを実行しているデバイスの割合を表す横棒。
    - 横棒で表されるパーセンテージの計算に使用される分数の (分子または分母) を強調表示します。
    - 推奨更新チャネルで実行されているデバイスのピアベンチマーク値も、パーセンテージとして表示されます。

#### <a name="trend-visualization-of-the-primary-insight"></a>主要な洞察の傾向を視覚化

次のグラフは、推奨される更新プログラムチャネルのうち、過去180日間のデバイスの数を示しています。 折れ線グラフのデータポイントは、過去28日間のアクティビティの集計です。

:::image type="content" source="../../media/appshealth-primarytrend.png" alt-text="推奨される更新プログラムチャネルを実行しているデバイスの傾向を示すグラフ。":::

### <a name="scoring-framework"></a>スコアリングフレームワーク

Microsoft 365 アプリの正常性スコアは、推奨チャネルおよび最新バージョンのデバイスで Microsoft 365 アプリが実行されているかどうかを測定します。

## <a name="explore-your-organization-microsoft-365-app-channels-and-versions"></a>組織を探索する Microsoft 365 アプリのチャネルとバージョン

また、組織内で現在実行されているチャネルとバージョンデバイスの詳細を表示するのに役立つサポート情報も提供します。 これらの追加指標は、生産性スコアに寄与しませんが、推奨チャネルで Microsoft 365 アプリを実行するようにデバイスを決定することで、Microsoft 365 アプリの正常性スコアを向上させるアクションプランを作成するのに役立ちます。

### <a name="devices-on-current-channel-and-running-supported-versions"></a>現在のチャネルのデバイスとサポートされているバージョンの実行

:::image type="content" source="../../media/devices-current-suppported-channel.png" alt-text="現在サポートされているチャネル内のデバイスの数を示す図。":::

1. **ヘッダー:**  強調表示現在のチャネル上のデバイスのうち、サポートされているバージョンの Microsoft 365 アプリを実行している割合
1. **本文:**  推奨チャネルで Microsoft 365 アプリを実行しているデバイスの価値に関する情報を提供します。
1. **視覚エフェクト:**  視覚エフェクトのブレークダウンは、次のように、Microsoft 365 アプリの最新バージョンとサポートされているバージョンのデバイスの割合を表しています。
    - **サポートされているバージョン:** 青いバーは、Microsoft 365 アプリのサポートされているバージョンで実行されているデバイスのパーセンテージを表します。
    - **最新リリース:** 青緑色のカラーバーは、最新のリリース上のデバイスの割合を表します。
1. **詳細情報:**   ヘルプコンテンツを表示するには、このリンクを選択します。

### <a name="devices-running-latest-and-supported-versions"></a>最新およびサポートされているバージョンを実行しているデバイス

:::image type="content" source="../../media/device-supported-versions.png" alt-text="最新バージョンおよびサポートされているバージョンのアプリを実行しているデバイスの数を示す図。":::

1. **ヘッダー:**  サポートされているバージョンと最新のバージョンを実行しているデバイスのパーセンテージを強調表示します。
1. **本文:**  推奨チャネルおよびサポートされている最新バージョンのデバイスを実行しているデバイスの値に関する情報を提供します。
1. **視覚エフェクト:** この視覚エフェクトのブレークダウンは、サポートされているバージョンと Microsoft 365 アプリの最新バージョンを実行しているデバイスの数を表示するための範囲を表すことを目的としています。
    - **サポートされているバージョン:** バーの青 (色付き) 部分と分数 (分子/分母) は、サポートされているバージョンの Microsoft 365 アプリを実行しているデバイスの割合を表します。
        - 分子: 過去28日以内に Microsoft 365 アプリのサポートされているバージョンのデバイスの数
        - 分母: 過去28日以内に Microsoft 365 アプリを使用しているデバイスの数
    - **最新のバージョン:** バーの青緑色 (カラー) 部分と分数 (分子/分母) は、Microsoft 365 アプリの最新バージョンを実行しているデバイスの割合を表します。
        - 分子: 過去28日以内の Microsoft 365 アプリの最新バージョンのデバイスの数
        - 分母: 過去28日以内に Microsoft 365 アプリを使用しているデバイスの数
1. **詳細情報:**   ヘルプコンテンツを表示するには、このリンクを選択します。

#### <a name="trend-visualization-of-the-devices"></a>デバイスの傾向を視覚化

このグラフは、過去180日間にわたる Microsoft 365 アプリのサポートされているバージョンと最新バージョンを実行しているデバイスの傾向ラインを示しています。

:::image type="content" source="../../media/trendline-devices-supportedversions.png" alt-text="サポートされている最新バージョンのアプリを長期間にわたって実行するデバイスの数を showa するグラフ。":::

## <a name="devices-in-your-organization"></a>組織内のデバイス

このセクションでは、Microsoft 365 アプリの正常性テクノロジエクスペリエンスに関するすべての指標に関連情報を提供することによって、注目する指標を操作するのに役立つ情報を提供します。

次の列が、channel/version レベルの表に表示されます。

- **Channel** : デバイス上の現在の Microsoft 365 アプリチャネル。
- **状態:**   Microsoft 365 アプリは、現在のチャネルとバージョンに基づくデバイスの状態をサポートしています。
- **バージョン:**  デバイス上の現在の Microsoft 365 アプリのバージョン。
- **デバイス数:**  デバイスの数。

## <a name="related-content"></a>関連コンテンツ

[コミュニケーション–ユーザーエクスペリエンス](communication.md) (記事) \
[コンテンツコラボレーション–ユーザーエクスペリエンス](content-collaboration.md) (記事) \
[会議– People エクスペリエンス](meetings.md) (記事) \
[モビリティ–ユーザーエクスペリエンス](mobility.md) (記事) \
[生産性スコアのプライバシー統制](privacy.md) (記事) \
[チームワーク–ユーザーエクスペリエンス](teamwork.md) (記事)