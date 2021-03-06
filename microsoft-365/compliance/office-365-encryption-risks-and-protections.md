---
title: 暗号化のリスクと保護
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
ms.custom:
- seo-marvel-mar2020
description: この記事では、Office 365 へのリスク、および保護に使用できる暗号化テクノロジについて説明します。
ms.openlocfilehash: a9abf3dcc6cbd1bdb237c6ccecbbbaa4d42fda2b
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769187"
---
# <a name="encryption-risks-and-protections"></a>暗号化のリスクと保護

Microsoft は、Microsoft 365 サービスおよびお客様のデータに対するリスクに重点を置いた制御およびコンプライアンスフレームワークに従います。 Microsoft は、これらのリスクを軽減するために、多数のテクノロジとプロセスベースの方法 (コントロールと呼ばれる) を実装しています。 コントロールを介したリスクの識別、評価、および軽減は、継続的なプロセスです。 

施設、ネットワーク、サーバー、アプリケーション、ユーザー (Microsoft 管理者など)、データなど、クラウドサービスのさまざまな層内におけるコントロールの実装は、多層防御戦略を形成します。 この戦略で重要なのは、さまざまなコントロールが異なる層に実装されており、同じまたは類似のリスクシナリオに対して保護されることです。 この複数層のアプローチは、何らかの理由でコントロールに障害が発生した場合に備えて、フェイルセーフ保護を提供します。

リスクのシナリオと、それらを軽減する現在利用可能な暗号化テクノロジを次に示します。 これらのシナリオは、多くの場合、Office 365 で実装されている他のコントロールを使用して軽減されます。

| 暗号化テクノロジ | サービス | キーの管理 | リスクシナリオ | 値 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online、Skype for Business | Microsoft | ディスクまたはサーバーが盗難または不適切にリサイクルされています。 | BitLocker は、盗難または不適切にリサイクルされたハードウェア (サーバー/ディスク) によるデータの損失を防止するための緊急時のアプローチを提供します。 |
| サービス暗号化 | SharePoint Online、Skype for Business、および OneDrive for businessExchange Online (ロードマップ) | Microsoft | 内部または外部のハッカーは、個々のファイル/データに blob としてアクセスしようとします。 | 暗号化されたデータをキーにアクセスせずに復号化することはできません。 ハッカーがデータにアクセスするリスクを軽減するのに役に立ちます。 |
| 顧客キー | SharePoint Online、OneDrive for Business、Exchange Online、Skype for business | 顧客 | N/A (この機能はコンプライアンス機能として設計されています。リスクに対する対策としてのものではありません)。 | お客様が内部の規制とコンプライアンスの義務、およびサービスを終了して Microsoft のデータへのアクセスを取り消すことができるように支援します。 |
| Microsoft 365 とクライアント間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Teams、Yammer | Microsoft、お客様 | Man-in-the-middle またはその他の攻撃によって、Microsoft 365 とクライアントコンピューターの間のデータフローをインターネット経由でタップします。 | この実装により、microsoft とお客様の両方に価値が提供され、Microsoft 365 とクライアントの間でデータの整合性を確保できます。 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for business | Microsoft | 社内またはその他の攻撃によって、microsoft 365 サーバー間のお客様のデータフローをさまざまな Microsoft データセンターにタップすることができます。 | この実装は、Microsoft データセンター間の攻撃からデータを保護するもう1つの方法です。 |
| Azure Rights Management (Microsoft 365 または Azure Information Protection に含まれています) | Exchange Online、SharePoint Online、OneDrive for Business | 顧客 | データは、データへのアクセス権を持たないユーザーの手に入ります。 | Azure Information Protection では、Azure RMS を使用して、複数のデバイス間でのファイルと電子メールのセキュリティ保護に役立つ暗号化、id、および承認ポリシーを使用して、顧客に価値を提供します。 Azure RMS は、特定の条件に一致する Microsoft 365 からのすべての電子メールを、別の受信者に送信する前に自動的に暗号化することができるお客様に価値を提供します。 |
| S/MIME | Exchange Online | 顧客 | 電子メールは、目的の受信者ではない人物の手に入ります。 | S/MIME では、S/MIME で暗号化された電子メールが電子メールの直接の受信者によって復号化されることを保証することで、お客様に価値が提供されます。 |
| Office 365 Message Encryption | Exchange Online、SharePoint Online | 顧客 | 保護された添付ファイルを含む電子メールは、電子メールの意図した受信者ではない Microsoft 365 内部または外部のユーザーの手に入ります。 | OME は、特定の条件に一致する Microsoft 365 からのすべてのメール (つまり、特定のアドレス宛てのすべての電子メール) が自動的に暗号化され、他の内部または外部の受信者に送信されるようになるお客様に価値を提供します。 |
| パートナー組織との SMTP TLS | Exchange Online | 顧客 | 電子メールは、Microsoft 365 テナントから別のパートナー組織への移行中に、man-in-the-middle またはその他の攻撃によって傍受されます。 | このシナリオでは、お客様に、Microsoft 365 テナントとパートナーの電子メール組織の間で暗号化された SMTP チャネル内のすべての電子メールを送受信できるという価値があります。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>マルチテナント環境で使用可能な暗号化テクノロジ

| 暗号化テクノロジ | で実装されている | キー交換のアルゴリズムと強さ | キー管理 * | FIPS 140-2 の検証 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレットセーフと Exchange サーバーのレジストリに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい。 AES 256 ビットを使用するサーバーの場合は、* * |
|  | SharePoint Online | AES 256 ビット | AES 外部キーは、シークレットセーフに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | AES 外部キーは、シークレットセーフに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
| サービス暗号化 | SharePoint Online | AES 256 ビット | Blob の暗号化に使用されるキーは、SharePoint Online コンテンツデータベースに格納されます。 SharePoint Online コンテンツデータベースは、データベースのアクセス制御と、保存時の暗号化によって保護されています。 暗号化は TDE in Azure SQL Database を使用して実行されます。 これらの機密情報は、テナントレベルではなく、SharePoint Online のサービスレベルで行われます。 これらの機密情報 (マスターキーと呼ばれることもあります) は、キーストアと呼ばれる別の安全なリポジトリに格納されます。 TDE は、アクティブデータベースとデータベースのバックアップとトランザクションログの両方に対して、セキュリティで保護を提供します。 顧客がオプションのキーを指定すると、顧客キーが Azure Key Vault に格納され、サービスはキーを使用してテナントキーを暗号化します。これは、サイトキーを暗号化するために使用されます。これは、ファイルレベルのキーを暗号化するために使用されます。 基本的に、顧客がキーを提供すると、新しいキー階層が導入されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | 各データは、ランダムに生成された異なる256ビットキーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納されます。これは、会議マスターキーごとにも暗号化されています。 マスターキーも、電話会議ごとに1回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft によって制御される暗号化キー (ロードマップ) または顧客 (顧客キーが使用されている場合) を使用するデータ暗号化ポリシーを使用して暗号化されます。 | 必要 |
| Microsoft 365 とクライアント/パートナーの間の TLS | Exchange Online | [複数の暗号スイートをサポートする便宜的な方法](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online 用の TLS 証明書 (outlook.office.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA1RSA 証明書です。 | はい、TLS 1.2 を256ビットの暗号強度で使用します。 |
|  | SharePoint Online | AES 256 を使用した TLS 1.2 <br> <br> [OneDrive for Business および SharePoint Online におけるデータ暗号化](https://technet.microsoft.com/library/dn905447.aspx) | SharePoint Online の TLS 証明書 (* sharepoint.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA1RSA 証明書です。 | 必要 |
|  | Skype for Business | [SIP 通信および PSOM データ共有セッションの TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business の TLS 証明書 (* lync.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Skype for Business の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | AES 256 を使用した TLS 1.2 <br> <br> [Microsoft Teams についてよく寄せられる質問-管理者向けヘルプ](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams 用の TLS 証明書 (teams.microsoft.com, edge.skype.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 | 必要 |
| Microsoft データセンター間の TLS | すべての Microsoft 365 サービス | AES 256 を使用した TLS 1.2 <br> <br> セキュリティで保護されたリアルタイム転送プロトコル (SRTP) | Microsoft では、Microsoft データセンター間のサーバー間通信に、社内で管理および展開された証明機関を使用しています。 | 必要 |
| Azure Rights Management (Microsoft 365 または Azure Information Protection に含まれています) | Exchange Online | は、更新され拡張された RMS 暗号化実装である [暗号化モード 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))をサポートします。 このメソッドは、署名と暗号化に RSA 2048 をサポートし、署名におけるハッシュの SHA-1-256 をサポートします。 | [Microsoft によって管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)されます。 | はい |
|  | SharePoint Online | は、更新され拡張された RMS 暗号化実装である [暗号化モード 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))をサポートします。 このメソッドは、署名と暗号化に RSA 2048 をサポートし、署名には SHA-1-256 をサポートします。 | [Microsoft によって管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)されます。これは既定の設定です。や <br> <br> お客様による管理。 Microsoft が管理するキーに代わるものです。 IT 管理の Azure サブスクリプションを所有している組織は、BYOK を使用して、その使用を無償でログに記録できます。 詳細については、「 [独自のキーを実装する](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)」を参照してください。 この構成では、nCipher Hsm を使用してキーを保護します。 詳細については、「 [NCipher hsm And AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)」を参照してください。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文 Standard 1.5 (PKCS #7) | お客様が管理する公開キー基盤が展開されているかどうかによって決まります。 キーの管理は顧客によって実行され、Microsoft は署名と復号化に使用される秘密キーにアクセスできません。 | ○ (3DES または AES256 を使用して送信メッセージを暗号化するように構成されている場合) |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ ([暗号化モード 2](https://technet.microsoft.com/library/dn569290.aspx) -署名と暗号化用の RSA 2048、および署名用の SHA-256) | Azure Information Protection を暗号化インフラストラクチャとして使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 | 必要 |
| パートナー組織との SMTP TLS | Exchange Online | AES 256 を使用した TLS 1.2 | Exchange Online 用の TLS 証明書 (outlook.office.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA1RSA 証明書です。 | はい、TLS 1.2 を256ビットの暗号強度で使用します。 |

**この表で参照されている TLS 証明書は、US データセンター用です。US 以外のデータセンターも2048ビットの SHA256RSA 証明書を使用します。*

***Exchange Online マルチテナント環境のほとんどのサーバーは、BitLocker の AES 256 ビット暗号化を使用して展開されています。AES 128 ビットを使用しているサーバーは、段階的に廃止されています。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>Government cloud community 環境で利用可能な暗号化テクノロジ

| 暗号化テクノロジ | で実装されている | キー交換のアルゴリズムと強さ | キー管理 * | FIPS 140-2 の検証 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレットセーフと Exchange サーバーのレジストリに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーは、シークレットセーフに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | AES 外部キーは、シークレットセーフに格納されます。 シークレットセーフは、高度な昇格とアクセス許可を必要とするセキュリティで保護されたリポジトリです。 アクセス許可の要求と承認は、ロックボックスと呼ばれる内部ツールを使用してのみ行うことができます。 AES 外部キーは、サーバーのトラステッドプラットフォームモジュールにも保存されます。 48桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
| サービス暗号化 | SharePoint Online | AES 256 ビット | Blob の暗号化に使用されるキーは、SharePoint Online コンテンツデータベースに格納されます。 SharePoint Online のコンテンツデータベースは、データベースのアクセス制御と、保存時の暗号化によって保護されています。 暗号化は TDE in Azure SQL Database を使用して実行されます。 これらの機密情報は、テナントレベルではなく、SharePoint Online のサービスレベルで行われます。 これらの機密情報 (マスターキーと呼ばれることもあります) は、キーストアと呼ばれる別の安全なリポジトリに格納されます。 TDE は、アクティブデータベースとデータベースのバックアップとトランザクションログの両方に対して、セキュリティで保護を提供します。 顧客がオプションのキーを指定すると、顧客キーが Azure Key Vault に格納され、サービスはキーを使用してテナントキーを暗号化します。これは、サイトキーを暗号化するために使用されます。これは、ファイルレベルのキーを暗号化するために使用されます。 基本的に、顧客がキーを提供すると、新しいキー階層が導入されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | 各データは、ランダムに生成された異なる256ビットキーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納されます。これは、会議マスターキーごとにも暗号化されています。 マスターキーも、電話会議ごとに1回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft またはお客様が管理する暗号化キーを使用するデータ暗号化ポリシーを使用して暗号化されます (顧客キーが使用されている場合)。 | 必要 |
| Microsoft 365 とクライアント/パートナーの間の TLS | Exchange Online | [複数の暗号スイートをサポートする便宜的な方法](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online 用の TLS 証明書 (outlook.office.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA1RSA 証明書です。 | はい、TLS 1.2 を256ビットの暗号強度で使用します。 |
|  | SharePoint Online | AES 256 を使用した TLS 1.2 | SharePoint Online の TLS 証明書 (* sharepoint.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA1RSA 証明書です。 | 必要 |
|  | Skype for Business | SIP 通信および PSOM データ共有セッションの TLS | Skype for Business の TLS 証明書 (* lync.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Skype for Business の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | [Microsoft Teams についてよく寄せられる質問-管理者向けヘルプ](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams の TLS 証明書 (teams.microsoft.com; edge.skype.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 | 必要 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、Skype for Business | AES 256 を使用した TLS 1.2 | Microsoft では、Microsoft データセンター間のサーバー間通信に、社内で管理および展開された証明機関を使用しています。 | 必要 |
|  |  | セキュリティで保護されたリアルタイム転送プロトコル (SRTP) |  |  |
| Azure Rights Management サービス | Exchange Online | は、更新され拡張された RMS 暗号化実装である [暗号化モード 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))をサポートします。 このメソッドは、署名と暗号化に RSA 2048 をサポートし、署名におけるハッシュの SHA-1-256 をサポートします。 | [Microsoft によって管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)されます。 | はい |
|  | SharePoint Online | は、更新され拡張された RMS 暗号化実装である [暗号化モード 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))をサポートします。 このメソッドは、署名と暗号化に RSA 2048 をサポートし、署名におけるハッシュの SHA-1-256 をサポートします。 | [Microsoft によって管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)されます。これは既定の設定です。や <br> <br> 顧客管理 (別名 is OK)。これは、Microsoft が管理するキーに代わるものです。 IT 管理の Azure サブスクリプションを所有している組織は、BYOK を使用して、その使用を無償でログに記録できます。 詳細については、「 [独自のキーを実装する](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)」を参照してください。 <br> <br> BYOK シナリオでは、nCipher Hsm を使用してキーを保護します。 詳細については、「 [NCipher hsm And AZURE RMS](https://www.thales-esecurity.com/msrms/cloud)」を参照してください。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文 Standard 1.5 (PKCS #7) | 公開キー基盤が展開されていることに依存します。 | はい。3DES または AES-256 を使用して送信メッセージを暗号化するように構成されている場合。 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ ([暗号化モード 2](https://technet.microsoft.com/library/dn569290.aspx) -署名と暗号化用の RSA 2048、および署名におけるハッシュの sha-1-256) | Azure RMS を暗号化インフラストラクチャとして使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 <br> <br> Microsoft Azure RMS を使用してキーを取得する場合、暗号化モード2が使用されます。 Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。 使用される方法は、社内 AD RMS 展開によって異なります。 暗号化モード 1 は、元来の AD RMS 暗号実装です。 署名と暗号化に RSA 1024 をサポートし、署名に SHA-1 をサポートしています。 このモードは、Hsm のすべての最新バージョンで引き続きサポートされています。ただし、Hsm を使用する BYOK 構成は除きます。 | 必要 |
| パートナー組織との SMTP TLS | Exchange Online | AES 256 を使用した TLS 1.2 | Exchange Online 用の TLS 証明書 (outlook.office.com) は、ボルチモア CyberTrust Root によって発行される2048ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、ボルチモア CyberTrust Root によって発行される2048ビットの sha1RSA 証明書です。 <br> <br> セキュリティ上の理由から、証明書は随時変更されることに注意してください。 | 必要 |

**この表で参照されている TLS 証明書は、US データセンター用です。US 以外のデータセンターも2048ビットの SHA256RSA 証明書を使用します。*
