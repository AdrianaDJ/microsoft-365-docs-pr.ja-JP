---
title: パイロットの Microsoft 脅威保護プロジェクトを実行する
description: 試験的な Microsoft の脅威保護プロジェクトを運用環境で実行して、Microsoft の脅威保護 (MTP) のメリットと導入を効果的に決定します。
keywords: Microsoft Threat Protection パイロット、パイロットを実行する Microsoft threat protection プロジェクトを実行する、microsoft threat protection を運用環境において評価する、Microsoft Threat Protection パイロットプロジェクト、サイバーセキュリティ、高度な永続脅威、エンタープライズセキュリティ、デバイス、デバイス、id、ユーザー、データ、アプリケーション、インシデント、自動化された調査と修復、高度な検索
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: bf080fddd7545c4397483c0eba7a010952922e7e
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47956537"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>パイロットの Microsoft 脅威保護プロジェクトを実行する 

**適用対象:**
- Microsoft Threat Protection

Microsoft の脅威保護 (MTP) のメリットと導入を効果的に決定するために、パイロットプロジェクトを実行できます。 運用環境で Microsoft の脅威保護を有効にし、定義されたユースケースから開始する前に、計画プロセスに従って、このパイロットプロジェクトで達成する必要があるタスクを決定し、成功の基準を決定することをお勧めします。 


## <a name="how-to-use-this-pilot-playbook"></a>このパイロットプレイブックの使用方法

このガイドでは、パイロットプロジェクトをセットアップする方法について、Microsoft の脅威保護とステップバイステップガイドの概要を説明します。 

![Microsoft の脅威保護パイロットを実行するフェーズ](../../media/pilotphases.png)

次のサンプルタイムラインは、環境内に適切なリソースがあるかによって異なります。 一部の検出とワークフローでは、他のユーザーよりも多くの学習時間が必要になることがあります。

![Microsoft の脅威保護パイロット実行のサンプルタイムライン](../../media/pilotimeline.png)

>[!IMPORTANT]
>最適な結果を得るには、パイロットの手順をできるだけ忠実に実行します。


### <a name="pilot-playbook-phases"></a>パイロットプレイブックのフェーズ 

Microsoft の脅威保護パイロットの実行には、次の4つのフェーズがあります。

|フェーズ | 説明 | 
|:-------|:-----|
| ![計画](../../media/mtp/plan.png)<br>[計画](mtp-pilot-plan.md)| Microsoft の脅威保護パイロットプロジェクトを実行する前に考慮する必要のある事項について説明します。 <br><br>-スコープ <br> -ユースケース <br>- 要件 <br>-テスト計画 <br> -成功の条件 <br> -スコアカード 
| ![準備](../../media/prepare.png) <br>[準備](mtp-evaluation.md)|  Microsoft 365 セキュリティセンターにアクセスして、Microsoft の脅威保護パイロット環境をセットアップします。 次のようなガイドが表示されます。<br><br>-パイロットの関係者を特定し、承認を求める <br> -環境に関する考慮事項 <br>-アクセス <br>-Azure Active Directory のセットアップ <br> -構成の順序 <br> -Microsoft 365 E5 試用版にサインアップする <br> -ドメインの構成 <br>-Microsoft 365 E5 ライセンスを割り当てる <br> -ポータルのセットアップウィザードを完了します。|
| ![攻撃シミュレーション](../../media/mtp/run-sim.png) <br>[攻撃シミュレーション](mtp-pilot-simulate.md) | 攻撃をシミュレートするには、次のように指導します。<br><br>-テスト環境の要件を確認する <br>-シミュレーションを実行する <br>-インシデントを調査する <br>-インシデントを解決する 
| ![決算と概要](../../media/mtp/close.png) <br>[決算と概要](mtp-pilot-close.md) | プロセスの最後に達すると、次のようになります。<br><br>-最終出力に進む<br>-利害関係者への出力を提示する <br>-フィードバックを提供する <br>-次の手順を実行します。 

## <a name="next-step"></a>次の手順
|![計画フェーズ](../../media/mtp/plan.png) <br>[計画フェーズ](mtp-pilot-plan.md) | Microsoft の脅威保護パイロットプロジェクトを計画する 
|:-------|:-----|