---
title: 高度な検索 Api
description: Microsoft の脅威保護 API を使用して高度な検索クエリを実行する方法について説明します。
keywords: 高度な検索、Api、api、MTP
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 92d5d2840963ae00ae0f03e3359f287371f770ee
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650426"
---
# <a name="advanced-hunting-apis"></a>高度な検索 Api

**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="limitations"></a>制限事項
1. クエリは、過去30日間のデータに対してのみ実行できます。
2. 結果には最大10万行が含まれます。
3. 実行回数は、テナントごとに制限されます。1分あたり最大15件の通話、稼働時間は1時間ごとに15分、稼働時間は1日に4時間。
4. 1回の要求の最大実行時間は10分です。

## <a name="permissions"></a>アクセス許可
この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法を含む詳細については、「 [Microsoft の脅威保護 api にアクセス](api-access.md)する」を参照してください。

アクセス許可の種類 |   アクセス許可  |   アクセス許可の表示名
:---|:---|:---
アプリケーション |   AdvancedHunting |  [高度なクエリを実行する]
委任 (職場または学校のアカウント) | AdvancedHunting | [高度なクエリを実行する]

>[!Note]
> ユーザー資格情報を使用してトークンを取得する場合:
>- ユーザーは ' View Data ' AD の役割を持っている必要があります。
>- ユーザーはデバイスグループの設定に基づいて、デバイスへのアクセス権を持っている必要があります。

## <a name="http-request"></a>HTTP 要求
```
POST https://api.security.microsoft.com/api/advancedhunting/run
```

## <a name="request-headers"></a>要求ヘッダー

ヘッダー | 値 
:---|:---
Authorization | ベアラー {token}。 **必須**。
Content-Type    | application/json

## <a name="request-body"></a>要求本文
要求本文で、次のパラメーターを使用して JSON オブジェクトを指定します。

パラメーター | 種類    | 説明
:---|:---|:---
クエリ | テキスト |  実行するクエリを示します。 **必須**。

## <a name="response"></a>応答
成功した場合、このメソッドは 200 OK を返し、応答本文で _Queryresponse_ オブジェクトを返します。 <br><br>

Response オブジェクトは3つの部分 (プロパティ) に分かれています。<br>
1) ```Stats``` -クエリパフォーマンス統計。<br>
2) ```Schema``` -応答のスキーマ。各列の名前の種類のペアのリスト。 <br>
3) ```Results``` -高度な検索イベントのリスト。

## <a name="example"></a>例

要求

以下は、要求の例です。


```json
{
    "Query":"DeviceProcessEvents | where InitiatingProcessFileName =~ \"powershell.exe\" | project Timestamp, FileName, InitiatingProcessFileName | order by Timestamp desc | limit 2"
}

```

応答

以下は、応答の例です。


```json
{
    "Stats": {
        "ExecutionTime": 4.621215,
        "resource_usage": {
            "cache": {
                "memory": {
                    "hits": 773461,
                    "misses": 4481,
                    "total": 777942
                },
                "disk": {
                    "hits": 994,
                    "misses": 197,
                    "total": 1191
                }
            },
            "cpu": {
                "user": "00:00:19.0468750",
                "kernel": "00:00:00.0156250",
                "total cpu": "00:00:19.0625000"
            },
            "memory": {
                "peak_per_node": 236822432
            }
        },
        "dataset_statistics": [
            {
                "table_row_count": 2,
                "table_size": 102
            }
        ]
    },
    "Schema": [
        {
            "Name": "Timestamp",
            "Type": "DateTime"
        },
        {
            "Name": "FileName",
            "Type": "String"
        },
        {
            "Name": "InitiatingProcessFileName",
            "Type": "String"
        }
    ],
    "Results": [
        {
            "Timestamp": "2020-08-30T06:38:35.7664356Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        },
        {
            "Timestamp": "2020-08-30T06:38:30.5163363Z",
            "FileName": "conhost.exe",
            "InitiatingProcessFileName": "powershell.exe"
        }
    ]
}

```

## <a name="related-topic"></a>関連トピック
- [Microsoft の脅威保護 Api にアクセスする](api-access.md)