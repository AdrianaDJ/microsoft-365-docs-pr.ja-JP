---
title: Microsoft Cloud における暗号化
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
description: この記事では、Microsoft cloud で顧客データを安全に保つために使用されるさまざまな形式の暗号化の概要について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214275"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft Cloud における暗号化

Microsoft のエンタープライズクラウドサービス内の顧客データは、さまざまな形式の暗号化などのさまざまなテクノロジとプロセスによって保護されています。 (この文書に含まれるお客様のデータには、Exchange Online メールボックスのコンテンツ、電子メール本文、予定表のエントリ、電子メールの添付ファイルの内容、適用可能な場合、Skype for Business コンテンツ、サイト内に格納されているファイル、および OneDrive for business または Skype for business にアップロードされたファイルが含まれます。Microsoft では、製品とサービスに対して複数の暗号化方式、プロトコル、および暗号を使用して、顧客データがクラウドサービスを通過するための安全なパスを提供し、クラウドサービス内に格納されている顧客データの機密性を保護するのに役立つようにしています。 Microsoft では、お客様のデータへの不正なアクセスからの障壁を得るために使用できる最強の安全な暗号化プロトコルの一部を使用しています。 適切なキー管理は、暗号化のベストプラクティスの重要な要素でもあり、microsoft は、すべての Microsoft 管理暗号化キーが適切にセキュリティ保護されていることを確認するために機能します。

お客様の構成に関係なく、Microsoft のエンタープライズクラウドサービス内に格納されているお客様のデータは、1つ以上の形式の暗号化を使用して保護されます。 (暗号化ポリシーとその強制の検証は、複数のサードパーティの監査者によって個別に確認され、それらの監査のレポートは[サービス信頼ポータル](https://aka.ms/stp)で利用できます)。

Microsoft は、お客様のデータを保存中および転送中に暗号化するサービス側テクノロジを提供しています。 たとえば、お客様のデータが保存されている場合、Microsoft Azure は[bitlocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)と[DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)を使用し、microsoft 365 は Bitlocker、 [Azure Storage Service 暗号化](https://docs.microsoft.com/azure/)、 [Distributed Key Manager](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM)、および microsoft 365 Service 暗号化を使用します。 転送中の顧客データの場合、Azure、Office 365、Microsoft コマーシャルサポート、Microsoft Dynamics 365、Microsoft Power BI、Visual Studio Team Services は、Microsoft データセンター間、およびユーザーデバイスと Microsoft データセンター間で、業界標準のセキュリティで保護されたトランスポートプロトコル (インターネットプロトコルセキュリティ (IPsec)、トランスポート層セキュリティ (TLS) など) を使用します。

Microsoft によって提供される暗号化セキュリティのベースラインレベルに加えて、クラウドサービスには、管理可能な追加の暗号化オプションも含まれています。 たとえば、Azure 仮想マシン (Vm) とユーザーの間のトラフィックに対して暗号化を有効にすることができます。 [Azure 仮想ネットワーク](https://azure.microsoft.com/services/virtual-network/)では、業界標準の IPsec プロトコルを使用して、企業の VPN ゲートウェイと Azure の間、および仮想ネットワーク上に配置された vm 間のトラフィックを暗号化することができます。 さらに、[新しい Office 365 メッセージの暗号化機能](set-up-new-message-encryption-capabilities.md)を使用すると、暗号化されたメールをだれにでも送信できます。

Microsoft[セキュリティポリシー](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)のコンポーネントである公開キー基盤の運用セキュリティ標準に準拠して、microsoft は、証明書と認証機構のために Windows オペレーティングシステムに含まれている暗号化機能を活用しています。これには、米国政府機関の[連邦情報処理規格](https://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 標準に準拠する暗号化モジュールの使用が含まれます。 (Microsoft の関連する NIST 証明書番号については、「」を参照してください。https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> ことMicrosoft セキュリティポリシーにリソースとしてアクセスするには、職場または学校のアカウントを使用してサインインする必要があります。 サブスクリプションをまだお持ちでない場合は、[無料試用版にサインアップでき](https://servicetrust.microsoft.com/Home/TrialSubscriptions)ます。

FIPS 140-2 は、これを使用する製品ではなく、暗号化を実装する製品モジュールを検証するために特別に設計された標準です。 サービス内で実装されている暗号化モジュールは、ハッシュの強度、キーの管理などの要件を満たすことが認定されている場合があります。 Microsoft のクラウドサービスでのデータの機密性、整合性、または可用性を保護するために暗号化機能が使用されている場合は、FIPS 140-2 標準に準拠するモジュールと暗号が使用されます。

Microsoft は、Windows オペレーティングシステムの新しいリリースごとにクラウドサービスで使用される基礎となる暗号化モジュールを認定しています。

- Azure および Azure 米国政府
- Dynamics 365、Dynamics 365 米国政府
- Office 365、Office 365 U.S. Government、Office 365 U.S. Government Defense

保存されている顧客データの暗号化は、BitLocker、DKM、Azure Storage Service の暗号化、Exchange Online、Skype for business、OneDrive for Business、および SharePoint Online のサービス暗号化など、複数のサービス側テクノロジによって提供されます。 Office 365 service encryption には、Azure Key Vault に格納されている、顧客が管理する暗号化キーを使用するオプションが含まれています。 Customer[キー](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)と呼ばれるこの顧客管理キーオプションは、Exchange Online、SharePoint Online、Skype for business、および OneDrive for business で使用できます。

送信中の顧客データの場合、すべての Office 365 サーバーは、既定で TLS を使用してセキュリティで保護されたセッションを、顧客データをセキュリティで保護するクライアントコンピューターを使用してネゴシエートします  これは、Skype for Business、Outlook、web 上の Outlook、モバイルクライアント、web ブラウザーなど、クライアントによって使用されるすべてのデバイスのプロトコルに適用されます。

(お客様に接しているすべてのサーバーは、既定で TLS 1.2 にネゴシエートされますが、必要に応じて、より低い標準へのネゴシエートもサポートしています)。

## <a name="related-links"></a>関連リンク

- [Azure での暗号化](office-365-azure-encryption.md)
- [BitLocker とDistributed Key Manager (DKM) による暗号化](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 でのサービスの暗号化](office-365-service-encryption.md)
- [Skype for business、OneDrive for Business、SharePoint Online、Exchange Online の Office 365 暗号化](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [転送中データの暗号化](office-365-encryption-for-data-in-transit.md)
- [顧客により管理される暗号化機能](office-365-customer-managed-encryption-features.md)
- [暗号化のリスクと保護](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 での暗号化](office-365-encryption-in-microsoft-dynamics-365.md)
