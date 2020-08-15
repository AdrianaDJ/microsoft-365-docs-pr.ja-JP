---
title: 複数地域環境における SharePoint ストレージ クォータ
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: 複数地域環境での SharePoint のストレージクォータと、SharePoint Online 管理者がクォータを管理する方法について説明します。
ms.openlocfilehash: ec736a6bd6061f8b028fca7a1c34d5278a84db89
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692242"
---
# <a name="sharepoint-storage-quotas-in-multi-geo-environments"></a><span data-ttu-id="a3299-103">複数地域環境における SharePoint ストレージ クォータ</span><span class="sxs-lookup"><span data-stu-id="a3299-103">SharePoint storage quotas in multi-geo environments</span></span>

<span data-ttu-id="a3299-104">既定では、複数地域環境のすべての地域の場所では、使用できるテナントのストレージ クォータを共有します。</span><span class="sxs-lookup"><span data-stu-id="a3299-104">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>

<span data-ttu-id="a3299-105">SharePoint 地域ストレージ クォータ設定では、地域の場所ごとにストレージ クォータを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a3299-105">With the SharePoint geo storage quota setting, you can manage the storage quota for each geo location.</span></span> <span data-ttu-id="a3299-106">地域の場所のストレージ クォータを割り当てると、それがその地域の場所に使用可能な最大ストレージ容量になり、使用可能なテナント ストレージ クォータから差し引かれます。</span><span class="sxs-lookup"><span data-stu-id="a3299-106">When you allocate a storage quota for a geo location, it becomes the maximum amount of storage available for that geo location, and is deducted from the available tenant storage quota.</span></span> <span data-ttu-id="a3299-107">残りの利用可能なテナント ストレージ クォータは、特定のストレージ クォータが割り当てられていない構成済みの地域の場所間で共有されます。</span><span class="sxs-lookup"><span data-stu-id="a3299-107">The remaining available tenant storage quota is then shared across the configured geo locations for which a specific storage quota has not been allocated.</span></span>

<span data-ttu-id="a3299-108">地域の場所に対する SharePoint ストレージ クォータは、SharePoint Online 管理者が中央の場所に接続することによって割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a3299-108">The SharePoint storage quota for any geo location can be allocated by the SharePoint Online administrator by connecting to the central location.</span></span> <span data-ttu-id="a3299-109">サテライトの場所の地域管理者は、ストレージ クォータを表示できますが、割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="a3299-109">Geo administrators for satellite locations can view the storage quota but cannot allocate it.</span></span>

## <a name="configure-a-storage-quota-for-a-geo-location"></a><span data-ttu-id="a3299-110">地域の場所のストレージ クォータを構成する</span><span class="sxs-lookup"><span data-stu-id="a3299-110">Configure a storage quota for a geo location</span></span>

<span data-ttu-id="a3299-111">地域の場所にストレージ クォータを割り当てるには、[Microsoft Office SharePoint Online モジュール](https://www.microsoft.com/download/details.aspx?id=35588 )を使用して、中央の場所に接続します。</span><span class="sxs-lookup"><span data-stu-id="a3299-111">Use the [Microsoft SharePoint Online Module](https://www.microsoft.com/download/details.aspx?id=35588 ) and connect to the central location to allocate the storage quota for a geo location.</span></span> 

<span data-ttu-id="a3299-112">場所にストレージ クォータを割り当てるには、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="a3299-112">To allocate Storage Quota for a location, run cmdlet:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB <value>`

<span data-ttu-id="a3299-113">現在の地域の場所に対するストレージ クォータを表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3299-113">To view Storage Quota for the current geo location, run:</span></span>

`Get-SPOGeoStorageQuota`

![Get-SPOGeoStorageQuota コマンドレットを表示している PowerShell ウィンドウのスクリーンショット](../media/multi-geo-storage-quota.png)

<span data-ttu-id="a3299-115">すべての地域の場所に対するストレージ クォータを表示するには、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3299-115">To view Storage Quota for all geo locations, run:</span></span>

`Get-SPOGeoStorageQuota -AllLocations`

<span data-ttu-id="a3299-116">地域の場所の割り当てられたストレージ クォータを削除するには、`StorageQuota value = 0` を設定します。</span><span class="sxs-lookup"><span data-stu-id="a3299-116">To remove the allocated storage quota for a geo location, set `StorageQuota value = 0`:</span></span>

`Set-SPOGeoStorageQuota -GeoLocation <geolocationcode> -StorageQuotaMB 0`