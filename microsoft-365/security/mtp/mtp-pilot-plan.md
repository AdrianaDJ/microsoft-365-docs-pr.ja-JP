---
title: パイロットを計画する (Microsoft 365 Defender プロジェクト)
description: 目標を管理し、成果を確実にするために、パイロットに Microsoft 365 Defender プロジェクトを関係者と計画します。
keywords: Microsoft の脅威保護のパイロット、パイロットのための microsoft の脅威保護プロジェクトの計画、microsoft threat protection の運用プロジェクト、サイバーセキュリティ、高度な脅威、企業セキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: 649f3e777a330e1b60faf4f3513a470b51e56a80
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356981"
---
# <a name="planning-your-pilot-microsoft-365-defender-project"></a>パイロットを計画する (Microsoft 365 Defender プロジェクト) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

|![計画](../../media/phase-diagrams/1-planning.png)<br/>計画|[![準備](../../media/phase-diagrams/2-prepare.png)](prepare-mtpeval.md)<br/>[準備](prepare-mtpeval.md) | [![攻撃のシミュレーション](../../media/phase-diagrams/3-simluate.png)](mtp-pilot-simulate.md)<br/>[攻撃のシミュレーション](mtp-pilot-simulate.md) | [![閉じて要約する](../../media/phase-diagrams/4-summary.png)](mtp-pilot-close.md)<br/>[閉じて要約する](mtp-pilot-close.md)|
|--|--|--|--|
|*ここでは、*| | | |

現在、計画段階になっています。

パイロットプロジェクトが成功したかどうかを確認するには、最初に利害関係者に対して綿密な計画を行い、承認を得ることが重要です。 計画の要素には、範囲の識別、ユースケース、要件、および成功の条件が含まれます。

このガイドでは、パイロットプロジェクトを計画する方法について説明します。 

>[!IMPORTANT]
>最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。


## <a name="scope"></a>範囲

パイロットのスコープによって、環境および使用可能なテスト方法に基づいて、テストの頻度を決定します。 考慮すべきスコープの例を次に示します。
- エンドポイント、サーバー、ドメインコントローラーを含む開発環境またはテスト環境。
- Microsoft 365、Azure、Active Directory サービス、エンドポイント、およびサーバーを使用した運用環境

>[!NOTE]
>まだ完全なライセンスを持っていない場合は、試用版ライセンスを取得して、 [Microsoft 365 Defender を評価](https://aka.ms/mtp-trial-lab) することができます。試験プロジェクトを計画、準備、セットアップ、構成、および実行します。 関係者は、開始から終了までのプロセスを容易にするために、大きな役割を果たします。

評価するオペレーティングシステムの種類も、組織の編成に基づいて定義する必要があります。 これには次のようなものがあります: [Mac エンドポイント](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac#system-requirements)、 [Linux サーバー](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-linux#system-requirements)、 [windows 10 エンドポイント](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)、 [windows Server 2016](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements#supported-windows-versions)。

## <a name="use-cases"></a>使用例

ユースケースは、テスト対象のツールが意図したユーザーによって消費されることを意図したステートメントを表します。 これらは、SOC アナリストなどの特定のペルソナの観点から、ユーザーストーリーとして表現できます。 以下に例を示します。
- SOC アナリストとして、ネットワーク内のデバイス、ユーザー、およびメールボックス全体でアラートとイベントを表示、関連付け、評価、および管理する必要があります。 [インシデント管理]
- SOC アナリストとして、ネットワーク内の悪意のあるイベントを自動的に調査して応答するためのツールとプロセスを用意する必要があります。 [自動赤外線]
- SOC アナリストとして、環境からデータを検索し、既知の脅威と潜在的な脅威、および疑わしいアクティビティを見つける必要があります。 [高度な検索]

これらのユースケースは、定義されたスコープのパラメーター内で作成する必要があることに注意してください。 たとえば、テストの範囲に Microsoft Cloud App Security などのツールの評価が含まれていない場合は、データソースを作成しないで、これに依存するユースケースを使用します。

## <a name="requirements"></a>要件

ユースケースのリストから、要件の作成を開始できます。 要件には、ツールがユースケースを満たすために必要な機能が含まれます。 これらの要件は、構成と保守、統合のサポート、探している機能やカスタム通知の作成機能などの機能固有の要件に分類できます。

## <a name="test-plan"></a>テスト計画

要件に応じて、さまざまなテスト方法が適している場合があります。 たとえば、自動修復の有効性を評価する必要がある場合は、テスト計画に、Microsoft 365 Defender 内で自動修復アクションをトリガーする動作を生成するための手順を含める必要があります。 特定の動作または攻撃を検出する必要がある場合は、テストにさらに手順が含まれることがあります。 その点は、要件を正確にテストするための計画を立てることです。

## <a name="success-criteria"></a>成功の基準

成功の基準は、最終的にテストの対象に対して測定するように設定されたバーです。 Microsoft 365 Defender (またはその他の重要なテクノロジ) を他のツールに対してテストしているかどうか、またはその他のツールに対してテストする場合は、ツールによって提供される値を決定するための定量化可能な条件が必要です。 範囲、要件、およびテスト計画に基づいて、成功の基準によってテストのスコアを決定します。 これは、必要に応じて、合格または失敗し、重み付けの採点が多くなります。 たとえば、特定の重要な領域では、ツールが80% 以上のスコアを必要とすることがあります。

## <a name="scorecard"></a>;

プランのすべての要素をまとめる1つの方法は、スコアカードを作成することです。 以下のサンプルスコアカードを参照してください。

| ユース ケース | 要件 | 構成要件 | テスト計画 | 予想結果 | テストの状態 | スコア | Notes |
|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
|インシデント管理|-Microsoft 365 Defender  </br></br>-Identity の Microsoft Defender </br></br>-エンドポイントの Microsoft Defender </br></br>-Microsoft Cloud App Security (オプション)|詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。 |[攻撃のシミュレーション](mtp-pilot-simulate.md) <br></br>[インシデントを調査する](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#investigate-an-incident) |調査担当は、インシデントの範囲と影響について理解し、インシデントを管理する||||
|自動赤外線|-Microsoft 365 Defender </br></br>-Identity の Microsoft Defender </br></br>-エンドポイントの Microsoft Defender |詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。 <br>自動赤外線を有効にする  |[攻撃のシミュレーション](mtp-pilot-simulate.md) <br></br>[自動調査](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#automated-investigation-and-remediation) |通知とインシデントは、Microsoft 365 Defender によって自動的に修復されます。||||
|高度な検出|-Microsoft 365 Defender </br></br>-エンドポイントの Microsoft Defender </br></br>-Office 用 Microsoft Defender 365 |詳細については、準備、セットアップ、および構成の [前提条件](https://aka.ms/mtp-trial-lab) を参照してください。|[高度な検索のシナリオ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-pilot-simulate#advanced-hunting-scenario) |調査担当者は、高度な検索、影響を受けるエンティティへのピボット、およびカスタム検出の作成によってデータを検索できます。||||



## <a name="next-step"></a>次の手順
|![準備フェーズ](../../media/mtp/prep.png) <br>[準備フェーズ](prepare-mtpeval.md) | Microsoft 365 Defender パイロット環境の準備
|:-------|:-----|
