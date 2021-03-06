---
title: 高度なメッセージ暗号化で暗号化された電子メールを取り消す
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: 管理者およびメッセージ送信者として、Office 365 Advanced Message Encryption で暗号化された特定の電子メールを取り消すことができます。
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868952"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>高度なメッセージ暗号化で暗号化された電子メールを取り消す

電子メールの取り消しは、Office 365 Advanced Message Encryption の一部として提供されます。 Office 365 の高度なメッセージの暗号化は、 [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home)、Office 365 E5、Microsoft 365 E5 (非営利団体の価格)、Office 365 Enterprise E5 (非営利スタッフの価格)、office の365教育用 A5 に含まれています。 Office 365 Advanced Message Encryption が含まれていないサブスクリプションが組織にある場合は、microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Microsoft 365 E3、Microsoft 365 E3 (非営利スタッフ価格)、または Office の 365 Sku で、Microsoft 365 E5 コンプライアンス SKU アドオンを使用して購入できます。

この記事は、 [Office 365 メッセージの暗号化](ome.md)についてのより大きな一連の記事の一部です。

Office 365 Advanced Message Encryption を使用してメッセージが暗号化されていて、Microsoft 365 管理者またはメッセージの送信者である場合は、特定の条件下でメッセージを取り消すことができます。 管理者が PowerShell を使用してメッセージを取り消します。 送信者は、Outlook on the web から直接送信したメッセージを取り消します。 この記事では、失効が可能な状況とその方法について説明します。
  
## <a name="encrypted-emails-that-you-can-revoke"></a>取り消すことができる暗号化された電子メール

管理者およびメッセージの送信者が、リンクベースの、ブランド化された電子メールを受信した場合、暗号化された電子メールを取り消すことができます。 受信者が、サポートされている Outlook クライアントでネイティブインライン環境を受信した場合、メッセージを取り消すことはできません。

受信者がリンクベースの機能を受信するか、またはインラインでの使用を許可するかは、受信者の id の種類によって異なります。 Office 365 と Microsoft アカウントの受信者 (たとえば、outlook.com users) は、サポートされている Outlook クライアントでインラインの動作を取得します。 Gmail、Yahoo 受信者など、他のすべての受信者の種類は、リンクベースの処理を行います。

管理者およびメッセージ送信者は、Outlook on the web から直接適用される暗号化を使用して暗号化されたメッセージを取り消すことができます。 たとえば、[暗号化のみ] オプションで暗号化されたメッセージです。

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Outlook on the web の [暗号化のみ] オプションを示すスクリーンショット。":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>取り消された暗号化された電子メールの受信者向けの手順

電子メールが失効されると、受信者は Office 365 メッセージ暗号化ポータルを経由して暗号化された電子メールにアクセスしたときにエラーを受信します。 "メッセージは送信者によって取り消されました"。

![取り消された暗号化された電子メールを示すスクリーンショット。](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>送信した暗号化されたメッセージを取り消す方法

送信した暗号化されたメッセージを取り消すには、次の手順を実行します。

1. Web 上の Outlook の [ **送信済みアイテム** ] フォルダーで、取り消したいメッセージを参照します。

   メールが revocable の場合は、メッセージの上部にある [外部アクセスの削除] リンクが表示されます。

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Outlook on the web で取り消したい暗号化されたメールを示すスクリーンショット。":::

2. [ **外部アクセスの削除** ] をクリックして、メッセージを取り消します。

   メッセージは、状態が [失効済みであることを示しています。

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Outlook on the web で暗号化されたメッセージが取り消されたことを示すスクリーンショット。":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>暗号化されたメッセージを管理者として取り消す方法

Microsoft 365 管理者は、次の一般的な手順に従って、対象となる暗号化された電子メールを取り消します。

- 電子メールのメッセージ ID を取得します。
- メッセージを取り消すことができることを確認します。
- メールを取り消します。

### <a name="step-1-obtain-the-message-id-of-the-email"></a>手順 1. 電子メールのメッセージ ID を取得する

暗号化されたメールを取り消すには、メールのメッセージ ID を収集します。 MessageId は通常、次の形式になります。

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

取り消したい電子メールのメッセージ ID を複数の方法で見つけることができます。 このセクションでは、いくつかのオプションについて説明しますが、ID を提供する任意の方法を使用できます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>セキュリティ/コンプライアンスセンターのメッセージ追跡を使用して取り消す電子メールのメッセージ ID を特定するには &amp;

1. [セキュリティ & コンプライアンスセンターで、新しいメッセージの追跡](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)を使用して、送信者または受信者によって電子メールを検索します。

2. 電子メールを見つけたら、それを選択して **メッセージ追跡の詳細** ウィンドウを開きます。 **詳細情報**を展開して、メッセージ ID を見つけます。

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>セキュリティ/コンプライアンスセンターで Office メッセージの暗号化レポートを使用して取り消す電子メールのメッセージ ID を特定するには &amp;

1. セキュリティ &amp; /コンプライアンスセンターで、[メッセージの **暗号化] レポート**に移動します。 このレポートの詳細については、「 [セキュリティ &amp; センターのコンプライアンスセンターで電子メールのセキュリティレポートを表示する](../security/office-365-security/view-email-security-reports.md)」を参照してください。

2. [ **詳細の表示** ] テーブルを選択し、取り消すメッセージを識別します。

3. メッセージをダブルクリックして、メッセージ ID を含む詳細を表示します。

### <a name="step-2-verify-that-the-mail-is-revocable"></a>手順 2。 メールが revocable かどうかを確認する

メッセージを取り消すことができるかどうかを確認するには、セキュリティコンプライアンスセンターの **詳細** 表で、[失効状態] フィールドが [暗号化] レポートに表示されているかどうかを確認し &amp; ます。

Windows PowerShell を使用して特定の電子メールメッセージを取り消すことができるかどうかを確認するには、次の手順を実行します。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。 手順については、「[Exchange Online PowerShell に接続する](https://aka.ms/exopowershell)」を参照してください。

2. 次のコマンドレットを実行します。

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   このコマンドは、メッセージの件名と、メッセージが revocable であるかどうかを返します。 例えば、

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>手順 3. メールを取り消す

取り消したい電子メールのメッセージ ID がわかっていて、そのメッセージが revocable であることを確認したら、セキュリティ &amp; コンプライアンスセンターまたは Windows PowerShell を使用して電子メールを取り消すことができます。

セキュリティ/コンプライアンスセンターを使用してメッセージを取り消すには &amp;

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、セキュリティ & コンプライアンスセンターに接続します。

2. [ **暗号化レポート**] の [メッセージの **詳細** ] テーブルで、[ **メッセージの取り消し**] を選択します。

Windows PowerShell を使用して電子メールを失効させるには、OMEMessageRevocation コマンドレットを使用します。

1. 組織で全体管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Exchange Online PowerShell に接続](https://aka.ms/exopowershell)します。

2. OMEMessageRevocation コマンドレットを次のように実行します。

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. 電子メールが失効したかどうかを確認するには、次のようにして、次のコマンドレットを実行します。

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    失効が成功した場合、コマンドレットは次の結果を返します。  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Office 365 の詳細なメッセージの暗号化に関する詳細情報

- [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)

- [Office 365 の高度なメッセージの暗号化-電子メールの有効期限](ome-advanced-expiration.md)

- [メッセージポリシーとコンプライアンスサービスの説明](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
