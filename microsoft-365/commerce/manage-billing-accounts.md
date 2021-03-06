---
title: 請求アカウントを管理する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: 課金アカウントとそれらを管理する方法について説明します。
ms.openlocfilehash: 3c99f3f22fb0eb13c4f9cab06a4037fe057b6fb4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638209"
---
# <a name="manage-billing-accounts"></a>請求アカウントを管理する

Microsoft 製品を試用または購入するためにサインアップするときに、課金アカウントが作成されます。 課金アカウントを使用して、アカウント設定、請求書、支払い方法、購入を管理します。 複数の課金アカウントにアクセスできます。 たとえば、Microsoft 365 に直接サインアップしたか、組織のエンタープライズアグリーメント、Microsoft Product & サービス契約、または Microsoft カスタマーアグリーメントへのアクセス権を持っている場合があります。 これらの各シナリオでは、別の課金アカウントが用意されています。

現在、Microsoft 365 管理センターは、次の種類の課金アカウントをサポートしています。

- Microsoft Online Services プログラム: この課金アカウントは、Microsoft 365 サブスクリプションに直接サインアップするときに作成されます。
- Microsoft 製品 & サービス契約 (MPSA) プログラム: この課金アカウントは、組織がソフトウェアとオンラインサービスを購入するために、MPSA ボリュームライセンス契約にサインしたときに作成されます。
- Microsoft カスタマーアグリーメント: この課金アカウントは、組織が Microsoft の担当者、認定パートナー、または個別に購入したときに作成されます。

[ <a href="https://go.microsoft.com/fwlink/p/?linkid=2084771" target="_blank">課金アカウント</a> ] ページには、Microsoft とのコマーシャルアカウントが表示されます。 既定では、組織には、直接購入の際に許可される、またはボリュームライセンスの構成によって承認される、少なくとも1つの請求アカウントがあります。

## <a name="understand-billing-account-details"></a>課金アカウントの詳細を理解する

[ **課金アカウント** の詳細] ページの一番上には、アカウントのプロファイルが表示され、組織に関する法的情報と税金の情報が含まれています。 自分のプロファイルを更新して、有効な住所と電話番号を変更することができます。 このアカウントは、購入した製品に対して支払われる法人です。

次の表に、[ **課金アカウント** の詳細] ページに表示される重要な用語を示します。

| フィールド名 | 説明 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 販売先住所 | 支払いを担当し、請求書で識別される法人。 ここで指定した住所は、購入時に代替配送先住所を提供することを選択しない限り、税率を決定するために使用されます。 詳細については、「 [税務情報](billing-and-payments/tax-information.md)」を参照してください。 |
| セグメント | 組織のビジネスセグメント (商用、教育、官公庁、または非営利) を識別する読み取り専用フィールド。 |
| アカウントの状態 | Microsoft とのコマーシャルアカウントの状態を指定する読み取り専用フィールド。 |
| 納税者番号 | 米国外の場合は、VAT またはローカルで同等のものを提供する必要があります。 詳細については、「 [税務情報](billing-and-payments/tax-information.md)」を参照してください。 |
| 保証 | 直接購入またはボリュームライセンスの組み合わせによって請求先アカウントを作成すると、組織の署名者は、アカウントの & 条件について概説する契約を承諾または署名します。 該当する場合、このビューにはアグリーメント履歴が一覧表示されます。 更新された条項に同意する必要がある場合は、[ **契約書の承認** ] リンクが表示されます。 |
| 課金プロファイル | 請求プロファイルでは、請求書を受け取ったユーザー、請求書の配送方法、支払い条件、PO 番号など、請求書のプロパティを定義します。 組織全体で請求書を配布するために、複数の課金プロファイルを作成し、購入時に適切な課金プロファイルを識別することができます。 請求プロファイルの詳細、およびそれらを使用して組織にとってより柔軟な請求オプションを作成する方法については、 [請求プロファイルを管理](billing-and-payments/manage-billing-profiles.md)してください。 |

> [!NOTE]
> **販売先**の名前または住所を変更する必要があり、**編集**リンクが表示されていない場合は、その変更につい[てサポートに連絡](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)する必要があります。 **販売先から名前へ**の変更の要求には、与信審査が必要です。 サポートに連絡する際には、次のいずれかのドキュメントの準備が整っている必要があります。
>
> - 会社名または企業構造の変化を示す外部アナウンスドキュメント
> - 官庁発行のドキュメントまたは登録レター
> - ローカル会社のレジストリから出力します。
>
> サポートは、顧客名のみが変更された変更を名前とアドレスに提供するのに役立ちますが、エンティティは変わりません。 提供されたドキュメントは、エンティティの名前のみが変更されたことを明確に示す必要があります。 販売のような取引、取引先の事業または "spinoff" のような変更が加えられている場合は、Microsoft 販売者にお問い合わせください。

## <a name="shipping-addresses"></a>配送先住所

このセクションでは、請求先アカウントに関連付けられている送付先住所を一覧表示します。 購入時に、この住所を使用して、購入先または使用されている場所を識別できます。 配送先住所は編集できます。 配送先住所を追加したり、既存の住所を更新したりすることができます。 この住所は、購入の税率を決定するために使用されます。

## <a name="understand-access-to-billing-accounts"></a>課金アカウントへのアクセスについて

役割とアクセス許可を通じて、他のユーザーに Microsoft 365 管理センターの課金アカウントへのアクセス権を与えることができます。 課金アカウントの所有者のみが課金アカウントへのアクセス権を付与できます。 ユーザーには、次のいずれかのロールを割り当てることができます。

- **課金アカウントの所有者** &mdash; アクセス許可の割り当て、アカウントの編集、アグリーメントの署名、およびアカウントの表示を行うことができます。
- **課金アカウントの共同作成者** &mdash; アカウントの編集、契約の署名、アカウントの表示を行うことができます。
- **課金アカウントのリーダー** &mdash; アカウントを表示できます。

> [!Note]
> 課金アカウントの役割は課金アカウントにのみ適用され、その他の Microsoft 365 管理センターのシナリオには適用されません。

## <a name="related-articles"></a>関連記事

[税金情報](billing-and-payments/tax-information.md)

[課金プロフィールを管理する](billing-and-payments/manage-billing-profiles.md)