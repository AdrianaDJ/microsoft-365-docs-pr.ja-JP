---
title: Microsoft Bookings でバッファー時間を設定する
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Microsoft 予約の予定の前または後にバッファー時間を設定して、機器のクリーンアップまたはリセットの時間を確保します。
ms.openlocfilehash: dceb777f9ddba9f1ddabfee00608813afae57a86
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419833"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Microsoft Bookings でバッファー時間を設定する

一部の予定には、お客様が会議室や備品をセットアップ、クリーンアップ、またはリセットするための時間が必要になる場合があります。 また、お客様の予定間で出張している場合は、お客様がお客様を待たずに予定間を移動できるようにするための時間が必要になることがあります。

定期的な予定の開始、予定の終了後、またはその両方を設定して、次の予定を準備するのに必要な時間をスタッフに与えることができます。

> [!NOTE]
> 予約は、Microsoft 365 Business Standard、Microsoft 365 A3、または Microsoft 365 A5 サブスクリプションを使用しているお客様に対して、既定でオンになっています。 予約は、Office 365 Enterprise E3 および Office 365 Enterprise E5 を持つお客様も利用できますが、既定ではオフになっています。 開始するには、「 [Microsoft 予約へのアクセスを取得](get-access.md)する」を参照してください。 予約をオンまたはオフにするには、「 [組織の予約を有効または無効](turn-bookings-on-or-off.md)にする」を参照してください。

## <a name="set-buffer-time-defaults"></a>バッファー時間の既定値の設定

バッファー時間の既定値は、[予約] の [ **サービスの詳細** ] ページで設定します。 このページに設定されているすべてのサービスの既定値と同様に、特定のお客様のニーズを満たす特定の予約に対して、これらの既定値を編集することができます。

バッファー時間の設定は、[**サービスの詳細**] ページの**既定の期間**選択のすぐ下にあります。 特定のサービスに設定する前に、バッファー時間の切り替えを選択することによって、バッファー時間の設定を有効にする必要があります。 これにより、次のように、各予約の前後に保持する既定の時間を選択するために使用さ**れるドロップダウン**の**前後**が表示されます。

   ![バッファー時間が有効な予約の画像](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>バッファー時間と予定タイミング

お客様との打ち合わせに関して混乱を避けるため、予約には、予定表のバッファー時間と実際の予定時間 (お客様が自分に会う時間) と、関連するスタッフへの電子メールの確認や事前通知が表示されます。 たとえば、次に示すのは、予定に対して予約されている予定のうち、予定が15分前のバッファー時間を含む顧客との予定です。

このイベント自体 (下の図の左側) には、実際のお客様の予定に対するバッファー時間と暗い網掛けの薄い網かけが表示されていることに注意してください。 予定の呼び出しアウト (イベントを選択したときに開かれます) は、特に、予定が 9: 00AM から 10: 00AM (Katie ヨルダン) になっていることを示し、予定の前に15分のバッファー時間を指定します。 スタッフへの確認と事前通知同様に、特定のバッファーおよび予定時間を参照します。顧客は、9: 00AM ~ 10: 00AM の予定時間を参照しているものだけを取得します。

   ![時間が表示された予約済みの会議の画像](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>バッファー時間と空き時間

お客様には、設定したバッファー時間は直接表示されず、変更もできません。 ただし、バッファー時間はサービス全体の期間を計算するために使用されるため、バッファーと定期的な予定時間の両方で、お客様と関連するスタッフが予約されています。 また、予定とバッファー時間の両方に十分な時間がある場合は、お客様とスタッフに対してのみ可用性が表示されます。

例として、15分前の予定のバッファー時間を持つ1時間の予定には、少なくとも1時間と15分の使用可能な時間帯が必要です。 そのため、このサービスの予定では、予定表に75分の時間ブロックが入力され、競合することなく、ブックを75分の可用性が必要になります。