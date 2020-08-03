---
title: セキュリティポリシーの構成アナライザー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、構成アナライザーを使用して、標準保護と厳格な保護の事前設定セキュリティポリシーの下にある設定を含むセキュリティポリシーを検索して修正する方法を学習できます。
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533991"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>EOP および Office 365 ATP の保護ポリシーの構成アナライザー

> [!NOTE]
> このトピックで説明する機能はプレビュー段階にあり、組織によっては使用できず、変更される可能性があります。

セキュリティ & コンプライアンスセンターの構成アナライザーでは、[既定のセキュリティポリシー](preset-security-policies.md)の標準保護と厳密な保護プロファイル設定の下にある設定を含む、セキュリティポリシーのいずれかを検索して修正するための一元的な場所が提供されます。

次の種類のポリシーが、構成アナライザーによって分析されます。

- **Exchange Online Protection (EOP) ポリシー**: これには、exchange online メールボックスを使用する Microsoft 365 組織と、exchange online メールボックスを持たないスタンドアロン EOP 組織が含まれます。
  
  - [スパム対策ポリシー](configure-your-spam-filter-policies.md)。
  - [マルウェア対策ポリシー](configure-anti-malware-policies.md)。
  - [EOP フィッシング対策ポリシー](set-up-anti-phishing-policies.md#spoof-settings)。

- **Office 365 Advanced Threat Protection (ATP) ポリシー**: これには、Microsoft 365 E5 または OFFICE 365 ATP アドオンサブスクリプションを使用する組織が含まれます。

  - ATP のフィッシング対策ポリシーには、次のものが含まれます。

    - EOP のフィッシング対策ポリシーで使用可能なものと同じ[スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)。
    - [偽装設定](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [高度なフィッシングしきい値](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - 「[安全なリンク」ポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)。

  - [安全な添付ファイルのポリシー](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)。

ベースラインとして使用される**標準**および**厳密**なポリシー設定値については、「 [EOP and Office 365 ATP security の推奨設定](recommended-settings-for-eop-and-office365-atp.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 [**構成アナライザー** ] ページに直接移動するには、を使用 <https://protection.office.com/configurationAnalyzer> します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 構成アナライザーを使用**して**セキュリティポリシーを更新するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 構成アナライザーへの読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターで構成アナライザーを使用する

[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **構成アナライザー**] に移動します。

![[脅威管理ポリシー] ページの [構成アナライザー] ウィジェット \>](../../media/configuration-analyzer-widget.png)

構成アナライザーには、次の2つの主要なタブがあります。

- **設定と推奨事項**: Standard または Strict を選択し、それらの設定を既存のセキュリティポリシーと比較します。 結果では、設定の値を調整して、Standard または Strict と同じレベルにすることができます。

- **構成ドリフトの分析と履歴**: このビューでは、構成アナライザーの結果に基づいて、ポリシーに加えた変更を追跡できます。

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>構成アナライザーの [設定] タブと [おすすめ候補] タブ

既定では、タブは標準の保護プロファイルと比較して開きます。 厳密保護プロファイルの比較に切り替えるには、[厳密な**推奨事項の表示**] をクリックします。 元に戻すには、[**標準的な推奨事項を表示**する] を選択します。

![構成アナライザーの [設定と推奨事項] ビュー](../../media/configuration-analyzer-settings-and-recommendations-view.png)

既定では、[**ポリシーグループ/設定名**] 列には、さまざまな種類のセキュリティポリシーの折りたたまれたビューと、改善を必要とするポリシーの設定数 (存在する場合) が含まれています。 ポリシーの種類は次のとおりです。

- **スパム対策**
- **フィッシング対策**
- **マルウェア対策**
- **Atp の安全な添付ファイル**(サブスクリプションに atp が含まれている場合)
- **Atp の安全なリンク**(サブスクリプションに atp が含まれている場合)

既定のビューでは、すべてが折りたたまれています。 各ポリシーの横に、ポリシーからの比較結果 (変更可能) と、標準または厳密な保護プロファイルの対応するポリシーの設定 (変更不可) が表示されます。 次の情報が表示されます。

- **緑**: すべての既存ポリシーのすべての設定は、少なくとも、比較対象の保護プロファイルと同じようにセキュリティで保護されています。
- **オレンジ**: 既存のポリシーで設定されている設定の数が少ないため、比較している保護プロファイルほど安全ではありません。
- **赤**: 既存のポリシーの設定の多くは、比較している保護プロファイルほど安全ではありません。 これは、多くのポリシーの設定のいくつか、または1つのポリシーの多くの設定の場合があります。

好ましい比較には、次のテキストが表示されます。**すべての設定**は \<**Standard** or **Strict**\> **推奨事項**に従います。 そうしないと、変更する推奨設定の数が表示されます。

[**ポリシーグループ]/[設定名**] を展開すると、アテンションを必要とする特定の各ポリシーのすべてのポリシーと関連付けられた設定が表示されます。 または、特定の種類のポリシー (**スパム対策**など) を拡張して、注意が必要な種類のポリシーの設定のみを表示することもできます。

比較に改善に関する推奨策 (緑色) がない場合は、ポリシーを拡張しても何も示されません。 改善に関していくつかの推奨事項 (黄色または赤) がある場合は、注意を要する設定が表示され、対応する情報が次の列に表示されます。

- 注意が必要な設定の名前。 たとえば、前のスクリーンショットでは、スパム対策ポリシーの**バルクメールのしきい値**です。

- **Policy**: 設定を含む影響を受けるポリシーの名前。

- **適用**対象: 影響を受けたポリシーが適用されるユーザーの数。

- **現在の構成**: 設定の現在の値。

- **最終更新**日: ポリシーが最後に変更された日付。

- **推奨事項**: 標準または厳密な保護プロファイルの設定値。 ポリシーの設定の値を、保護プロファイルの推奨値と一致するように変更するには、[**採用**] をクリックします。 変更に成功すると、「**推奨事項**」というメッセージが表示されます。 [**更新**] をクリックして、推奨数の削減、および結果からの特定の設定/ポリシー行の削除を確認します。

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>構成アナライザーの [構成誤差の分析と履歴] タブ

このタブでは、セキュリティアナライザーの情報に基づいてカスタムセキュリティポリシーに加えた変更を追跡できます。 既定では、次の情報が表示されます。

- **最終更新日時**
- **更新者**
- **設定名**
- **ポリシー**
- **Type**

結果をフィルター処理するには、**[フィルター]** をクリックします。 表示される [**フィルター** ] ポップアップでは、次のフィルターから選択できます。

- **開始**時刻と**終了時刻**(date)
- **標準保護**または**厳密な保護**

結果を .csv ファイルにエクスポートするには、[**エクスポート**] をクリックします。

![構成アナライザーの構成誤差分析と履歴ビュー](../../media/configuration-analyzer-configuration-drift-analysis-view.png)