---
title: 手動予約を作成する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: 次の手順に従って、Microsoft の予約アプリを使用して予定を作成し、従業員を割り当てます。
ms.openlocfilehash: dffc63b1f638c551e40d22852b1ba6a73c5be869
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962563"
---
# <a name="create-a-manual-booking"></a>手動予約を作成する

予約のスケジュールとスタッフの割り当てには 2 つの方法があります。 最初の方法は、お客様が自分の web サイトに追加したスタンドアロンの予約ページまたは組み込み予約ページを使用している場合です。 もう1つの方法は、顧客が予定を呼び出すときなど、自分または自分の従業員が手動で予約を入力できるようにすることです。 この記事は手動のシナリオについて説明します。

1. Microsoft 365 で、アプリ起動ツールを選択し、[ **予約**] を選択します。

   ![アプリ起動ツールでの予約の画像](../media/bookings-applauncher.png)

1. In the navigation pane, select **Calendar** \> **New booking**.

   ![新しい予約 UI の画像](../media/bookings-newbooking.png)

1. 提供するサービスを選びます。 サービスのセットアップの手順については [、「Microsoft 予約のサービスオファーリングの定義](define-service-offerings.md) 」を参照してください。

1. 顧客情報 (名前、メール アドレス、電話番号などの関連情報) を入力します。

1. サービスを提供するスタッフ メンバーを選びます。 表示されるスタッフ メンバー リストは、[サービス] ページでセットアップした内容によって決まります。

   ![スタッフリストの UI の画像](../media/bookings-staff-list.png)

1. サービスの詳細情報 (日付、時刻、場所などの関連情報) を入力します。顧客の有効なメール アドレスを入力すると、[ **保存**] ボタンが [ **送信**] に変わり、確認が顧客に送信されるという注意が表示されます。顧客の確認には、予定表に追加する予定に関する添付ファイルも含まれます。選んだスタッフ メンバーにも、予定情報が記載された会議の招待が送信されるので、スタッフも自分の予定表に予定を追加できます。

1. [ **メール アラームを追加する**] を選びます。

1. アラームを送信する時期、送信場所 (**顧客**、 **スタッフ**、 **すべての出席者**)、およびアラームメッセージを指定します。

1. Select **Save** \> **Send**.

   お客様が受け取る通知のメールの例を次に示します。

:::image type="content" source="../media/bookings-confirmed-email.png" alt-text="スクリーンショット: 手動による予約からの確認メールの例":::