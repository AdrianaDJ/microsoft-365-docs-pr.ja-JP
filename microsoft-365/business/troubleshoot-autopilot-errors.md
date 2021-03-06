---
title: AutoPilot デバイス エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Microsoft 365 Business Premium で自動操縦デバイスファイルを操作するときに表示される可能性のあるエラーのトラブルシューティング方法について説明します。
ms.openlocfilehash: bec5126696ee322db42e4b7c5cd8e0df485ab2c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403412"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot デバイス エラーのトラブルシューティング

## <a name="device-file-error-messages"></a>デバイスファイルのエラーメッセージ

ここでは、Microsoft 365 Business Premium で自動操縦デバイスファイルを処理するときに表示される可能性のあるエラーについて説明します。 
  
|**エラー コード**|**解決策を実行する**|
|:-----|:-----|
|無効な要求本文  <br/> |このエラーが発生することはまれです。このエラーが表示された場合は、操作を再試行してください。  <br/> |
|デバイスのハードウェアハッシュ値が正しくありません。  <br/> |このエラーが表示される場合は、1つのデバイスのハードウェアハッシュで CSV ファイルに指定した値が正しくないことを意味します。 最初に、値が正しく入力されたことを確認します。 値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。  <br/> |
|別のテナントに割り当てられたデバイス  <br/> |このエラーが表示される場合は、1つまたは複数のデバイスのシリアル番号またはプロダクトキーで CSV ファイルに指定した値が正しくないことを意味します。 最初に、値が正しく入力されたことを確認します。 値が正しいと考えられるが、このエラーがまだ発生している場合は、ハードウェアベンダーにお問い合わせください。  <br/> |
|CSV ファイルに無効なシリアル番号またはプロダクトキーが含まれています  <br/> |このエラーが表示される場合は、登録しようとしているデバイスが別の組織によって既に登録されていることを意味します。 このエラーを解決するには、ハードウェアベンダーにお問い合わせください。  <br/> |
|このデバイスは自動操縦を使用したセットアップではサポートされていません  <br/> | このエラーは、デバイスが自動操縦展開の要件を満たしていないことを意味します。 デバイスは次の要件を満たしている必要があります。  <br/>  Windows 10 バージョン 1703 以降。  <br/>  Windows の標準外の機能を使用していない新しいデバイス。  <br/> |
|デバイスが見つかりません  <br/> |このエラーは、CSV ファイル内の1つ以上のデバイスが組織に登録されていないことを意味します。 この問題を解決するには、ハードウェアベンダーにお問い合わせください。  <br/> |
