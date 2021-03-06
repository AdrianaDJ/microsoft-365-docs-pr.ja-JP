---
title: データプライバシー規制に id、デバイス、および脅威保護を使用する
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365 の id、デバイス、および脅威保護サービスによる個人データ漏洩を防止します。
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847180"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>データプライバシー規制に id、デバイス、および脅威保護を使用する

Microsoft 365 には、組織がデータプライバシー関連のコンプライアンス規制に準拠するために役立つ、id、デバイス、および脅威保護のさまざまな機能が用意されています。 この記事では、これらの分野で必要なデータプライバシーの規則について説明し、関連する Microsoft 365 の機能とサービスの一覧を提供し、実装要件に対応するための詳細情報へのリンクを提供します。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Id、デバイス、および脅威保護がデータプライバシー規制にどのように関連しているか

データのプライバシーに関する規定は、その特異性によって異なりますが、呼び出し対象の本質は GDPR の記事 5 (1) (f) に含まれています。これは次のように記述します。 

- 個人データの適切なセキュリティを確保する方法で処理されるのは、承認されていない、または違法な処理に対する保護や、適切な技術または組織上の手段 (「誠実で機密性」) を使用した、偶発的な損失、破壊または破損の防止です。

個人データ違反は、管理者またはエンドユーザーのアカウント侵害や悪意のあるシステムアクセスによって発生することがよくあります。 たとえば、管理者アカウントのハッキングによって、顧客のクレジットカード番号またはその他の個人情報を exfiltration することができます。 Microsoft 365 で使用可能なすべての推奨される id、デバイス、および脅威保護を実装する必要があります。これは、コンプライアンスマネージャーに含まれるコンプライアンススコアに反映される可能性があります。

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>評価作業とコンプライアンスマネージャーの結果の使用

コンプライアンスマネージャーには、次のカテゴリを使用した id、デバイス、および脅威保護が含まれます。

- Id は、 **コントロールアクセス** のカテゴリに対応します。
- デバイスの **管理** カテゴリに対応します。
- 脅威保護は **脅威からの保護** カテゴリに対応します。
 
これらの4つの主要なデータプライバシー規制のセット全体でこれらを選択した場合、コンプライアンスマネージャーは90の改善アクションを指定します。ほとんどの場合、スコアは "27" です。 このような大規模な番号は、これらのカテゴリのコンプライアンスマネージャーによって呼び出されているため、参考として、いくつかの一般的なものがここに記載されています。

Id と **コントロールアクセス** カテゴリに [azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/)を使用します。これには、次の操作を実行できます。

- リプレイ対策認証を実装する ("Man-in-the-middle" 攻撃を防ぐため)
- レガシ認証をブロックする
- ユーザーのリスクとユーザーサインインリスクポリシーを構成します。
- 管理者および非管理者に対して、条件付きアクセスと多要素認証 (MFA) を有効にします。
- パスワードポリシーを構成して、適用します。
- Azure AD 特権 Id 管理を使用して、特権アカウントへのアクセスを制限します。
- 終了時にアクセスを無効にします。
- ユーザーアカウントと状態の変更を監査します。
- 役割グループと管理上の変更を確認します。

デバイス用の [Microsoft エンドポイントマネージャー](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) と **デバイスの管理** カテゴリを使用して、次のことを行うことができます。

- Jail が壊れていて、モバイルデバイスをブロックする。
- モバイルデバイス管理用に Intune を構成します。
- Android、iOS、macOS、Windows デバイスのコンプライアンスポリシーを作成します。
- Android、iOS、macOS、Windows デバイス用のデバイス構成プロファイルを作成します。
- IOS および Windows 用のアプリ保護ポリシーを作成します。
- ロック画面を使用して情報を隠す。
- モバイルデバイスのパスワードポリシーを実装します。
- モバイルデバイスが非アクティブ時にロックされるようにする。
- 複数のサインインエラーについてモバイルデバイスをワイプする必要があります。

「 **脅威からの保護** 」カテゴリで、 [Exchange Online Protection と Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md)を使用します。これには、次のことを行うことができます。

- 送信者の認証を有効にします (SPF、DMARC、および DKIM)。
- Microsoft Defender for Office 365 のフィッシング対策ポリシーをセットアップします。
- 安全な添付ファイルを実装します。
- 安全なリンクを実装します。
- マルウェアの検出と応答のポリシーを実装します。
- 送信および受信スパムポリシーを実装します。

### <a name="references"></a>設定

- [共通 ID とデバイスのアクセス ポリシー](../security/office-365-security/identity-access-policies.md)
- [Office 365 で脅威から保護する](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [添付ファイル保護](../security/office-365-security/atp-safe-attachments.md)
- [リンク保護](../security/office-365-security/atp-safe-links.md)
- [安全なドキュメント](../security/office-365-security/safe-docs.md)
