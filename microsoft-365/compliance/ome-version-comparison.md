---
title: メッセージ暗号化 (OME) バージョンの比較
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: この記事では、Office 365 メッセージの暗号化の各バージョンの違いについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a52d0c0164dfddb9f678bffa088760a271bc28e3
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754131"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

この記事では、従来の Office 365 Message Encryption (OME) を、新しい OME 機能と Office 365 Advanced Message Encryption と比較します。 新機能は、OME と Information Rights Management (IRM) の両方の合併およびより新しいバージョンです。 GCC High への展開に関する固有の特性についても概説します。 2つのを組織内で共存させることができます。 新機能のしくみについては、「 [Office 365 Message Encryption (OME)](ome.md)」を参照してください。

||
|:-----|
|この記事は、Office 365 メッセージの暗号化についてのより大きな一連の記事の一部です。 この記事は、管理者および It 担当者を対象としています。 暗号化されたメッセージの送信または受信に関する情報をお探しの場合は、「 [Office 365 Message Encryption (OME)](ome.md) 」の記事の一覧を参照し、ニーズに最も適した記事を見つけてください。 |
||

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>機能と機能の並行比較

|                                   |以前の機能       |                   |新機能              |
|-----------------------------------|-------------------|-------------------|--------------------------|
|**機能**                     | **レガシー OME**    | **IRM**           | **OME の新機能** |
|*暗号化されたメールを送信する*        |Exchange メールフロールールを使用する|エンドユーザーが Outlook デスクトップまたは Outlook on the Web から開始しました。または Exchange メールフロールールを介して|エンドユーザーが Outlook デスクトップ、Outlook for Mac、または Outlook on the Web から開始しました。Exchange メールフロールール (トランスポートルールとも呼ばれます) とデータ損失防止 (DLP) を使用します。|
|*Rights management テンプレート*       |   N/A      |オプションとカスタムテンプレートを転送しない|転送しないオプション、Encrypt-Only オプション、およびカスタムテンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|Outlook クライアントでのネイティブインライン環境|Outlook クライアントを使用した同じ組織内の受信者に対するネイティブなインライン作業。  受信者は、Outlook 以外のクライアントを使用して OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*外部の受信者のための環境*|受信者が HTML メッセージを受信し、web ブラウザーまたはモバイルアプリでそれをダウンロードして開く|N/A|Microsoft 365 受信者のネイティブインライン環境。 他のすべての受信者は OME ポータルからメッセージを読み取ることができます (ダウンロードまたはアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルに制限はありません。|添付ファイルが保護されている|添付ファイルは、[転送不可] オプションおよびカスタムテンプレートに対して保護されています。 管理者は、Encrypt-Only オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (BYOK) のサポートを利用する*|なし                |なし               |BYOK サポート          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME に比べた新しい OME 機能の利点

新機能には、次のような利点があります。

- Encrypt-Only (安全なコラボレーションを可能にする)、転送不可、およびカスタム制限を使用できます。
- 送信者は、新しい機能で暗号化されたメールを Outlook デスクトップ、Outlook for Mac、web クライアントの Outlook から手動で送信できます。
- Microsoft 365 の受信者は、サポートされている Outlook クライアントでインライン表示を使用することができます。 または、管理者が Microsoft 365 の受信者をブランド化された環境で表示することを選択できます。
- Gmail、Yahoo、Microsoft accounts などの Microsoft 365 の外側にあるアカウントは、OME ポータルと連携しています。これにより、これらの受信者にとってより良いユーザー環境が提供されます。 その他のすべての id は、1回限りのパスコードを使用して暗号化されたメッセージにアクセスします。
- 管理者はブランド化をカスタマイズし、複数のブランド設定テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消すことができます。
- 新しい機能は、セキュリティコンプライアンスセンターを通じて詳細な利用状況レポートを提供し &amp; ます。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 の高度なメッセージ暗号化機能

Office 365 Advanced Message Encryption は、新しい OME 機能の上部に追加機能を提供します。 高度なメッセージ暗号化機能を使用するには、組織内に新しい Office 365 メッセージ暗号化機能が設定されている必要があります。 また、これらの機能を使用するためには、受信者は OME ポータルを使用して、セキュリティで保護されたメールを表示して返信する必要があります。 高度な機能は次のとおりです。

- メッセージの取り消し

- メッセージの有効期限

- 複数ブランド化テンプレート

Office 365 の高度なメッセージの暗号化は、GCC High ではサポートされていません。

高度なメッセージ暗号化の使用の詳細については、「 [Office 365 Advanced Message encryption](ome-advanced-message-encryption.md)」を参照してください。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC 高展開での Office 365 メッセージ暗号化の固有の特徴

GCC の高環境で Office 365 メッセージ暗号化を使用することを計画している場合は、受信者の利便性に関して独自の特徴がいくつかあります。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC High および GCC の高受信者間での暗号化された電子メール

送信者は、Outlook for PC および Mac および web 上の Outlook でメールを手動で暗号化できます。また、Exchange メールフロールールを使用して電子メールを暗号化するポリシーを設定することもできます。

GCC の内部にいる受信者は、PC と Mac 用の Outlook と、その他すべてのユーザーとしての web 上の Outlook で、同じインライン読み取り操作を受け取ります。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC 高および非 GCC の高受信者間での暗号化された電子メール

GCC の内部にある送信者は、暗号化された電子メールを GCC の広い境界の外部に送信できます。またはその逆もあります。

市販の Microsoft 365 ユーザー、Outlook.com ユーザー、その他の電子メールプロバイダー (Gmail、Yahoo など) を含む、GCC 以外のすべての受信者には、ラッパーメールが送信されます。 このラッパーメールは、受信者がメッセージを読んで返信できるようにするために、OME ポータルに受信者をリダイレクトします。 これは、OME の暗号化されたメールを GCC High に送信する GCC の外部の送信者にも当てはまります。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と、同じテナント内の新機能の共存

従来の OME と新機能の両方を同じテナントで使用できます。 管理者として、メールフロールールの作成時に使用する OME のバージョンを選択することによって、これを行います。

- 以前のバージョンの OME を指定するには、Exchange メールフロールールの動作を使用します。 **以前のバージョンの OME を適用**します。

- 新しい機能を指定するには、Exchange メールフロールールのアクションを使用して、 **Office 365 メッセージの暗号化および権限保護を適用**します。

ユーザーは、Outlook デスクトップ、Outlook for Mac、および Outlook on the web を使用して、新しい機能で暗号化されたメールを手動で送信できます。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新機能への移行

両方のバージョンの OME を共存させることができますが、ルールのアクションを使用する古いメールフロールールを編集して、新しい機能を使用するには、 **以前のバージョンの OME を適用** することを強くお勧めします。 メールフロールールのアクションを使用するようにこれらのルールを更新する **Office 365 メッセージの暗号化および権限保護を適用**します。 手順については、「 [Office 365 で電子メールメッセージを暗号化するためのメールフロールールの定義](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、新しい OME 機能は組織に対して自動的に有効になります。 組織内の新しい OME 機能の詳細については、「 [Office の新しい365メッセージの暗号化機能をセットアップ](set-up-new-message-encryption-capabilities.md)する」を参照してください。

Azure Information Protection を有効にしている場合、OME のレガシバージョンが自動的に有効になります。 以前は、Azure Information Protection が有効になっていない場合でも、従来の OME は動作していました。 このような場合は、これで終了です。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、ルールの動作を使用するメールフロールールを構成します。 **以前のバージョンの OME を適用**します。 手順については、「メール [フロールールを定義して電子メールメッセージを暗号化する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
