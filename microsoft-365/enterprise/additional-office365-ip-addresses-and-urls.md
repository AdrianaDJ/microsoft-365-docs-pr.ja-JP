---
title: Office 365 IP アドレスと URL Web サービスに含まれないその他のエンドポイント
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/29/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: ''
description: '概要: 新しいエンドポイントの Web サービスでは、特定のシナリオ用の一部のエンドポイントは含まれません。'
hideEdit: true
ms.openlocfilehash: b94bd187eb0e450a2a85d4d156472e1f96420261
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558178"
---
# <a name="additional-endpoints-not-included-in-the-office-365-ip-address-and-url-web-service"></a>Office 365 IP アドレスと URL Web サービスに含まれないその他のエンドポイント

一部のネットワーク エンドポイントは以前に公開されているため、[Office 365 IP アドレスと URL Web サービス](microsoft-365-ip-web-service.md)には含まれていません。Web サービスの範囲に含まれるのは、組織の境界ネットワーク上の Office 365 のユーザーの接続に必要なネットワーク エンドポイントです。現在、以下のものが含まれません。

1. Microsoft データ センターからお客様のネットワーク (ハイブリッド サーバーの着信ネットワーク トラフィック) への必要なネットワーク接続。
2. 組織のネットワーク境界上 (送信サーバーのネットワーク トラフィック) のお客様のネットワーク上のサーバーからのネットワーク接続。
3. ユーザーが設定する、ネットワーク接続要件に関する特殊なシナリオ。
4. DNS 解決の接続要件 (下記の一覧には含まれていません)。
5. Internet Explorer または Microsoft Edge の信頼済みサイト。

DNS に関するものを除き、記載された特定のシナリオを必要としない場合は、大多数のお客様にとりこれらはすべて省略可能です。

| 行 | 用途 | Destination (転送先) | 型 |
|:-----|:-----|:-----|:-----|
| 1  | PST やファイル取り込みのための[インポート サービス](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6) | その他の要件については、「[インポート サービス](https://support.office.com/article/use-network-upload-to-import-your-organization-pst-files-to-office-365-103f940c-0468-4e1a-b527-cc8ad13a5ea6)」をご覧ください。 | 特殊な送信シナリオ |
| 2  | [Office 365 用の Microsoft サポート/回復アシスタント](https://diagnostics.office.com/#/)  | https<span>://</span>autodiscover.outlook.com <BR> <span>https://</span>officecdn.microsoft.com <BR> <span>https://</span>api.diagnostics.office.com <BR> <span>https://</span>apibasic.diagnostics.office.com <BR> <span>https://</span>autodiscover-s.outlook.com <BR> <span>https://</span>cloudcheckenabler.azurewebsites.net <BR> <span>https://</span>dcs-staging.azure-api.net <BR> <span>https://</span>login.live.com <BR> <span>https://</span>login.microsoftonline.com <BR> <span>https://</span>login.windows.net <BR> <span>https://</span>o365diagtelemetry.trafficmanager.net <BR> <span>https://</span>odc.officeapps.live.com <BR> <span>https://</span>offcatedge.azureedge.net <BR> <span>https://</span>officeapps.live.com <BR> <span>https://</span>outlook.office365.com <BR> <span>https://</span>outlookdiagnostics.azureedge.net | 送信サーバー トラフィック |
| 3  | Azure AD Connect (SSO オプション使用) – WinRM およびリモート PowerShell | 顧客の STS 環境 (AD FS サーバーおよび AD FS プロキシ) \| TCP ポート 80 と 443 | 受信サーバー トラフィック |
| 4  | AD FS プロキシ サーバー (フェデレーション対象顧客専用) などの STS | 顧客の STS (AD FS プロキシなど)\|ポート TCP 443 または TCP 49443 (ClientTLS使用) | 受信サーバー トラフィック |
| 5  | [Exchange Online ユニファイド メッセージング/SBC 統合](https://technet.microsoft.com/library/jj673565.aspx) | オンプレミス セッション ボーダー コント ローラーと *. um.outlook.com 間で双方向 | 送信サーバー トラフィック |
| 6  | メールボックスの移行。オンプレミスの [Exchange ハイブリッド](https://docs.microsoft.com/exchange/exchange-deployment-assistant) から Office 365 へのメールボックスの移行が開始されると、Office 365 は Exchange Web サービス (EWS)/Mailbox Replication サービス (MRS) サーバーに接続されます。Exchange Online サーバーが使用する NAT IP アドレスを特定の送信元 IP の範囲からの受信接続に限定する場合は、「 [Office 365 の URL と IP アドレスの範囲](urls-and-ip-address-ranges.md) 」の「Exchange Online」サービス領域の欄に一覧が掲載されています。TCP 443 接続を特定の送信元 IP 範囲に制限する前に、MRS プロキシが別の FQDN とパブリック IP アドレスに解決するようにして、OWA などの公開済みの EWS エンドポイントへのアクセスが制限されないように注意する必要があります。 | 顧客のオンプレミス EWS/MRS プロキシ<br> TCP ポート 443 | 受信サーバー トラフィック |
| 7  | [Exchange ハイブリッド](https://docs.microsoft.com/exchange/exchange-deployment-assistant) 空き時間情報の共有などの共存機能。 | 顧客のオンプレミス Exchange サーバーのバージョン | 受信サーバー トラフィック |
| 8  | [Exchange ハイブリッド](https://docs.microsoft.com/exchange/exchange-deployment-assistant) プロキシ認証 | 顧客のオンプレミス STS | 受信サーバー トラフィック |
| 9  | [Exchange ハイブリッド構成ウィザード](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)を使用して [Exchange ハイブリッド](https://docs.microsoft.com/exchange/exchange-deployment-assistant)を構成する場合に使用します。 <br> 注: これらのエンドポイントは、Exchange ハイブリッドの構成にのみ必要です。  | TCP ポート 80 と 443 の domains.live.com は、Exchange 2010 SP3 ハイブリッド構成ウィザードでのみ必要です<BR> <BR> GCC High、DoD IP アドレス: 40.118.209.192/32、168.62.190.41/32 <BR> <BR> 世界中の商用および GCC: *.store.core.windows.net、asl.configure.office.com、mshrcstorageprod.blob.core.windows.net、tds.configure.office.com、mshybridservice.trafficmanager.net <BR>  | 送信サーバー トラフィック |
| 10  | AutoDetect サービスは、[iOS および Android 用の Outlook でハイブリッド先進認証](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)を行う [Exchange ハイブリッド](https://docs.microsoft.com/exchange/exchange-deployment-assistant) シナリオで使用します。 <BR> <BR> ```*.acompli.net``` <BR> <BR> ```*.outlookmobile.com``` <BR> <BR> ```*.outlookmobile.us``` <BR> <BR> ```52.125.128.0/20``` <BR> ```52.127.96.0/23``` <BR> | 顧客の TCP 443 のオンプレミス Exchange サーバー | 受信サーバー トラフィック |
| 11  | Exchange ハイブリッド Azure AD 認証 | *. msappproxy.net | TCP 送信サーバーのみのトラフィック |
| 12   | Office 2016 の Skype for Business には、UDP ポートを使用するビデオ ベースの画面共有が含まれています。Office 2013 以前の Skype for Business クライアントでは、TCP ポート 443 経由で RDP を使用していました。 | TCP ポート 443 を 52.112.0.0/14 に開く | Office 2013 以前の Skype for Business の古いクライアント バージョン |
| 13   | Skype for Business ハイブリッド オンプレミス サーバーから Skype for Business Online への接続性 | 13.107.64.0/18, 52.112.0.0/14  <BR> UDP ポート 50,000-59,999 <BR>  TCP ポート 50,000-59,999; 5061 | Skype for Business オンプレミス サーバーの送信接続性 |
| 14   | オンプレミスのハイブリッド接続を使用するクラウド PSTN では、オンプレミスのホストへのネットワーク接続を開く必要があります。Skype for Business Online のハイブリッド構成の詳細については、  | 「[Skype for Business Server と Office 365 間のハイブリッド接続を計画する](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity)」を参照してください。 | Skype for Business オンプレミス ハイブリッド受信 |
| 15  | **認証と ID FQDN** <br> FQDN (```secure.aadcdn.microsoftonline-p.com```) を機能させるには、クライアントの Internet Explorer (IE) またはエッジの信頼済みサイト ゾーンに含める必要があります。 |  | 信頼済みサイト |
| 16   |  **Microsoft Teams FQDN** <br> Internet Explorer または Microsoft Edge を使用している場合は、最初にサード パーティの cookie を有効にし、信頼済みサイトに (スイート製品全体の FQDN、CDN、および 14 行目に記載されているテレメトリに加え) Teams の FQDN を追加する必要があります。詳細については、「[Microsoft Teams の既知の問題](https://docs.microsoft.com/microsoftteams/known-issues)」を参照してください。 |  | 信頼済みサイト |
| 17   |  **Sharepoint Online と OneDrive for Business FQDN** <br> 「\<tenant>」が入ったすべての FQDN (「.sharepoint.com」) を機能させるには、クライアントの IE または Edge の信頼済みサイト ゾーンに含める必要があります。スイート製品全体の FQDN、CDN、および 14 行目に記載されているテレメトリに加えて、これらのエンドポイントも追加する必要があります。 |  | 信頼済みサイト |
| 18   | **Yammer**  <br> Yammer はブラウザーでのみ利用でき、認証されたユーザーはプロキシを経由する必要があります。Yammer のすべての FQDN をさせるには、クライアントの IE またはエッジの信頼済みサイト ゾーンに含める必要があります。 |  | 信頼済みサイト |
| 19  | [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) を使用して、オンプレミスのユーザー アカウントを Azure AD に同期します。 | 詳細については、「[ハイブリッド ID で必要なポートとプロトコル](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-ports)」、「[Azure AD の接続のトラブルシューティング](https://docs.microsoft.com/azure/active-directory/hybrid/tshoot-connect-connectivity)」、および「[Azure AD Connect Health エージェントのインストール](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-health-agent-install#outbound-connectivity-to-the-azure-service-endpoints)」を参照してください。 | 送信サーバーのみのトラフィック |
| 1280  | 中国の 21 ViaNet の [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/) を使用して、オンプレミスのユーザー アカウントを Azure AD に同期します。 | \*.digicert.com:80 <BR> \*.entrust.net:80 <BR> \*.chinacloudapi.cn:443 <BR> secure.aadcdn.partner.microsoftonline-p.cn:443 <BR>*.partner.microsoftonline.cn:443 <BR> <BR>「[Azure AD の接続に関する問題のトラブルシューティング](https://docs.azure.cn/zh-cn/active-directory/hybrid/tshoot-connect-connectivity)」も参照してください。 | 送信サーバーのみのトラフィック |
|  21  | Microsoft Stream (Azure AD ユーザー トークンが必要)。 <BR> Office 365 ワールドワイド (GCC を含む) | \*.cloudapp.net <BR> \*.api.microsoftstream.com <BR> \*.notification.api.microsoftstream.com <BR> amp.azure.net <BR> api.microsoftstream.com <BR> az416426.vo.msecnd.net <BR> s0.assets-yammer.com <BR> vortex.data.microsoft.com <BR> web.microsoftstream.com <BR> TCP ポート 443  | 受信サーバー トラフィック |
| 22  | サーバーの新規インストールと Active Directory ドメイン サービス (AD DS) でのセットアップの両方の、多要素認証要求に MFA サーバーを使用します。 | 「 [AZURE AD 多要素認証サーバーの](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-deploy#plan-your-deployment)概要」を参照してください。  | 送信サーバーのみのトラフィック |
| 最高  | Microsoft Graph の変更通知 | 開発者は、Microsoft Graph のイベントを購読するために、[変更の通知](https://docs.microsoft.com/graph/webhooks?context=graph%2Fapi%2F1.0&view=graph-rest-1.0)を利用できます。 | *.cloudapp.net<BR> 104.43.130.21、137.116.169.230、13.79.38.63、104.214.39.228、パブリッククラウド: 168.63.250.205、52.161.9.202、40.68.103.62、13.89.60.223、23.100.95.104、40.113.95.219、104.214.32.10、168.63.237.145、52.161.110.176、52.174.177.183、13.85.192.59、13.85.192.123、13.86.37.15、13.89.108.233、13.89.104.147、20.44.210.83、20.44.210.146、40.76.162.99、40.76.162.42、40.74.203.28、40.74.203.27、51.104.159.213、51.104.159.181、51.124.75.43、51.124.73.177、51.138.90.7、51.138.90.52、52.139.153.222、52.139.170.157、52.139.170.47、52.142.114.29、52.142.115.31、52.147.213.251、52.147.213.181、52.148.24.136、52.148.27.39、52.148.115.48、52.148.114.238、52.154.246.238、52.159.23.209、52.159.17.84、52.184.94.140、 <BR> 米国政府機関向け Microsoft Cloud: 52.244.231.173、52.238.76.151、52.244.250.211、52.238.78.108、52.243.147.249、52.243.148.19、52.243.157.104、52.243.157.105、52.244.33.45、52.244.35.174、52.244.111.156、52.244.111.170 <BR> Microsoft Cloud ドイツ: 51.4.231.136、51.5.243.223、51.4.226.154、51.5.244.215、51.4.150.206、51.4.150.235、51.5.147.130、51.5.148.103 <BR> 21Vianet が運用している Microsoft Cloud 中国: 139.219.15.33、42.159.154.223、42.159.88.79、42.159.155.77、40.72.155.199、40.72.155.216、40.125.138.23、40.125.136.69、42.159.72.35、42.159.72.47、42.159.180.55、42.159.180.56<BR> TCP ポート 443 <BR> 注: 開発者は、サブスクリプションの作成時にさまざまなポートを指定できます。  | 受信サーバー トラフィック |
|||||

## <a name="related-topics"></a>関連項目

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)
  
[Office 365 の接続に関するトラブルシューティング](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d.aspx)
  
[クライアント接続](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[コンテンツ配信ネットワーク](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure データ センターの IP 範囲](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Microsoft パブリック IP スペース](https://www.microsoft.com/download/details.aspx?id=53602)
