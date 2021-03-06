---
title: Insider リスク管理ユーザーダッシュボード
description: Microsoft 365 の insider リスク管理ユーザーダッシュボードについて
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 224221950104b5dee6a6e8f179db34ee6fad014e
ms.sourcegitcommit: e5ac81132cc5fd248350627a3cc7b3c640f53b6e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48208773"
---
# <a name="insider-risk-management-users-dashboard"></a>Insider リスク管理ユーザーダッシュボード

**ユーザーダッシュボード**は、insider リスク管理ワークフローの重要なツールであり、調査担当者やアナリストがリスクアクティビティをより完全に理解するのに役立てることができます。 このダッシュボードは、insider リスク管理ポリシーの作成と insider リスク管理ケースの管理の間で、管理上のニーズを満たすためのビューおよび管理機能を提供します。

ユーザーが insider リスク管理ポリシーに追加されると、バックグラウンドプロセスによって、 [インジケーターをトリガー](insider-risk-management-settings.md#indicators)するユーザーアクティビティが自動的に評価されます。 インジケーターをトリガーした後、ユーザーアクティビティにはリスクスコアが割り当てられます。 これらのアクティビティの中には、内部者のリスク警告が発生する場合がありますが、一部のアクティビティは、少なくともリスクスコアレベルを満たしていない場合があります。また、内部的なリスク警告は作成されません。 **ユーザーダッシュボード**を使用すると、これらの種類のインジケーターやリスクスコアをユーザーに表示することができます。また、アクティブな insider リスクの通知を持つユーザーを表示することもできます。

また、一般的なイベントが insider リスク管理ワークフローの外部で報告された後に、ユーザーを insider のリスクポリシーに追加する必要があるシナリオもあります。 **ユーザーダッシュボード**を使用すると、特定の期間に対してユーザーを手動で insider リスクポリシーに追加し、ユーザーがトリガーインジケーターを使用するための要件をバイパスできます。 これらのユーザーは、ポリシーに割り当てられている場合は常にユーザーダッシュボードに表示されます。

ユーザーダッシュボードでユーザーが表示される方法の詳細については、次のシナリオを参照してください。

- アクティブな insider リスクポリシー通知があるダッシュボードユーザー
- ダッシュボードをトリガーするユーザー
- ポリシーに一時的に追加されたダッシュボードユーザー

## <a name="dashboard-users-with-active-insider-risk-policy-alerts"></a>アクティブな insider リスクポリシー通知があるダッシュボードユーザー

**ユーザーダッシュボード**には、アクティブな insider リスクポリシー通知を持つすべてのユーザーが自動的に表示されます。 これらのユーザーには、トリガーインジケーターとアクティビティリスクスコアの両方があり、内部的なリスク警告を作成するための要件を満たしています。 これらのユーザーのアクティビティは、ユーザー **ダッシュボード** でユーザーを選択し、[ **ユーザーアクティビティ** ] タブに移動することによって表示されます。

## <a name="dashboard-users-with-triggering-indicators"></a>ダッシュボードをトリガーするユーザー

**ユーザーダッシュボード**には、インジケーターをトリガーするすべてのユーザーが自動的に表示されますが、これには insider リスクの警告を作成するアクティビティリスクスコアはありません。 たとえば、報告された resignation date を持つユーザーが表示されるのは、このイベントはトリガーされますが、リスクスコアがあるアクティビティではないためです。 これらのユーザーのアクティビティは、ユーザー **ダッシュボード** でユーザーを選択し、[ **ユーザーアクティビティ** ] タブに移動することによって表示されます。

## <a name="dashboard-users-added-temporarily-to-policies"></a>ポリシーに一時的に追加されたダッシュボードユーザー

**ユーザーダッシュボード**を使用すると、insider リスク管理ワークフローの外部で例外的なイベントを発生させた後に、既存の insider リスク管理ポリシーにユーザーを一時的に追加することができます。 ユーザーを一時的に追加して、必要なコネクタが構成されていない場合でも、ユーザーを insider リスク管理ポリシーに追加して、ポリシーをテストすることもできます。

ユーザーが手動でポリシーに追加されると、過去90日間のユーザーアクティビティが採点され、 **ユーザーアクティビティ** のタイムラインに追加されます。 たとえば、現在、内部者のリスクポリシーにスコープ内にいないユーザーがいて、ユーザーが組織内の法務部門にデータリークアクティビティを報告しているとします。 法務部門では、ユーザーのために新しい短期的な監視要件を構成することをお勧めします。 ユーザーは、指定した期間 (アクティブ化ウィンドウ) の *データリーク* ポリシーに一時的に割り当てることができます。 一時的に追加されたすべてのユーザーが **ユーザーダッシュボード** に表示されます。トリガーのインジケーター要件は免除されます。

>[!NOTE]
>新たに手動で追加したユーザーが **ユーザーダッシュボード**に表示されるまで数時間かかる場合があります。 これらのユーザーの過去90日間のアクティビティは、表示に最大24時間かかる場合があります。 手動で追加されたユーザーのアクティビティを表示するには、ユーザー **ダッシュボード** でユーザーを選択し、詳細ウィンドウの [ **ユーザーアクティビティ** ] タブを開きます。

**ライセンス認証ウィンドウ**で定義された時間が経過すると、次の場合に、ユーザーは insider Policy と**Users dashboard**から自動的に削除されます。

- ユーザーには、トリガーされたインジケーターまたは insider リスクポリシーの警告はありません。
- 手動で定義された **ライセンス認証ウィンドウ** の期間が、グローバルポリシーの **アクティブ化ウィンドウ** の期間よりも長くなっている場合。 

最も長い期間が設定された **アクティブ化ウィンドウ** の設定は、持続時間が短くなると、 **アクティブウィンドウ** の設定よりも常に優先されます。 たとえば、insider リスク管理のグローバル設定の [グローバル**ポリシー**期間] タブで、**アクティブ化ウィンドウ**を15日間構成している場合は、すべての insider リスクポリシーに自動的に適用されます。 

ユーザーを *データ漏洩* 者のリスクポリシーに一時的に追加し、このユーザーの **アクティブ化ウィンドウ** として30日を定義します。 15日のグローバル **アクティブ化ウィンドウ** の設定は、一時的に追加されたユーザーの **アクティブ化ウィンドウ** の30日の設定を定義することによって上書きされます。 一時的に追加されたユーザーは、 **ユーザーダッシュボード** に残り、30日間、ポリシーの範囲内になります。

一時的に追加されたユーザーに対して定義されている**アクティブ**化ウィンドウの設定よりも、グローバル**アクティブ化ウィンドウ**の設定がこれとは逆のシナリオでは、一時的に追加されたユーザーの [**アクティブ**化] ウィンドウ**の設定が**上書きされます。 一時的に追加されたユーザーは、 **ユーザーダッシュボード** に残り、グローバル **ライセンス認証ウィンドウ** の設定で定義された日数のポリシーの範囲内になります。

## <a name="view-user-information-on-the-users-dashboard"></a>ユーザーダッシュボードでユーザー情報を表示する

**ユーザーダッシュボード**に表示される各ユーザーには、次の情報が含まれています。

- **Users**: ユーザーのユーザー名。 Insider リスク管理のグローバル匿名化設定が有効になっている場合、このフィールドは匿名化です。
- **リスクレベル**: ユーザーの現在の計算されたリスクレベル。 このスコアは24時間ごとに計算され、ユーザーに関連付けられたすべてのアクティブなアラートの警告リスクスコアを使用します。 トリガーのみが発生するユーザーの場合、リスクレベルは0になります。
- **Active alerts**: すべてのポリシーのアクティブなアラートの数。
- **確認**された違反: ユーザーの *確認ポリシー違反* として解決されたケースの数。
- **ケース**: ユーザーの現在のアクティブなケース。

![Insider リスク管理ユーザーダッシュボード](../media/insider-risk-users-dashboard.png)

>[!NOTE]
>**ユーザーダッシュボード**に表示されるユーザー数は、アクティブな通知と一致するポリシーの量によっては、一部のインスタンスで制限される場合があります。 警告が生成されると、アクティブな通知を持つユーザーが **ユーザーダッシュボード** に表示されます。表示されるユーザーの最大数に達した場合、まれに発生することがあります。 このような状況では、表示されていないアクティブな通知を持つユーザーは、既存のユーザー通知がトリアージされているため、 **ユーザーダッシュボード** に追加されます。

## <a name="view-user-details"></a>ユーザーの詳細を表示する

ユーザーのリスクアクティビティの詳細を表示するには、ユーザー **ダッシュボード**でユーザーをダブルクリックして、ユーザーの詳細ウィンドウを開きます。 詳細ウィンドウで、次の情報を表示できます。

- [**ユーザープロファイル**] タブ
    - **[Name and title**]: Azure Active Directory からのユーザーの名前と役職。 Insider リスク管理のグローバル匿名化設定が有効になっている場合、これらのユーザーフィールドは匿名化または empty になります。
    - **ユーザーの電子メール**: ユーザーの電子メールアドレス。
    - **エイリアス**: ユーザーのネットワークエイリアス。
    - **組織または部署**: ユーザーの組織または部署。

- [**ユーザーアクティビティ**] タブ
    - [**最近のユーザーアクティビティの履歴**]: 過去180日までのユーザーアクティビティについて、インジケーターと insider のリスク指標の両方が一覧表示されます。 また、内部的なリスク指標に関連するすべてのアクティビティはスコアを獲得できますが、アクティビティには insider のリスク警告が生成される場合としない場合があります。 トリガーするインジケーターの例は、resignation 日付またはユーザーの最後にスケジュールされた日付である場合があります。 Insider のリスク指標は、リスクの要素があると判断され、ユーザーが含まれるポリシーで定義されています。 イベントおよびリスクアクティビティは、最新のアイテムが最初に一覧表示されます。

## <a name="temporarily-add-a-user-to-a-policy"></a>ポリシーにユーザーを一時的に追加する

ユーザーを insider リスク管理ポリシーに一時的に追加するには、Microsoft 365 コンプライアンスセンターの**insider リスク管理**ソリューションの [**ユーザー** ] タブを使用します。 ユーザーが手動で追加された、 **ユーザーダッシュボード**に追加されて表示されるポリシーのトリガーインジケーター要件。 ユーザーを insider リスク管理ポリシーに永続的に追加するには、ポリシーウィザードを使用します。

既存の insider リスクポリシーにユーザーを追加するには、次の手順を実行します。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**ユーザー** ] タブを選択します。
2. ツールバーの [ **ポリシーにユーザーを追加** ] を選択します。
3. [ **新しいユーザーの追加** ] ダイアログで、[ **ユーザー** ] フィールドにユーザー名を入力します。 ポリシーに追加するユーザーを選択します。
4. [ **ポリシー** ] フィールドのドロップダウン矢印を選択して、構成済みの insider リスク管理ポリシーを表示します。 ユーザーを追加するポリシーを選択します。
5. **ライセンス認証のウィンドウ**スライダーコントロールを使用して、ユーザーがポリシーに含まれ、ユーザーダッシュボードに表示される期間を定義します。 指定した時間によって、ポリシーがこのユーザーに対してアクティブである期間が決まり、最初のアラートが生成されたとき、または (DLP ポリシーのような) トリガーインジケーターが検出されたときに開始されます。 **アクティブ化ウィンドウ**の範囲は、5から30日です。
6. [ **追加** ] を選択し、ポリシーにユーザーを追加する **ことを確認** します。

>[!NOTE]
>新たに手動で追加したユーザーが **ユーザーダッシュボード**に表示されるまで数時間かかる場合があります。 これらのユーザーの過去90日間のアクティビティは、表示に最大24時間かかる場合があります。 手動で追加されたユーザーのアクティビティを表示するには、ユーザー **ダッシュボード** でユーザーを選択し、詳細ウィンドウの [ **ユーザーアクティビティ** ] タブを開きます。

## <a name="run-automated-tasks-with-power-automate-flows-for-a-user"></a>ユーザーのパワー自動化フローで自動化タスクを実行する

推奨される電源自動化フロー、リスク調査担当およびアナリストは、以下のことを迅速に実行できます。

- ユーザーが insider のリスクポリシーに追加されたときに通知する

Insider リスク管理ユーザーのパワー自動化フローを実行、管理、または作成するには、次のようにします。

1. [ユーザー操作] ツールバーの [ **自動化** ] を選択します。
2. 実行する電源の自動化フローを選択し、[ **実行フロー**] を選択します。
3. フローが完了したら、[ **完了**] を選択します。

Insider リスク管理のための電力自動化フローの詳細については、「 [insider リスク管理の設定](insider-risk-management-settings.md#power-automate-flows-preview)の概要」を参照してください。
