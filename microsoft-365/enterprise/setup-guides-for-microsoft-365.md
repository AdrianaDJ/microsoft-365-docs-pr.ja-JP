---
title: Microsoft 365 および Office 365 サービスのセットアップ ガイド
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365_Setup
search.appverid:
- MET150
- MET150
- BCS160
ms.assetid: 165f46e8-3533-4d76-be57-97f81ebd40f2
description: セットアップガイドを使用して、Microsoft 365 または Office 365 の計画と構成を促進します。
ms.openlocfilehash: 7024494de231e5adcce4bb91414b5f7bb3349f88
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844094"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 および Office 365 サービスのセットアップ ガイド

「Microsoft 365 および Office 365 セットアップガイド」では、テナント、アプリ、およびサービスの計画と展開について、調整されたガイダンスとリソースが提供されています。 これらのガイドは、 [microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) の作業可能なスペシャリストが個々の対話で共有するのと同じベストプラクティスを使用して作成され、microsoft 365 管理センター内のすべての管理者が使用できます。 これにより、製品のセットアップ、セキュリティ機能の有効化、コラボレーションツールの展開、高度な展開を高速化するためのスクリプトの提供に関する情報が得られます。

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでのセットアップガイドへのアクセス方法

セットアップガイドは、Microsoft 365 管理センターの [セットアップガイダンス](https://aka.ms/setupguidance) ページからアクセスできます。 進捗状況を追跡して、ガイドを完成させるためのオプションをいつでも取得できます。 **セットアップガイダンス** ページにアクセスするには、次のようにします。

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)で、 **ホーム** ページに移動します。

2. **トレーニング & ガイド** カードを検索します。 

   ![Microsoft 365 管理センターのトレーニング & ガイドカード](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. カスタマイズした **セットアップガイダンス** を選択します。

   ![Microsoft 365 管理センターのセットアップガイダンスページのスクリーンショット](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

>[!NOTE]
>Microsoft 365 管理センターにアクセスするには、テナント管理者のアクセス許可が必要です。

## <a name="how-do-setup-guides-work-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターでのセットアップガイドの動作について

各ガイドには、手順を追って説明する、リソース、記事、および必要に応じて、構成の変更を行うために使用できるスクリプトが記載されています。 これらのガイドでは、小規模および大規模な組織の特定のニーズを反映する選択肢について説明します。 さらに、経験豊富な管理者のためのサポートが含まれています。

![セットアップガイドの例](../media/setup-guides-for-microsoft-365/m365-setupguide-example.png)

ガイドを使用すると、計画段階での特定の Microsoft 365 および Office 365 の機能の詳細について説明し、展開とロールアウトの間に、または設定を変更する展開を完了した後にそれらを見直すことができます。

## <a name="guides-for-initial-setup"></a>初期セットアップのガイド

### <a name="prepare-your-environment"></a>環境を準備する

「 [環境の準備](https://aka.ms/prepareyourenvironment) 」ガイドを使用すると、Microsoft 365 および Office 365 サービスのために組織の環境を準備することができます。 目的に関係なく、適切な展開を確実に行うために必要なタスクがあります。 環境の準備中にエラーが発生しないようにするために、ドメインの接続、ユーザーの追加、ライセンスの割り当て、Exchange Online を使用した電子メールのセットアップ、Office アプリのインストールまたは展開を行うためのステップバイステップの手順が提供されています。 

### <a name="email-setup-advisor"></a>電子メールの設定アドバイザー

[電子メールセットアップアドバイザー](https://aka.ms/office365setup)では、組織の Exchange Online を構成するために必要なステップバイステップガイダンスが提供されています。 これには、新しい電子メールアカウントの設定、電子メールの移行、電子メール保護の構成が含まれます。 電子メールの設定を正常に行うために、このアドバイザーを使用すると、組織の現在のメールシステム、移行されるメールボックスの数、およびユーザーとそのアクセスを管理する方法に基づいて、推奨される移行方法が提供されます。

### <a name="gmail-contacts-and-calendar-advisor"></a>Gmail 連絡先と予定表アドバイザー

Gmail ユーザーのメールボックスを Microsoft 365 に移行すると、電子メールメッセージは移行されますが、連絡先と予定表アイテムは移行されません。 [Gmail 連絡先および予定表アドバイザー](https://aka.ms/gmailcontactscalendar)は、Outlook.com、Outlook クライアント、または PowerShell でインポートおよびエクスポートメソッドを使用して、google 連絡先と google カレンダーアイテムを Microsoft 365 にインポートするための手順を提供します。

### <a name="microsoft-365-deployment-advisor"></a>Microsoft 365 展開アドバイザー

[Microsoft 365 展開アドバイザー](https://aka.ms/microsoft365setupguide)は、生産性ツール、セキュリティポリシー、およびデバイス管理機能を設定する際のガイダンスを提供します。 Microsoft 365 Business Premium または Microsoft 365 for enterprise サブスクリプションを使用すると、このアドバイザーを使用して組織のデバイスをセットアップおよび構成することができます。 

クラウドサービスを有効にし、サポートされている最新バージョンの Windows 10 にデバイスを更新し、デバイスを Azure Active Directory (Azure AD) に参加させるためのガイダンスとアクセス方法について説明します。


### <a name="remote-work-setup-guide"></a>リモート作業セットアップガイド

[リモート作業セットアップガイド](https://aka.ms/remoteworksetup)は、ユーザーがリモートで正常に作業できるようにするために必要なヒントとリソースを組織に提供し、データをセキュリティで保護し、ユーザーの資格情報を保護します。 

リモートアクセス VPN インフラストラクチャの負荷が軽減されるように、クラウド内の Microsoft 365 リソースと組織のネットワークの両方に対して、リモートワーカーのデバイストラフィックを最適化するガイダンスを受け取ります。 

### <a name="windows-virtual-desktop-setup-guide"></a>Windows 仮想デスクトップセットアップガイド

Windows 仮想デスクトップは、クラウドで実行される包括的なデスクトップおよびアプリケーション仮想化サービスです。 これは、簡略化された管理、マルチセッション Windows 10、Microsoft 365 アプリの最適化、およびリモートデスクトップサービス (RDS) 環境のサポートを提供する唯一の仮想デスクトップインフラストラクチャ (VDI) です。 Windows デスクトップとアプリを数分で Azure に展開して拡張し、組み込みのセキュリティ機能とコンプライアンス機能を利用できます。 

[Windows 仮想デスクトップセットアップガイド](https://aka.ms/wvdsetupguide)は、管理者に、リソースの計画と、展開、セットアップのガイダンス、およびその他のリソースに関する前提条件を提供します。 

### <a name="microsoft-edge-deployment-advisor"></a>Microsoft Edge 展開アドバイザー

Microsoft Edge は、世界クラスの互換性とパフォーマンス、必要なセキュリティとプライバシー、および web を最高にするために設計された新しい機能を提供するために、地上から再構築されています。

[Microsoft Edge 展開アドバイザー](https://aka.ms/edgeadvisor)は、エンタープライズサイト探索を構成して、組織内でアクセスされるサイトが IE モードを使用する必要があるかどうかを確認し、重要なセキュリティ機能を確認して構成し、組織の要件を満たすためにプライバシーポリシーおよび追加のポリシーを構成し、デバイスで web アクセスを管理するのに役立ちます。 Microsoft Edge は個別のデバイスにダウンロードできます。または、構成マネージャーまたは Microsoft Intune を使用して、組織内の複数のユーザーに展開する方法について説明します。
Windows 仮想デスクトップは、クラウドで実行される包括的なデスクトップおよびアプリケーション仮想化サービスです。 これは、簡略化された管理、マルチセッション Windows 10、Microsoft 365 アプリの最適化、およびリモートデスクトップサービス (RDS) 環境のサポートを提供する唯一の仮想デスクトップインフラストラクチャ (VDI) です。 Windows デスクトップとアプリを数分で Azure に展開して拡張し、組み込みのセキュリティ機能とコンプライアンス機能を利用できます。 

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune 構成マネージャーの共同管理のセットアップガイド

組織が Microsoft Intune と構成マネージャーの両方を使用して共同管理する既存の Configuration Manager クライアントデバイスと新しいインターネットベースのデバイスについては、 [Intune 構成マネージャーの共同管理セットアップガイド](https://aka.ms/comanagementsetup) を使用してください。 この共同管理の展開ガイドを使用すると、Windows 10 デバイスを管理して、両方のソリューションのメリットを受けながら、組織のデバイスに新しい機能を追加できます。

## <a name="guides-for-authentication-and-access"></a>認証とアクセスのガイド

### <a name="azure-ad-setup-guide"></a>Azure AD セットアップガイド

[AZURE AD セットアップガイド](https://aka.ms/aadpguidance)には、組織に強力なセキュリティ基盤があることを確認するための情報が記載されています。 このガイドでは、管理者向けの Azure の役割ベースのアクセス制御 (Azure RBAC)、オンプレミスのディレクトリの Azure AD Connect、および Azure AD Connect の正常性などの初期機能をセットアップして、自動同期時にハイブリッド id の正常性を監視できるようにします。 

また、オプションの高度な id 保護とユーザープロビジョニングの自動化を含む、セルフサービスのパスワードのリセット、条件付きアクセス、および統合されたサードパーティのサインオンを有効にする方法についても説明します。

### <a name="sync-users-from-your-orgs-directory"></a>組織のディレクトリからユーザーを同期する

「 [組織のディレクトリ同期」ウィザードからユーザーを同期](https://aka.ms/directorysyncsetup) すると、ディレクトリ同期が有効になります。 これにより、オンプレミスとクラウドの id が統合されて、簡単にアクセスして管理できるようになります。 シングルサインオン、セルフサービスオプション、アカウントの自動プロビジョニング、条件付きアクセス制御、コンプライアンスポリシーなど、新しい機能のロックを解除します。 これにより、ユーザーはどこからでも必要なリソースにアクセスできるようになります。

### <a name="plan-your-passwordless-deployment"></a>パスワードの展開を計画する

ユーザーがデバイスに安全にアクセスできるようにするための代替サインイン方法にアップグレードします。パスワードを次のようにします。以下のいずれかの認証方法を使用します。 

- Windows Hello for Business
- Microsoft Authenticator アプリ
- セキュリティキー 

[パスワードを使用しない [] 展開ウィザード](https://aka.ms/passwordlesssetup) を使用して、適切な passwordless の認証方法を見つけ、それらの展開方法に関するガイダンスを受けることができます。 

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>セルフサービスによるパスワードのリセット (SSPR) の展開を計画する

ユーザーに対して、自分のアカウントがロックされている場合は、自分のパスワードを変更または再設定することができます。または、ヘルプデスクエンジニアに連絡する必要なしに、パスワードを忘れることがあります。 

自分の環境に SSPR を展開する際に役立つ、適切な Azure ポータルオプションを構成するための関連記事と手順を受信するには、「 [セルフサービスによるパスワードリセット展開の計画」](https://aka.ms/SSPRSetupGuide) を使用します。

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>Active Directory フェデレーションサービス (AD FS) の展開アドバイザー

[AD fs 展開アドバイザー](https://aka.ms/adfsguidance)は、Microsoft 365 および Office 365 サービスのユーザーを認証するオンプレミスの AD FS インフラストラクチャを展開するためのステップバイステップのガイダンスを提供します。 このガイドでは、組織が AD FS のコンポーネントと要件を確認し、展開に必要な SSL 証明書を取得してインストールし、必要な web アプリケーションプロキシサーバーをインストールすることができます。 

## <a name="guides-for-security-and-compliance"></a>セキュリティとコンプライアンスのガイド

### <a name="microsoft-defender-for-endpoint-advisor"></a>エンドポイントアドバイザーの Microsoft Defender

[エンドポイントアドバイザーの Microsoft Defender](https://aka.ms/mdatpsetup)には、企業ネットワークが高度な脅威の防止、検出、調査、および応答を行う際に役立つ手順が記載されています。 組織の脆弱性に関する情報が得られた評価を行い、最適な展開パッケージと構成方法を決定します。 

>[!NOTE]
>エンドポイントの Microsoft Defender には、Microsoft ボリュームライセンスが必要です。

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protection のセットアップガイド

Microsoft Exchange Online Protection (EOP) は、スパムやマルウェアから保護するためのクラウドベースの電子メールフィルター処理サービスであり、メッセージングポリシー違反から組織を保護する機能を備えています。 

[Exchange Online Protection セットアップガイド](https://aka.ms/EOPguidance)を使用して、オンプレミスメールボックスの3つの展開シナリオ &mdash; 、ハイブリッド (オンプレミスとクラウドの混在) メールボックスのどちらを選択するか、またはすべてのクラウドメールボックスを組織に適合させるかを選択して、EOP を設定し &mdash; ます。 このガイドでは、ユーザーのライセンスを設定して確認し、Microsoft 365 管理センターでアクセス許可を割り当て、セキュリティ & コンプライアンスセンターで組織のマルウェア対策とスパムポリシーを構成するための情報とリソースを提供します。 

### <a name="microsoft-defender-for-office-365-advisor"></a>Microsoft Defender for Office 365 advisor

[Microsoft Defender For Office 365 advisor](https://aka.ms/oatpsetup)は、電子メールメッセージ、リンク、およびサードパーティのコラボレーションツールを使用して、お客様の環境で発生する可能性のある悪意のある脅威から組織を保護します。 このガイドでは、組織のニーズに合わせて Office 365 プランの Defender を準備および識別するのに役立つリソースと情報について説明します。 

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft information protection セットアップガイド

機密情報が確実に保護されるように、情報保護戦略に適用できる機能の概要について説明します。 機密情報を検出、分類、保護、および監視する4段階のライフサイクルアプローチを使用します。 [Microsoft information protection セットアップガイド](https://aka.ms/mipsetupguide)には、これらの各ステージを完了するためのガイダンスが記載されています。

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft information ガバナンスセットアップガイド

「 [Microsoft Information ガバナンスセットアップガイド」](https://aka.ms/migsetupguide) では、設定した特定のライフサイクルのガイドラインに従ってデータを分類して管理するための、組織のガバナンス戦略の設定と管理に必要な情報について説明します。 このガイドでは、組織の再利用可能なコンテンツおよびコンプライアンスレコードに適用されるラベル、ラベルポリシー、および保持ポリシーを作成、自動適用、または発行する方法について説明します。 また、バルクシナリオのファイル計画を使用して CSV ファイルをインポートする方法や、個々のドキュメントに手動で適用する方法についての情報も得られます。 

## <a name="guides-for-collaboration"></a>グループ作業のガイド

### <a name="microsoft-365-apps-deployment-advisor"></a>Microsoft 365 アプリの展開アドバイザー

[Microsoft 365 Apps 展開アドバイザー](https://aka.ms/OPPquickstartguide)は、Word、Excel、PowerPoint、OneNote などの Office 製品の最新バージョンを実行しているユーザーのデバイスを取得するのに役に立ちます。 管理ツールを使用してエンタープライズ展開に簡単にインストールできるオプションを含む、さまざまな展開方法についてのガイダンスが用意されています。 手順は、環境を評価し、特定の展開要件を把握して、インストールを成功させるために必要なサポートツールを実装するのに役立ちます。 

### <a name="office-mobile-apps-setup-assistant"></a>Office mobile apps セットアップアシスタント

[Office mobile apps セットアップアシスタント](https://aka.ms/officeappguidance)には、Windows、IOS、Android のモバイルデバイスで office アプリをダウンロードしてインストールするための手順が記載されています。 このガイドでは、Microsoft 365 および Office 365 アプリを携帯電話およびタブレットデバイスにダウンロードしてインストールするための詳細な手順について説明します。

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teams セットアップガイド

[Microsoft Teams セットアップガイド](https://aka.ms/teamsguidance)では、チームとプライベートコミュニケーションの両方について、メッセージング、通話、および音声またはビデオ会議を通じてリアルタイム会話をホストするチームワークスペースをセットアップするためのガイダンスを組織に提供します。 Teams 管理センター内でネットワークプランナーツールと Teams アドバイザーを使用して、組織のネットワーク要件を決定する手順が表示されます。 展開が完了すると、Teams の使用を開始するのに役立つリソースがガイドに表示されます。

### <a name="sharepoint-setup-guide"></a>SharePoint セットアップガイド

[Sharepoint セットアップガイド](https://aka.ms/spoguidance)は、sharepoint ドキュメントストレージとコンテンツ管理のセットアップ、サイトの作成、外部共有の構成、データの移行、および詳細設定の構成を行うことができます。また、組織内のユーザーの活動とコミュニケーションを促進します。 コンテンツ共有のアクセス許可ポリシーを構成する手順を実行し、移行同期ツールを選択して、SharePoint 環境のセキュリティ設定を有効にします。 

### <a name="onedrive-setup-guide"></a>OneDrive セットアップガイド

Onedrive の [セットアップガイド](https://aka.ms/ODfBquickstartguide) を使用して、onedrive ファイルの保存、共有、グループ作業、および同期機能を使い始めることができます。 OneDrive は、ユーザーが Microsoft 365 アプリのファイルを同期し、外部共有を構成し、ユーザーデータを移行し、セキュリティとデバイスアクセスの詳細設定を構成するための一元的な場所を提供します。 Onedrive のセットアップガイドは、OneDrive サブスクリプションまたはスタンドアロンの OneDrive プランを使用して展開できます。 

### <a name="yammer-deployment-advisor"></a>Yammer 展開アドバイザー

Yammer を使用して組織全体に接続して参加します。 [Yammer 展開アドバイザー](https://aka.ms/yammerdeploymentguide)は、ドメインを追加し、管理者を定義し、yammer ネットワークを結合することで、yammer ネットワークを準備します。 Yammer を展開して、外観をカスタマイズし、セキュリティとコンプライアンスを構成し、設定を調整するためのガイダンスが得られます。

## <a name="advanced-wizards"></a>高度なウィザード

### <a name="in-place-upgrade-with-configuration-manager"></a>構成マネージャーを使用した一括アップグレード

Windows 7 および Windows 8.1 デバイスを Windows 10 の最新バージョンにアップグレードする場合は、「 [Configuration Manager で一括アップグレード](https://aka.ms/win10upgradedemo) を実行する」を参照してください。 前提条件を確認し、一括アップグレードを自動的に構成するには、用意されているスクリプトを使用します。

### <a name="deploy-office-to-your-users"></a>ユーザーに Office を展開する

Office 展開ツールを使用してインストールをカスタマイズする機能を使用して、クラウドから Office アプリを展開します。 [ [Office をユーザーに展開する] ガイドを ](https://aka.ms/proplusodt) 使用すると、高度な設定を使用してカスタマイズされた office 構成を作成したり、事前に推奨される構成を使用したりできます。 ユーザーが自己インストールを実行しているか、ユーザーに個別にまたは一括して展開しているかにかかわらず、この詳細ウィザードでは、組織に合わせてカスタマイズされた Office インストールをユーザーに提供するためのステップバイステップの手順を説明します。

### <a name="deploy-office-to-remote-users"></a>リモートユーザーに Office を展開する

リモートで機能するようになったので、ユーザーが内部ネットワークに接続されていない場合や、自分のデバイスを使用している場合は、組織の Office 設定を受信する必要があります。 

Office [をリモートユーザー](https://aka.ms/officeremoteinstall) として展開するガイドを使用して、カスタマイズした office インストールを作成し、ユーザーに対して、構成を使用して office をシームレスにインストールする生成された PowerShell スクリプトを送信します。

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>Configuration Manager を使用して Microsoft 365 アプリを展開および更新する

構成マネージャーを使用している組織の場合は、「 [Deploy and Update microsoft 365 apps With Configuration manager advisor](https://aka.ms/oppinstall) 」を使用して、fasttrack エンジニアに推奨されるベストプラクティスを使用して Microsoft 365 アプリの展開を自動的に構成するスクリプトを生成できます。 このガイドを使用して、展開グループを構築し、Office アプリと機能をカスタマイズし、動的またはリーンインストールを構成した後、スクリプトを実行して、展開の対象とする必要があるアプリケーション、自動展開ルール、およびデバイスコレクションを作成します。 
