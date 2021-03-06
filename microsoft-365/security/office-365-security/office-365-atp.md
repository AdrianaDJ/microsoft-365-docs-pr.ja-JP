---
title: Microsoft Defender for Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 には、安全な添付ファイル、安全なリンク、高度なフィッシング詐欺対策ツール、レポート ツール、および脅威インテリジェンス機能が含まれています。
ms.openlocfilehash: 11b6445e17fc870c2999ddb56715b0c5cee5b5fc
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357709"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) をご利用の法人のお客様を対象としています。 Outlook.com、Microsoft 365 Family、または Microsoft 365 Personal を使用していて、Outlook の安全なリンクまたは添付ファイルに関する情報を探している場合は、「[Microsoft 365 サブスクライバー用の Outlook.com の高度なセキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

Microsoft Defender for Office 365 は、電子メール メッセージ、リンク (URL) や共同作業ツールによって生じる悪意のある脅威から組織を保護します。 Defender for Office 365 には次のものが含まれます。

- **[脅威保護ポリシー](#configure-microsoft-defender-for-office-365-policies)**: 脅威保護ポリシーを定義して、組織に適切なレベルの保護を設定します。

- **[レポート](#view-microsoft-defender-for-office-365-reports)**: 組織の Defender for Office 365 パフォーマンスを監視するリアルタイム レポートを表示します。

- **[脅威の調査および反応機能](#use-threat-investigation-and-response-capabilities)**: 最先端のツールを使用して、脅威の調査、把握、シミュレーション、および回避を行います。

- **[自動調査および対応機能](office-365-air.md)**: 脅威の調査および軽減にかかる時間と労力を節約します。

## <a name="getting-started"></a>はじめに

Microsoft Defender for Office 365 を初めて使用している場合、または *実行しながら* 最適な方法を学ぶ場合は、この記事を参照しながら、初期 Defender for Office 365 構成をチャンクに分割し、調査し、レポートを表示することをお勧めします。 論理的な初期構成チャンクは次の通りです。

- 名前に "*対策*" を使用してすべてを構成します。
  - マルウェア対策
  - フィッシング詐欺対策
  - スパム対策
- 名前に "*安全*" を使用してすべてを設定します。
  - 安全なリンク
  - 安全な添付ファイル
- ワークロードを保護する (例: OSharePoint Online、OneDrive と Teams)
- ゼロアワー自動消去を使用して保護する

詳細については、 [このリンクをクリック](protect-against-threats.md)してください。

> [!NOTE]
> Microsoft Defender for Office 365 には、2 種類のプランがあります。 "リアルタイム検出" を使用している場合は **プラン 1** で、脅威エクスプローラーを使用している場合は **プラン 2** が表示されます。 このプランは、表示されるツールに影響しますので、お客様のプランについて理解していることをご確認ください。

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 プラン 1 およびプラン 2

次の表は、各プランに含まれる機能をまとめたものです。

****

|Microsoft Defender for Office 365 プラン 1|Microsoft Defender for Office 365 プラン 2|
|---|---|
|<br/>構成、保護、および検出機能: <ul><li>[添付ファイル保護](atp-safe-attachments.md)</li><li>[リンク保護](atp-safe-links.md)</li><li>[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 保護のフィッシング詐欺対策](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[リアルタイムの検出](threat-explorer.md)</li></ul>|Microsoft Defender for Office 365 プラン 1 機能<br/>--- プラスのもの ---<br/>自動化、調査、修復、教育の機能:</li><li>[脅威トラッカー](threat-trackers.md)</li><li>[脅威エクスプローラー](threat-explorer.md)</li><li>[自動調査および対応](office-365-air.md)</li><li>[攻撃シミュレータ](attack-simulator.md)</li></ul>|
|

- Microsoft Defender for Office 365 プラン 2 は、Office 365 E5、Office 365 A5、および Microsoft 365 E5 Security と Microsoft 365 E5 に含まれています。

- Microsoft Defender for Office 365 プラン 1 は、Microsoft 365 Business Premium に含まれています。

- Microsoft Defender for Office 365 プラン 1 および Microsoft Defender for Office 365 プラン 2 は、それぞれ特定のサブスクリプションのアドオンとして利用できます。 詳細については、「[Microsoft Defender for Office 365 プラン全体での機能の可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」を参照してください。

- [安全なドキュメント](safe-docs.md)機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティ ライセンス (Microsoft Defender for Office 365 プランには含まれません) を持つユーザーのみが利用できます。

- 現在のサブスクリプションに Microsoft Defender for Office 365 が含まれていない場合は、[販売員に連絡して試用版を開始](https://go.microsoft.com/fwlink/p/?LinkId=518644)し、Defender for Office 365 が組織でどのように機能するかを確認してください。

## <a name="configure-microsoft-defender-for-office-365-policies"></a>Microsoft Defender for Office 365 ポリシーを構成する

Microsoft Defender for Office 365 を使用して、組織のセキュリティ チームは、セキュリティ/コンプライアンス センターでポリシーを定義することにより、保護を構成できます ([https://protection.office.com](https://protection.office.com) > **脅威管理** > **ポリシー** に移動します)。

> [!TIP]
> 定義するポリシーの簡単なリストについては、「[脅威から保護する](protect-against-threats.md)」を参照してください。

## <a name="defender-for-office-365-policies"></a>Defender for Office 365 ポリシー

組織で定義されているポリシーにより、定義済み脅威に対する動作と保護レベルが決まります。 ポリシー オプションは、非常に柔軟です。 たとえば、組織のセキュリティ チームは、ユーザー、組織、受信者、ドメイン レベルで詳細に脅威保護を設定できます。 新しい脅威や課題が毎日出現するため、ポリシーを定期的に確認することが重要です。

- **[安全な添付ファイル機能](atp-safe-attachments.md)**: 悪意のあるコンテンツがないかどうかメールの添付ファイルを確認して、メッセージング システムを保護できるゼロデイ保護機能を提供します。 ウイルス/マルウェアの署名を持たないすべてのメッセージと添付ファイルを特別な環境にルートし、機械学習と分析技術を使用して悪意を検出します。 疑わしいアクティビティが見つからない場合、メッセージはメールボックスに転送されます。 詳細については、「[安全な添付ファイル ポリシーを設定する](set-up-atp-safe-attachments-policies.md)」を参照してください。

- **[安全なリンク](atp-safe-links.md)**: メール メッセージや Office ファイルなどで、URL をクリックした時に検証を行います。 保護は継続的に行われ、メッセージおよび Office 環境全体に適用されます。 クリックごとにリンクがスキャンされます。安全なリンクは常にアクセスでき、悪意のあるリンクは動的にブロックされます。 詳細については、「[安全なリンク ポリシーを設定する](set-up-atp-safe-links-policies.md)」をご覧ください。

- **[SharePoint、OneDrive、Microsoft Teams 用の ATP](atp-for-spo-odb-and-teams.md)**: チーム サイトやドキュメント ライブラリ内で悪意のあるファイルを特定してブロックすることで、ユーザーが共同作業でファイルを共有する際に組織を保護します。 詳細については、「[SharePoint、OneDrive、Microsoft の Defender for Office 365 を有効にする](turn-on-atp-for-spo-odb-and-teams.md)」を参照してください。

- **[Defender for Office 365 のフィッシング対策保護](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)**: ユーザー、内部およびカスタム ドメインの偽装を検出します。 この機能は、コンピューターの学習モデルや高度な偽装検出アルゴリズムを適用してフィッシング攻撃に回避します。 詳細については、「[Microsoft Defender for Office 365 のフィッシング詐欺対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。

## <a name="view-microsoft-defender-for-office-365-reports"></a>Microsoft Defender for Office 365 レポートを表示する

Microsoft Defender for Office 365 には、Defender for Office 365 パフォーマンスを監視するための高度な[レポート ダッシュボード](view-reports-for-atp.md)が含まれています。 アクセスするには、セキュリティ/コンプライアンス センターの [**レポート**]  >  [**ダッシュ ボード**] の順に移動します。

レポートはリアルタイムで更新され、最新の分析情報を提供します。 また、これらのレポートは推奨事項を提供し、間近に迫った脅威を警告します。 定義済みレポートには次のものが含まれます:

- [脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)

- [脅威保護の状態レポート](view-reports-for-atp.md#threat-protection-status-report)

- [Defender for Office 365 のファイル型レポート](view-reports-for-atp.md#defender-for-office-365-file-types-report)

- [Defender for Office 365 のメッセージ処理レポート](view-reports-for-atp.md#defender-for-office-365-message-disposition-report)

- レポートは、上記のもの以外にもいくつかあります。

## <a name="use-threat-investigation-and-response-capabilities"></a>脅威の調査および対応機能を使用する

Microsoft Defender for Office 365 プラン 2 には、組織のセキュリティ チームが悪意のある攻撃を予測、把握、および回避するために、クラス最高の[脅威の調査および対応のツール](office-365-ti.md)が含まれます。

- **[脅威トラッカー](threat-trackers.md)** は、一般的なサイバーセキュリティの問題に関する最新のインテリジェンスを提供します。 たとえば、最新のマルウェアに関する情報を表示し、組織に対する実際の脅威になる前に対策を講じることができます。 使用可能な脅威トラッカーには、[[注目のトラッカー](threat-trackers.md#noteworthy-trackers)]、[[急上昇中のトラッカー](threat-trackers.md#trending-trackers)]、[[追跡されたクエリ](threat-trackers.md#tracked-queries)]、[[保存されたクエリ](threat-trackers.md#saved-queries)] があります。

- **[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)** (エクスプローラーとも呼ばれます) は、最近発生した脅威を特定して分析できるリアルタイムのレポートです。 カスタム期間のデータを表示するようにエクスプローラーを構成することができます。

- **[攻撃シミュレータ](attack-simulator.md)** を使用すると、現実的な攻撃シナリオを組織で実行して、脆弱性を特定することができます。 スピア フィッシング資格情報獲得と添付ファイルの攻撃、パスワード スプレーとブルート フォース パスワード攻撃など、現在の種類の攻撃のシミュレーションを利用できます。

## <a name="save-time-with-automated-investigation-and-response"></a>自動化された調査と対応で時間を節約する

(**新機能!**) 潜在的なサイバー攻撃を調査している場合は、期限厳守です。 脅威をより早く特定して軽減できれば、組織はより良くなります。 [自動調査および対応](office-365-air.md) (AIR) 機能には、アラートがトリガーされたときなどには自動的に、またはエクスプローラーのビューから手動で起動できるセキュリティ プレイブックのセットが含まれています。 AIR は、セキュリティ運用チームの脅威を軽減するための時間と労力を効果的かつ効率的に節約できます。 詳細については、「[Office 365 での AIR](office-365-air.md)」を参照してください。

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>Microsoft Defender for Office 365 の機能を使用するために必要な権限

セキュリティ/コンプライアンス センターで Microsoft Defender for Office 365 機能にアクセスするには、適切な役割が割り当てられている必要があります。 次の表にいくつかの例があります:

|役割または役割グループ|追加情報|
|---|---|
|グローバル管理者 (Azure Active Directory またはセキュリティ/コンプライアンス センターで割り当てることができます)|[Microsoft 365 管理者ロールについて](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|セキュリティ管理者 (Azure Active Directory またはセキュリティ/コンプライアンス センターで割り当てることができます)|[Azure Active Directory での管理者役割のアクセス許可](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online 組織管理 (Exchange Online で割り当てることができます)|[Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> [Exchange Online の PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|検索と消去 (セキュリティ/コンプライアンス センターでのみ割り当てることができます)|[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)|

詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 を取得する

Microsoft Defender for Office 365 は、Microsoft 365 E5、Office 365 E5、Office 365 A5、Microsoft 365 Business Premium などの特定のサブスクリプションに含まれています。 サブスクリプションに Defender for Office 365 が含まれていない場合は、特定のサブスクリプションへのアドオンとして Defender for Office 365 プラン 1 または Defender for Office 365 プラン 2 を購入できます。 詳細については、次のリソースを参照してください。

- Defender for Office 365 プランを含むサブスクリプションのリストについては、「[Microsoft Defender for Office 365 の可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)」を参照してください。

- プラン 1 と 2 に含まれる機能のリストについては、「[Microsoft Defender for Office 365 プランで利用できる機能](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)」

- [適切な Microsoft Defender for Office 365 を入手](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)して、プランを比較し、Defender for Office 365 を購入してください。

- [無料試用版を開始する](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 の新機能

Microsoft Defender for Office 365 には継続的に新機能が追加されています。 詳細については、次のリソースを参照してください。

- 「[Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)」は、開発およびロール アウトの新機能の一覧を提供します。

- [Microsoft Defender for Office 365 サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)は、Defender for Office 365 プラン全体の機能と可用性について説明しています。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

- [Microsoft 365 Defender での自動調査および対応 (AIR)](../mtp/mtp-autoir.md)
