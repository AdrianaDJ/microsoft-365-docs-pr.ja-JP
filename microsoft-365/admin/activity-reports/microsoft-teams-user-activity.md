---
title: 管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Microsoft Teams ユーザーアクティビティレポートを取得して、組織内の Teams アクティビティを把握する方法について説明します。
ms.openlocfilehash: 47e12c1cb1b475807ef40e68e09d57db6f01e291
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241836"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>管理センターの microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ

Microsoft 365 **Reports** dashboard には、組織内の製品全体にわたるアクティビティの概要が表示されます。 これにより、個別の製品レベルのレポートを詳細に確認して、各製品内のアクティビティについてより詳しく知ることができます。 [レポートの概要に関するトピック](activity-reports.md)を参照してください。 Microsoft Teams ユーザーアクティビティレポートでは、組織内の Microsoft Teams アクティビティについての洞察を得ることができます。
  
> [!NOTE]
> レポートを表示するには、Microsoft 365 または Exchange、SharePoint、または Skype for Business 管理者のグローバル管理者、グローバルリーダー、またはレポート閲覧者である必要があります。 
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを取得する手順

1. 管理センターで、[**レポート**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用状況</a>] ページの順に移動します。

    
2. **[レポートの選択**] ドロップダウンから、[ **Microsoft Teams** \>の**ユーザーアクティビティ**] を選択します。
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Microsoft Teams ユーザー アクティビティ レポートを解釈する

[ **アクティビティ**] グラフと [ **ユーザー**] グラフを確認すると、Microsoft Teams のユーザー アクティビティを把握することができます。<br/>![Microsoft 365 レポート-Microsoft Teams ユーザーアクティビティ。](../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|||
|:-----|:-----|
|1.  <br/> |[ **Microsoft Teams ユーザー アクティビティ**] レポートでは、過去 7 日間、30 日間、90 日間、または 180 日間の傾向を確認できます。 ただし、レポートで特定の日を選択すると、表 (7) には、(レポートが生成された日付ではなく) 現在の日付から最大 28 日間のデータが表示されます。  <br/> |
|2.  <br/> |各レポートのデータは、通常、過去 24 - 48 時間まで表示されます。  <br/> |
|3.  <br/> |[ **アクティビティ**] ビューには、アクティビティの種類ごとに Microsoft Teams アクティビティの数が表示されます。アクティビティの種類は、チームのチャット メッセージ数、プライベート チャット メッセージ数、コール数、または会議数です。  <br/> |
|4.  <br/> |[ **ユーザー**] ビューには、アクティビティの種類ごとにユーザー数が表示されます。アクティビティの種類は、チームのチャット メッセージ数、プライベート チャット メッセージ数、コール数、または会議数です。  <br/> |
|5.  <br/> | [ **アクティビティ**] グラフの Y 軸は、指定されたアクティビティの数です。  <br/>  [ **ユーザー**] グラフの Y 軸は、チーム チャット、プライベート チャット、コール、または会議に参加したユーザーの数です。  <br/>  グラフの X 軸は、特定のレポートに対して選択した日付範囲です。  <br/> |
|6.  <br/> |凡例の項目を選択して、グラフに表示する系列をフィルター処理できます。 たとえば、[**アクティビティ**] グラフで、**チャネルメッセージ**、**チャットメッセージ**、**通話**、または**会議**を選択すると、それぞれに関連する情報のみが表示されます。 この選択を変更しても、グリッド テーブルの情報は変更されません。  <br/> ![Microsoft Teams アクティビティチャートをフィルターにかける](../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|7.  <br/> | 表示されるグループのリストは、最も長い (180 日) レポート期間にわたって存在した (削除されなかった) すべてのグループのセットによって決まります。アクティビティ数は、日付の選択によって異なります。  <br/> 注: 次の一覧のすべての項目は、追加するまで列に表示されないことがあります。<br/>[ **ユーザー名**] はユーザーのメール アドレスです。 実際のメール アドレスを表示することも、このフィールドを匿名にすることもできます。  <br/> [ **最終活動日 (UTC)**] は、ユーザーが Microsoft Teams アクティビティに参加した最後の日付を指します。  <br/> [ **チャネル メッセージ数**] は、指定された期間内にユーザーがチーム チャットに投稿した一意のメッセージの数です。  <br/> [ **チャット メッセージ数**] は、指定された期間内にユーザーがプライベート チャットに投稿した一意のメッセージの数です。  <br/> [ **コール数**] は、指定された期間内にユーザーが参加したコールの数です。  <br/> [ **会議数**] は、指定された期間内にユーザーが参加したオンライン会議の数です。  <br/> [ **その他のアクティビティ**] は、そのユーザーによるその他のチーム アクティビティの数です。  <br/> [ **削除済み**] は、チームが削除されたかどうかを示します。レポート期間中にアクティビティがあるチームが削除されると、[削除済み] が true に設定された状態でグリッドに表示されます。  <br/> [ **削除日**] は、チームが削除された日付です。  <br/> [ **割り当てられている製品**] は、このユーザーに割り当てられている製品の一覧です。  <br/>  組織のポリシーにより、ユーザー情報を特定できるレポートを表示できない場合は、これらすべてのレポートのプライバシー設定を変更できます。 「**Microsoft 365 管理センターのアクティビティ レポート**」の「[ユーザー レベルの詳細を非表示にする方法](activity-reports.md)」セクションを参照してください。  <br/> |
|8.  <br/> |レポートに列を追加または削除する**列**を選択します。  <br/> ![Teams user activity report - choose columns](../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|9.  <br/> |また、[**エクスポート**] リンクを選択して、レポート データを Excel の .csv ファイルにエクスポートすることもできます。 これにより、すべてのユーザーのデータがエクスポートされ、単純な並べ替えとフィルター処理を行ってさらに分析することができます。 ユーザー数が 2000 未満である場合は、レポート自体のテーブル内で並べ替えとフィルター処理を行うことができます。 ユーザー数が 2000 を超える場合は、フィルター処理と並べ替えを行うために、データをエクスポートする必要があります。  <br/> |
|||
   
