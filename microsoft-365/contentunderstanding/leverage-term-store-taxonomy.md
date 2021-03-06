---
title: 抽出子の作成時に用語ストアの分類を活用する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Microsoft SharePoint Syntex のドキュメント理解モデルで抽出子を作成するときに、用語ストアの分類法を活用します。
ms.openlocfilehash: 0008dd02ef46401e9f0c9414b8363cff034c18eb
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087323"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>抽出子の作成時に用語ストアの分類を活用する

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>


SharePoint Syntex のドキュメント理解モデルで抽出子を作成する場合、[マネージド メタデータ サービス](https://docs.microsoft.com/sharepoint/managed-metadata#terms)の用語ストア分類を利用して、抽出するデータの優先用語を表示できます。  

例として、モデルは、ドキュメント ライブラリにアップロードされているすべての **契約** ドキュメントを識別して分類します。  さらに、モデルは各契約から **契約サービス** 値も抽出し、ライブラリ ビューの列に表示します。 契約内のさまざまな契約サービス値の中には、会社が使用しなくなって名前が変更された古い値がいくつかあります。 たとえば、契約サービスでの *Design*、*Graphics*、*Topography* という用語への参照はすべて、*Creative* と呼ばれる必要があります。 モデルが契約ドキュメントから過去の条件の 1 つを抽出するときは必ず、ライブラリ ビューに現在の条件 (Creative) を表示する必要があります。 以下の例では、モデルのトレーニング中に、1 つのサンプル ドキュメントに古い用語である *Design* が含まれていることがわかります。

   ![用語ストア](../media/content-understanding/design.png)</br>


## <a name="use-a-managed-metadata-column-in-your-extractor"></a>抽出子で管理されたメタデータ列を使用する

用語セットは、SharePoint 管理センターの 管理されたメタデータ サービス 用語ストアで構成されます。 以下の例では、*契約サービス* の [用語セット](https://docs.microsoft.com/sharepoint/managed-metadata#term-set)は、*Creative* などのいくつかの用語を含むように構成されています。  詳細は、この用語に 3 つの同義語 (*Design*、*Graphics*、*Topography*) があり、これらの同義語を *Creative* に翻訳する必要があることを示しています。 

   ![用語セット](../media/content-understanding/term-store.png)</br>

用語セットで同義語を使用する理由はいくつか考えられます。 たとえば、古い用語、名前が変更された用語、または名前付けに関する組織部門間のバリエーションがある可能性があります。

モデルで抽出子を作成するときに管理メタデータ フィールドを選択できるようにするには、それを[管理メタデータ サイト列として追加する](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f)必要があります。 サイト列を追加すると、モデルの抽出子を作成するときに選択できるようになります。

   ![契約サービス](../media/content-understanding/contract-services.png)</br>


モデルをドキュメント ライブラリに適用した後、ドキュメントがライブラリにアップロードされると、抽出子が同義語の値 (*Design*、*Graphics*、*Topography*) のいずれかを検出すると、*Creative Services* 列に優先用語 (*Creative*) が表示されます。

   ![契約サービス列](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>関連項目
[管理されたメタデータの概要](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[抽出子を作成する](create-an-extractor.md)

[管理メタデータ列を作成する](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





