---
title: 暗号化の BitLocker
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 で BitLocker 暗号化を使用する方法について説明し、コンピューターやディスクの紛失や盗難によるデータの盗難の可能性を低減します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033625"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker と Distributed Key Manager (DKM) による暗号化

Microsoft サーバーは、BitLocker を使用して、お客様のデータが保存されているディスクドライブをボリュームレベルで暗号化します。 BitLocker 暗号化は、Windows に組み込まれているデータ保護機能です。 BitLocker は、顧客データが含まれるディスクに何者かが物理的にアクセスできるようになりかねない過失がプロセスや制御 (アクセス制御またはハードウェアのリサイクルなど) で生じた場合に、脅威から安全に保護するために使用されるテクノロジの 1 つです。 その場合、BitLocker は、コンピューターやディスクの紛失、盗難、または不適切な廃棄によるデータの盗難や漏洩などの脅威の可能性を低減します。

BitLocker は、Exchange Online、SharePoint Online、Skype for Business の顧客データが格納されているディスク上に、Advanced Encryption Standard (AES) 256 ビット暗号化を使用して展開されます。 ディスクセクターは、完全なボリューム暗号化キー (FVEK) で暗号化され、ボリュームマスターキー (VMK) を使用して暗号化されます。これは、サーバーのトラステッドプラットフォームモジュール (TPM) にバインドされます。 VMK は FVEK を直接保護するため、VMK を保護することが重要になります。 次の図は、特定のサーバー (この場合は Exchange Online server を使用) に対する BitLocker キー保護チェーンの例を示しています。

次の表は、特定のサーバー (この場合は Exchange Online server) に対する BitLocker キー保護チェーンを示しています。

| キーの保護機能 | 性 | 生成方法 | 保存される場所 | 保護 |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| AES 256-ビット外部キー | サーバーごと | BitLocker Api | TPM またはシークレットセーフ | ロックボックス/アクセス制御 |
|  |  |  | メールボックスサーバーのレジストリ | TPM 暗号化 |
| 48桁の数字のパスワード | ディスクあたり | BitLocker Api | Active Directory | ロックボックス/アクセス制御 |
| X.509 証明書をデータ回復エージェント (DRA) として公開キー保護機能とも呼びます。 | 環境 (Exchange Online マルチテナントなど) | Microsoft CA | ビルドシステム | 秘密キーへの完全なパスワードを持っているユーザーはいません。 パスワードは、[物理的な保護] の下にあります。 |


BitLocker キー管理は、Microsoft データセンターで暗号化されたディスクのロック解除/回復に使用する回復キーの管理を伴います。 Microsoft 365 では、セキュリティで保護された共有にマスターキーを格納します。これは、スクリーンドおよび承認された個人のみがアクセスできます。 キーの資格情報は、アクセス制御データ ("secret store" と呼ばれる) に対するセキュリティで保護されたリポジトリに格納されます。これには、高度な昇格と、ジャストインタイムのアクセス昇格ツールを使用してアクセスするための管理承認が必要です。

BitLocker は、2つの管理カテゴリに分類されるキーをサポートします。

- 通常、サーバーまたは特定のディスクにインストールされているオペレーティングシステムのインスタンスの有効期間が短時間で、BitLocker で管理されているキー。 これらのキーは、サーバーの再インストール時またはディスクのフォーマット時に削除され、リセットされます。

- Bitlocker の外部で管理されているが、ディスクの復号化に使用される BitLocker 回復キー。 BitLocker は、オペレーティングシステムが再インストールされ、暗号化されたデータディスクが既に存在するシナリオで、回復キーを使用します。 回復キーは、応答側がディスクのロックを解除する必要がある Exchange Online の管理された可用性監視プローブによっても使用されます。

BitLocker で保護されたボリュームは、完全なボリューム暗号化キーを使用して暗号化されます。これは、ボリュームマスターキーで暗号化されます。 BitLocker は FIPS に準拠したアルゴリズムを使用して、暗号化キーが暗号化されずに保存または送信されることがないようにします。 お客様のデータを保存するための Microsoft 365 の実装は、既定の BitLocker 実装から逸脱したものではありません。
