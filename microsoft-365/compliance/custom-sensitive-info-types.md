---
title: DLP 用のカスタムの機密情報の種類
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 主なパターン、英数字、信頼度など、データ損失防止 (DLP) のカスタム機密情報の種類の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e414d9a31869e9b1382f0713d6d70df745c41471
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681765"
---
# <a name="custom-sensitive-information-types"></a>カスタムの機密情報の種類

Microsoft 365 には機密情報の種類が多数組み込まれており、[データ損失防止](data-loss-prevention-policies.md) (DLP)、あるいは [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) 用に組織内で使用することができます。 組み込まれている機密情報の種類は、クレジットカード番号、銀行口座番号、パスポート番号などを特定して保護するのに役立ちます。これらの情報の特定と保護は、正規表現 (regex) または関数によって定義されたパターンに基づいて行われます。 詳細については、「[機密情報の種類で検索される情報](what-the-sensitive-information-types-look-for.md)」を参照してください。

ただし、組織固有の形式で、異なる機密情報の種類 (従業員 ID やプロジェクト番号など) を特定して保護する必要がある場合は、 カスタムの機密情報の種類を作成することができます。

カスタムの機密情報の種類の基本的な部分は次のとおりです。

- **プライマリ パターン**: 従業員 ID 番号、プロジェクト番号など。これは通常、正規表現 (RegEx) によって識別されますが、キーワード リストにもできます。

- **追加の証拠**: 9 桁の従業員 ID 番号を探していると仮定します。9 桁の数字がすべて従業員 ID 番号ではないので、「従業員」、「社員証」、「ID」などのキーワードや追加の正規表現を基にして、別のテキスト パターンを検索できます。この補強証拠 (_補強_または_裏付け_証拠とも呼ばれる) は、コンテンツに含まれる 9 桁の数字が実際に従業員 ID 番号である可能性を高めます。

- **文字の近接**: プライマリ パターンと補強証拠が互いに近いほど、検出されたコンテンツが探しているものになる可能性が高くなります。次の図に示すように、プライマリ パターンと補強証拠との文字の距離 (_近接ウィンドウ_とも呼ばれる) を指定できます。

    ![補強証拠と近接ウィンドウの図](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **信頼レベル**: 持っている補強証拠が多ければ多いほど、探している機密情報と一致する可能性が高くなります。より多くの証拠を使用して検出された一致には、より高いレベルの信頼を割り当てることができます。

  パターンを満たす場合は、数と信頼度が返され、DLP ポリシーの条件に使用できます。機密情報の種類を検出する条件を DLP ポリシーに追加する場合、次の図に示すように、数と信頼度を編集できます。

    ![インスタンス数と一致精度オプション](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

次のオプションを使用して、セキュリティ/コンプライアンス センターでカスタムの機密情報の種類を作成できます。

- **EDM を使用する**データ一致 (EDM) に基づく分類によって、カスタム機密情報の種類を設定します。 この方法では、定期的に更新できる安全なデータベースを使用して、動的な機密情報の種類を作成することができます。 詳細については、「[Exact Data Match に基づく分類で、カスタムの機密情報の種類を作成する](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)」を参照してください。

- **PowerShell を使用する** PowerShell を使用して、カスタムの機密情報の種類を設定します。 この方法は、UI を使用する場合よりも複雑ですが、より多くの構成オプションがあります。 詳細については、「[セキュリティ/コンプライアンス センターの PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)」を参照してください。

- **UI を使用する** セキュリティ/コンプライアンス センターの UI を使用して、カスタムの機密情報の種類を設定します。 この方法では、正規表現、キーワード、キーワード辞書を使用することができます。 詳細については、「[カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」を参照してください。

> [!NOTE]
> Microsoft 365 の情報保護は、次のような場合に2バイト文字セットの言語をpreviewでサポートしています。
> - 中国語 (簡体字)
> - 中国語 (繁体字)
> - 韓国語
> - 日本語

>このサポートは、機密情報の種類で使用できます。 詳細については、「[2バイト文字セットのリリースノート (preview) についての情報保護サポー](mip-dbcs-relnotes.md)」を参照してください。

