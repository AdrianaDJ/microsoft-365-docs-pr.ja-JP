---
title: Microsoft 365 Defender の AIR の誤検知または誤検知を処理する
description: Microsoft 365 Defender で、何らかの問題があるか、またはエアで誤って検出されましたか? 分析のために誤検知または誤検知を Microsoft に送信する方法について説明します。
keywords: 自動化、調査、警告、トリガー、アクション、修復、誤検知、false 負
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 92ad4a96665a5355bce7e3546f8c52779f770927
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843734"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>自動調査と応答機能で誤検知/否定を処理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

Microsoft 365 Defender ミスの [自動調査および応答機能](mtp-autoir.md) があったかどうか、または誤って検出されたのでしょうか? この問題を解決するには、以下の手順を実行します。 次の操作を行うことができます:

- [False 正/負の値を Microsoft に報告し](#report-a-false-positivenegative-to-microsoft-for-analysis)ます。

- [通知を調整し](#adjust-an-alert-to-prevent-false-positives-from-recurring) ます (必要な場合)。そして 

- [デバイスに対して実行された修復操作を元に戻し](#undo-a-remediation-action-that-was-taken-on-a-device)ます。 

この記事をガイドとして使用します。 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>False 正/負の値を分析のために Microsoft に報告する

|不在時または誤って検出されたアイテム |サービス  |操作  |
|---------|---------|---------|
|-電子メールメッセージ <br/>-電子メールの添付ファイル <br/>-電子メールメッセージ内の URL<br/>-Office ファイル内の URL      |[Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[迷惑メールの疑い、フィッシング、Url、およびファイルをスキャン用に Microsoft に送信する](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|デバイス上のファイルまたはアプリ    |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)         |[マルウェア分析のために Microsoft にファイルを提出する](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>警告を調整して誤検知が繰り返されないようにする

|シナリオ |サービス |操作 |
|--------|--------|--------|
|-警告が正規の使用によってトリガーされる <br/>-警告が正確でない    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> または <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Cloud App Security ポータルで通知を管理する](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|ファイル、IP アドレス、URL、またはドメインが安全であっても、デバイスのマルウェアとして扱われる|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) |["許可" アクションを含むカスタムインジケーターを作成する](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>デバイスで実行された修復アクションを元に戻す

修復アクションがデバイス (Windows 10 デバイスなど) に対して実行され、そのアイテムが実際には脅威ではない場合、セキュリティ操作チームは [アクションセンター](mtp-action-center.md)の修復アクションを取り消すことができます。

> [!IMPORTANT]
> 次のタスクを実行する前に、 [必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks) があることを確認してください。

1. [https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。 

2. ナビゲーション ウィンドウで、[ **アクション センター** ] を選択します。 

3. [ **履歴** ] タブで、元に戻す操作を選択します。 これにより、フライアウトが開きます。<br/>
    > [!TIP]
    > フィルターを使用して、結果の一覧を絞り込みます。 

4. 選択したアイテムのポップアップで、[ **調査ページを開く** ] を選択します。

5. 調査の詳細ビューで、[ **操作** ] タブを選択します。

6. 状態が [ **完了** ] であるアイテムを選択し、[ **判断** ] 列に [ **承認済み** ] などのリンクを探します。 これにより、アクションの詳細を含むフライアウトが開きます。

7. アクションを元に戻すには、[ **修復の削除** ] を選択します。

## <a name="see-also"></a>関連項目

- [自動調査の詳細と結果を表示する](mtp-autoir-results.md)
- [Microsoft 365 Defender での高度な検索を使用して、積極的に脅威を探します。](advanced-hunting-overview.md)
