---
title: Office 365 Message Encryption の古い情報
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 組織の従来のファイルを Office 365 Message Encryption (OME) に移行する方法について説明します。
ms.openlocfilehash: ecf4723df9afdf09d63150a3ec7564df44dd9808
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408995"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 Message Encryption の古い情報

まだ組織を新しい OME 機能に移行していない場合でも、既に OME を展開している場合は、この記事の情報が組織に適用されます。 Microsoft は、組織にとって適切であることをすぐに、新しい OME 機能に移行するための計画を立てることを推奨します。 手順については、「 [Azure Information Protection の上に構築された新しい Office 365 メッセージ暗号化機能のセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。 新しい機能が最初にどのように機能するかについて詳しくは、「 [Office 365 Message Encryption](ome.md)」を参照してください。 この記事の残りの部分では、新しい OME 機能のリリース前の OME の動作を示します。
  
Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 メッセージの暗号化は、Outlook.com、Yahoo、Gmail、その他の電子メールサービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。
  
次に、いくつかの例を示します:
  
- 銀行の従業員がクレジットカードの明細書を顧客に送信する

- 保険会社の担当者は、顧客にポリシーの詳細を提供します。

- 抵当ブローカーは、顧客からローン申請の財務情報を要求します。

- 医療保険会社が患者に医療保険情報を送信する

- 弁護士が顧客または別の弁護士に機密情報を送信する

## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>新機能なしで Office 365 メッセージの暗号化がどのように機能するか

Office 365 Message Encryption は、Microsoft Azure Rights Management (Azure RMS) に基づいて構築されたオンラインサービスです。 Azure RMS では、管理者はメールフロールールを定義して、暗号化の条件を決めることができます。 たとえば、特定の受信者に宛てたすべてのメッセージの暗号化を必要とするルールがあります。
  
この短いビデオを見て、Office 365 メッセージの暗号化が新機能なしでどのように動作するかを確認します。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
ユーザーが暗号化ルールに一致する電子メールメッセージを Exchange Online で送信すると、メッセージは HTML 添付ファイルと共に送信されます。 受信者は、HTML 添付ファイルを開き、Office 365 メッセージ暗号化ポータルで暗号化されたメッセージを表示する指示に従います。 受信者は、Office 365 に関連付けられた Microsoft アカウントまたは職場または学校でサインインするか、またはワンタイムパスコードを使用して、メッセージを表示するかを選択できます。 どちらのオプションも、指定された受信者のみが暗号化されたメッセージを表示できるようにするために役立ちます。 このプロセスは、新しい OME 機能とは大きく異なります。
  
下の図は、暗号化と復号化のプロセスにおける電子メール メッセージの流れをまとめたものです。
  
![暗号化された電子メールのパスを示す図](../media/O365-Office365MessageEncryption-Concept.png)
  
詳細については、 [新しい OME 機能のリリース前に、「従来の Office 365 Message Encryption のサービス情報](legacy-information-for-message-encryption.md#LegacyServiceInfo)」を参照してください。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>新しい OME 機能を使用しない Office 365 メッセージ暗号化のメールフロールールを定義する

新しい機能を使用せずに Office 365 メッセージの暗号化を有効にするには、exchange Online および Exchange Online Protection 管理者が Exchange メールフロールールを定義します。 これらのルールは、電子メールメッセージを暗号化する条件、およびメッセージの暗号化を削除する条件を決定します。 ルールに対して暗号化アクションが設定されている場合、メッセージを送信する前に、ルールの条件に一致するすべてのメッセージに対してこのサービスによってアクションが実行されます。

メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Office 365 Message Encryption は、暗号化された電子メールの受信者からの返信を暗号化することもできます。また、電子メールユーザーにとって便利なように、これらの返信を復号化するルールを作成することができます。 このようにすると、組織内のユーザーは、返信を表示するために暗号化ポータルにサインインする必要がなくなります。
  
Exchange メールフロールールの作成方法の詳細については、「 [Define rules For Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
  
### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用せずに電子メールメッセージを暗号化するためのメールフロールールを作成する

1. Web ブラウザーで、グローバル管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [ **管理** ] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、[**メールフロー** ] [ルール] に移動し、 \> **Rules** [新しい**New** ![ 新規作成] アイコンを選択して ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [ **名前**] にルールの名前 (DrToniRamos@hotmail.com のメールの暗号化など) を入力します。

6. **[次の場合、このルールを適用する]** で条件を選択し、必要に応じて値を入力します。たとえば、DrToniRamos@hotmail.com 宛のメッセージを暗号化するには、以下のようにします。

   1. **[次の場合、このルールを適用する]** で、**[受信者]** を選択します。

   2. 連絡先リストから既存の名前を選択するか、**[名前の確認]** ボックスに新しい電子メール アドレスを入力します。

      - 既存の名前を選択する場合は、一覧から名前を選択してから **[OK]** をクリックします。

      - 新しい名前を入力するには、[ **名前の確認** ] ボックスに電子メールアドレスを入力し、[ **名前の確認** \> **]** を選択します。

7. さらに条件を追加するには、[ **その他のオプション** ] を選択し、[ **条件の追加** ] を選択してリストから選択します。

   たとえば、受信者が組織の外部にいる場合にのみルールを適用するには、[**条件の追加**] を選択し、[**受信者が外部/内部**の \> **組織外**にある] を選択し \> **OK**ます。

8. 新しい OME 機能を使用せずに暗号化を有効にするには、 **次の操作を行い**ます。 [ **メッセージセキュリティを変更**する] [ \> **前のバージョンの OME を適用**する]、[ **保存**] の順に選択します。

   IRM ライセンスが有効になっていないというエラーが表示される場合は、従来の OME を使用していません。

9. オプション別のアクションを指定するには、[ **アクションの追加** ] を選択します。

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Exchange Online の PowerShell を使用して、新しい OME 機能なしで電子メールメッセージを暗号化するためのメールフロールールを作成する

1. Exchange Online PowerShell に接続します。 詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **New-transportrule**コマンドレットを使用してルールを作成し、 _ApplyOME_パラメーターをに設定し `$true` ます。

   この例では、DrToniRamos@hotmail.com に送信されるすべての電子メールメッセージが暗号化されている必要があります。

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   ここで

   - 新しいルールの一意の名前は、"Dr Toni Ramos の暗号化ルール" です。
   - パラメーター _に_ は、メッセージの受信者を指定します (名前、電子メールアドレス、識別名などで識別されます)。 この例では、受信者は電子メールアドレス "DrToniRamos@hotmail.com" によって識別されます。
   - /は、メッセージの受信者の場所を _指定します_ 。 この例では、受信者のメールボックスは hotmail にあり、組織の一部ではないため、値 `NotInOrganization` が使用されます。

   詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)」を参照してください。

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>新しい OME 機能を使用せずに暗号化された電子メールの返信から暗号化を削除する

電子メール ユーザーが暗号化メッセージを送信した場合、これらのメッセージの受信者は、暗号化された返信で応答することができます。 メールフロールールを作成して、返信からの暗号化を自動的に削除することで、組織内の電子メールユーザーが暗号化ポータルにサインインして表示されないようにすることができます。 これらのルールは、EAC または Windows PowerShell コマンドレットを使用して定義できます。 組織内から送信されたメッセージ、または組織内から送信されたメッセージに返信するメッセージの暗号化を解除することができます。 組織外からの暗号化されたメッセージを解読することはできません。

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>EAC を使用して、新しい OME 機能を使用せずに暗号化された電子メールの返信からの暗号化を削除するためのルールを作成する

1. Web ブラウザーで、管理者のアクセス許可が付与されている職場または学校のアカウントを使用して、 [Office 365 にサインイン](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)します。

2. [ **管理** ] タイルを選択します。

3. Microsoft 365 管理センターで、[**管理センター** ] [Exchange] を選択し \> **Exchange**ます。

4. EAC で、[**メールフロー** ] [ルール] に移動し、 \> **Rules** [新しい**New** ![ 新規作成] アイコンを選択して ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **新しいルールを作成**します。 EAC の使用方法の詳細については、「exchange [Online の exchange 管理センター](https://docs.microsoft.com/exchange/exchange-admin-center)」を参照してください。

5. [ **名前**] にルールの名前を入力します。たとえば、[受信メールからの暗号化の削除] などです。

6. [ **次の場合、このルールを適用** する] [ **受信者が** \> **組織内**にある] など、メッセージから暗号化を削除する条件を選択します。

7. [ **実行する処理**] で、[ **メッセージのセキュリティを変更する**] を選択し \> ます。 **以前のバージョンの OME を削除**します。

8. **[保存]** を選択します。

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Exchange Online PowerShell を使用して、新しい OME 機能なしで暗号化された電子メールの返信から暗号化を削除するルールを作成する

1. Exchange Online PowerShell に接続します。 詳細については、「[Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

2. **New-transportrule**コマンドレットを使用してルールを作成し、 _RemoveOME_パラメーターをに設定し `$true` ます。

   この例では、組織内の受信者に送信されるすべてのメールから暗号化を削除します。

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   ここで

   - 新しいルールの一意の名前は、"受信メールから暗号化を削除する" です。
   - /は、メッセージの受信者の場所を _指定します_ 。 この例では、値の `InOrganization` 値が使用されています。これは、次のいずれかを示しています。
     - 受信者が組織内のメールボックス、メールユーザー、グループ、またはメールが有効なパブリックフォルダーである。
     - 受信者の電子メールアドレスが、組織内の権限のあるドメインまたは内部の中継ドメインとして構成さ _れている_ 承認済みドメイン内にあり、認証された接続を介してメッセージが送信または受信された。

詳細な構文とパラメーターについては、「[New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/New-TransportRule)」を参照してください。

## <a name="sending-viewing-and-replying-to-messages-encrypted-without-the-new-capabilities"></a>新しい機能を使用せずに暗号化されたメッセージの送信、表示、および返信

Office 365 メッセージの暗号化では、管理者が定義したルールに基づいて電子メールメッセージが自動的に暗号化されます。 暗号化されたメッセージを含む電子メールが、添付の HTML ファイルと共に受信者の受信トレイに到着します。
  
受信者は、メッセージ内の指示に従って添付ファイルを開き、Office 365 に関連付けられた Microsoft アカウントまたは職場または学校を使用して認証を行います。 受信者がどちらのアカウントも持っていない場合、暗号化されたメッセージを表示するためにユーザーがサインインするための Microsoft アカウントを作成することができます。 または、受信者はメッセージを表示するための1回限りのパスコードを取得することもできます。 サインインまたはワンタイムパスコードを使用すると、受信者は復号化されたメッセージを表示し、暗号化された応答を送信できます。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>Office 365 メッセージの暗号化を使用して暗号化されたメッセージをカスタマイズする

Exchange Online および Exchange Online Protection 管理者は、暗号化されたメッセージをカスタマイズできます。 たとえば、会社のブランドとロゴを追加したり、概要を指定したり、暗号化されたメッセージや、受信者が暗号化されたメッセージを表示するポータルで、免責事項のテキストを追加したりすることができます。 Windows PowerShell のコマンドレットを使用して、暗号化された電子メール メッセージが受信者に表示される際の以下の側面をカスタマイズできます。

- 暗号化メッセージを含む電子メールの導入部のテキスト

- 暗号化メッセージを含む電子メールの免責事項のテキスト

- メッセージ表示ポータルに表示されるポータルのテキスト

- 電子メール メッセージおよび表示ポータルに表示されるロゴ

いつでも既定のルック アンド フィールに戻すこともできます。
  
以下の例は、電子メールの添付ファイルに表示される ContosoPharma のカスタム ロゴです。
  
![暗号化メッセージ ページの表示例](../media/TA-OME-3attachment2.jpg)
  
**暗号化の電子メールメッセージと暗号化ポータルを組織のブランドでカスタマイズするには**
  
1. 「リモート [Powershell を使用して Exchange online に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」の説明に従って、リモート powershell を使用して exchange online に接続します。

2. 以下の説明に従って、Set-OMEConfiguration コマンドレットを使用します。この場合、ガイダンスについ [ては、](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) 次の表を参照してください。

   **暗号化のカスタマイズ オプション**

**カスタマイズする暗号化エクスペリエンスの特性**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **例:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> サポートされているファイル形式: .png、.jpg、.bmp、.tiff  <br/> ロゴ ファイルの最適なサイズ:40 KB 未満  <br/> 最適なロゴ画像のサイズ:170x70 ピクセル  <br/> |

**暗号化の電子メールメッセージおよび暗号化ポータルからブランドのカスタマイズを削除するには**
  
1. 「リモート [Powershell を使用して Exchange online に接続する](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)」の説明に従って、リモート powershell を使用して exchange online に接続します。

2. 次の説明に従って Set-OMEConfiguration コマンドレットを使用し[ます。](https://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b) 組織のブランド化されたカスタマイズを DisclaimerText、EmailText、および PortalText の値から削除するには、値を空の文字列に設定し  `""` ます。 ロゴなどのすべてのイメージ値について、値をに設定  `"$null"` します。

   **暗号化のカスタマイズ オプション**

|**この暗号化の機能を既定のテキストと画像に戻すには**|**使用する Windows PowerShell コマンド**|
|:-----|:-----|
|暗号化された電子メール メッセージに付けられる既定のテキスト  <br/> 暗号化メッセージの表示手順の上に表示される既定のテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|暗号化メッセージを含む電子メールの免責文  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **例:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|暗号化メールの表示ポータルの最上部に表示されるテキスト  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **既定値に戻す例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|ロゴ  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **既定値に戻す例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |

## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>新しい OME 機能のリリース前の従来の Office 365 メッセージ暗号化のサービス情報
<a name="LegacyServiceInfo"> </a>

次の表では、新しい OME 機能のリリース前の Office 365 Message Encryption サービスに関する技術情報を提供します。
  
|**サービスの詳細情報**|**説明**|
|:-----|:-----|
|クライアント デバイスの要件  <br/> |暗号化されたメッセージは、Form Post をサポートする最新のブラウザーで HTML 添付ファイルを開くことができれば、任意のクライアント デバイスで表示できます。  <br/> |
|暗号化アルゴリズムと連邦情報処理規格 (FIPS) への準拠  <br/> |Office 365 Message Encryption は、Windows Azure Information Rights Management (IRM) と同じ暗号化キーを使用し、暗号化モード 2 をサポートします (RSA システム用の 2K キーと SHA-1 システム用の 256 ビット キー)。 基礎となる IRM 暗号化モードの詳細については、「 [AD RMS 暗号化モード](https://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)」を参照してください。  <br/> |
|サポートされているメッセージの種類  <br/> |Office 365 Message Encryption は、**IPM.Note** のメッセージ クラス ID があるアイテムでのみサポートされます。 詳細については、「 [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx)」を参照してください。  <br/> |
|メッセージ サイズの制限  <br/> |Office 365 Message Encryption は、25 メガバイトまでのメッセージを暗号化できます。 メッセージサイズの制限の詳細については、「 [Exchange Online の制限](https://technet.microsoft.com/library/exchange-online-limits.aspx)」を参照してください。  <br/> |
|Exchange Online の電子メールアイテム保持ポリシー  <br/> |Exchange Online は、暗号化されたメッセージを保存しません。  <br/> |
|Office 365 Message Encryption の言語サポート  <br/> | Office 365 Message encryption では、次のように Microsoft 365 言語がサポートされています。  <br/>  受信メールメッセージと添付 HTML ファイルは、送信者の言語設定に基づいてローカライズされます。  <br/>  表示するためのポータルは、受信者のブラウザーの設定に基づいてローカライズされます。  <br/>  暗号化されたメッセージの本文 (コンテンツ) は、ローカライズされません。  <br/> |
|OME ポータルと OME Viewer アプリの個人情報  <br/> |[Office 365 Messaging Encryption Portal privacy statement](https://privacy.microsoft.com/privacystatement) には、お客様の個人情報を使用して Microsoft が行うことと行わないことについて詳しく記されています。  <br/> |

## <a name="frequently-asked-questions-about-legacy-ome"></a>従来の OME についてよく寄せられる質問
<a name="LegacyServiceInfo"> </a>

Office 365 メッセージの暗号化についての質問 いくつかの答えを次に示します。 必要な情報が見つからない場合は、「 [Microsoft Tech Community フォーラム (Office 365](https://techcommunity.microsoft.com/t5/Office-365/ct-p/Office365))」を確認してください。
  
 **Q.ユーザーが暗号化された電子メールメッセージを組織外の受信者に送信します。Office 365 メッセージの暗号化で暗号化された電子メールメッセージの読み取りと返信を行うために、外部の受信者が行う必要があることはありますか。**
  
Microsoft 365 の暗号化されたメッセージを受信する組織外の受信者は、次の2つの方法のいずれかで表示できます。
  
- Office 365 に関連付けられた Microsoft アカウントまたは職場または学校のアカウントを使用してサインインします。

- ワンタイムパスコードを使用します。

 **Q.Microsoft 365 の暗号化メッセージは、クラウドまたは Microsoft サーバーに保存されますか。**
  
いいえ、暗号化されたメッセージは受信者の電子メールシステムに保持され、受信者がメッセージを開いたときに、Microsoft サーバーに表示するために一時的に投稿されます。 メッセージはそこに格納されません。
  
 **Q. 暗号化された電子メール メッセージを独自のブランドでカスタマイズすることはできますか。**
  
はい。 Windows PowerShell コマンドレットを使用して、暗号化された電子メール メッセージの上に表示する既定のテキスト、免責事項テキスト、および電子メール メッセージや暗号化ポータルに使用するロゴをカスタマイズできます。 詳細については、「[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)」を参照してください。
  
 **Q. このサービスは組織内のすべてのユーザーに対して 1 つのライセンスが必要ですか。**
  
暗号化された電子メールを送信する組織内のすべてのユーザーに対して 1 つのライセンスが必要です。
  
 **Q. 外部の受信者はサブスクリプションが必要ですか。**
  
いいえ。外部の受信者は、暗号化されたメッセージを読んで返信するためにサブスクリプションを必要としません。
  
 **Q.Office 365 メッセージの暗号化と Rights Management Services (RMS) との違い**
  
RMS は、次のような組み込みのテンプレートを提供することによって、組織の内部電子メールに関する情報権限保護機能を提供します。「転送不可」および「会社の機密」 Office 365 Message Encryption は、外部の受信者や内部の受信者に送信されるメッセージの電子メールメッセージの暗号化をサポートしています。
  
 **Q.Office 365 メッセージの暗号化と S/MIME の違い**
  
S/MIME は、基本的に、クライアント側の暗号化テクノロジであり、複雑な証明書管理と発行インフラストラクチャが必要です。 Office 365 メッセージの暗号化は、メールフロールール (トランスポートルールとも呼ばれます) を使用します。証明書の公開には依存しません。
  
 **Q. モバイル デバイスで暗号化されたメッセージを読むことはできますか。**
  
はい、Google Play ストアおよび Apple App store から OME Viewer アプリをダウンロードすることによって、Android および iOS のメッセージを表示することができます。 OME Viewer アプリの HTML 添付ファイルを開いてから、指示に従って暗号化されたメッセージを開きます。 その他のモバイル デバイスでは、メール クライアントが投稿フォームをサポートしている限り HTML 添付ファイルを開くことができます。
  
 **Q. 返信や転送されたメッセージは暗号化されますか。**
  
はい。返信はスレッド期間の間、暗号化されます。
  
 **Q.Office 365 メッセージの暗号化はローカライズを提供しますか?**
  
受信電子メールと HTML コンテンツは、送信者の電子メール設定に基づいてローカライズされます。表示ポータルは、受信者のブラウザー設定に基づいてローカライズされます。ただし、暗号化されたメッセージの本文 (コンテンツ) はローカライズされません。
  
 **Q.Office 365 メッセージの暗号化に使用される暗号化方法**
  
Office 365 メッセージの暗号化は、暗号化インフラストラクチャとして Rights Management サービス (RMS) を使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。
  
- Microsoft Azure RMS を使用してキーを取得する場合、暗号化モード2が使用されます。 暗号化モード 2 は、AD RMS 暗号実装を更新して強化した方式です。 この方式は署名と暗号化に RSA 2048 をサポートし、署名に関しては SHA-256 もサポートします。

- Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。使用される方法は、社内 AD RMS 展開によって異なります。暗号化モード 1 は、元来の AD RMS 暗号実装です。この方式は署名と暗号化に RSA 1024 をサポートし、署名に関しては SHA-1 もサポートします。このモードは、引き続き RMS の現在のすべてのバージョンでサポートされています。

詳細については、「 [AD RMS 暗号化モード](https://go.microsoft.com/fwlink/p/?LinkId=398616)」を参照してください。
  
**Q。暗号化されたメッセージが Office365@messaging.microsoft.com から送られたことを示しているのはなぜ** ですか?
  
暗号化された返信が暗号ポータルから、または OME ビューアー アプリを介して送信されるとき、送信元電子メール アドレスは Office365@messaging.microsoft.com に設定されます。暗号化メッセージは Microsoft エンドポイントを介して送信されるためです。これにより、暗号化されたメッセージがスパムとしてマークされるのを回避できます。このラベルがあるため、暗号化ポータル内の電子メールとアドレスの表示名が変更されることはありません。また、このラベルが適用されるのは、ポータルを介して送信されるメッセージだけで、他の電子メール クライアントを介して送信されるメッセージには適用されません。
  
 **Q.Exchange Hosted Encryption (EHE) サブスクライバー。Office 365 メッセージの暗号化へのアップグレードの詳細については、どこから入手できますか。**
  
EHE のすべてのお客様は、Office 365 Message Encryption にアップグレードされました。 詳細については、「 [Exchange Hosted Encryption Upgrade Center」](https://go.microsoft.com/fwlink/p/?LinkID=511077)を参照してください。
  
 **Q.Office 365 メッセージの暗号化をサポートするために、組織のファイアウォール内の Url、IP アドレス、またはポートを開く必要がありますか。**
  
はい。 Office 365 Message Encryption によって暗号化されたメッセージの認証を有効にするには、ご自分の組織の許可リストに Exchange Online の URL を追加する必要があります。 Exchange Online の Url の一覧については、「 [Microsoft 365 の url と IP アドレスの範囲](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges)」を参照してください。
  
 **Q.Microsoft 365 で暗号化されたメッセージを送信できる受信者の数**
  
受信者の制限は、メッセージあたりの受信者数が500の場合、または配布リストの展開後に、11980文字がメッセージ **の "宛先** " フィールドに設定されている場合は、最初の方になります。
  
 **Q. 特定の受信者に送信されたメッセージを取り消すことは可能ですか。**
  
いいえ。 送信されたメッセージを特定のユーザーに対して取り消すことはできません。
  
 **Q. 受信されて既読になった暗号化メッセージのレポートを表示することはできますか。**
  
暗号化されたメッセージが表示されているかどうかを示すレポートはありませんが、特定のメールフロールール (トランスポートルールとも呼ばれます) に一致したメッセージの数を特定するために利用できる Microsoft 365 レポートがあります。
  
 **Q. OME ポータルと OME Viewer アプリで提供した情報を Microsoft はどのように使用しますか。**
  
[Office 365 Messaging Encryption ポータルのプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明では、Microsoft が個人情報に対して実行する操作と行わないことについての詳細情報が提供されています。

**Q.要求した後に1回限りのパスコードを受け取っていない場合はどうすればよいですか。**

最初に、電子メールクライアントの迷惑メールまたはスパムフォルダーを確認します。 組織の DKIM および DMARC の設定により、これらの電子メールがスパムとしてフィルター処理されることがあります。

次に、セキュリティ & コンプライアンスセンターで [検疫] をチェックします。 多くの場合、1回限りのパスコードが含まれているメッセージ (特に、組織が受信する最初のコード) によって検疫が終了します。
