---
title: EOP のメールフロールール
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: メールフロールール (トランスポートルール) を使用して、組織を通過するメッセージを識別し、処理を行うことができます。
ms.openlocfilehash: 11bf2af56c6e85c868e2e0726736f624e196805c
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021051"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>スタンドアロン EOP のメール フロー ルール (トランスポート ルール)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 組織では、メールフロールール (トランスポートルールとも呼ばれます) を使用して、組織を通過するメッセージを識別し、処理を行うことができます。

このトピックでは、メールフロールールのコンポーネントとその機能について説明します。

メールフロールールを作成、コピー、管理する手順については、「 [Exchange Online でメールフロールールを管理](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)する」を参照してください。 ルールごとに、ルールを適用、ルールをテスト、ルールをテストして送信者に通知するという、いずれかのオプションを選択できます。 テストオプションの詳細については、「 [Exchange Online の](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)[メールフロールール](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules)とポリシーヒントをテストする」を参照してください。

メールフロールールに一致したメッセージに関する概要と詳細のレポートについては、「 [メール保護レポートを使用してマルウェア、スパム、ルールの検出に関するデータを表示する](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)」を参照してください。

メール フロー ルールを使用して特定のメッセージング ポリシーを実装するには、次のトピックを参照してください。

- [メールフロールールを使用して Exchange Online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Office 365 Enterprise で暗号化を設定する](../../compliance/set-up-encryption.md)

- [Exchange Online の組織全体のメッセージの免責事項、署名、フッター、またはヘッダー](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [EOP で受信拒否リストを作成する](create-block-sender-lists-in-office-365.md)

- [Exchange Online Protection でファイルの添付のブロックを通じてマルウェアの脅威を削減する](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Office 365 で電子メールメッセージを暗号化または暗号化解除するルールを定義する](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

次のビデオは、スタンドアロン EOP でのメールフロールールの設定のデモを示しています。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>メール フロー ルールの構成要素

メール フロー ルールは条件、例外、アクション、プロパティからできています。

- **条件** : アクションを適用するメッセージを識別します。 一部の条件は、メッセージ ヘッダー フィールド (例、宛先、差出人、または CC フィールド) を確認します。 その他の条件はメッセージ プロパティ (例、メッセージの件名、本文、添付ファイル、メッセージ サイズ、またはメッセージ分類) を確認します。 ほとんどの条件は、比較演算子 (例、次と一致する、次と一致しない、または次が含まれる) と一致する値を指定する必要があります。 条件または例外が 1 つもない場合、ルールはすべてのメッセージに適用されます。

スタンドアロン EOP のメールフロールール条件の詳細については、「 [Exchange Online でのメールフロールールの条件と例外 (述語)](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)」を参照してください。

- **例外** : アクションが適用されないメッセージを指定します (オプション)。 条件で使用可能なメッセージ識別子と同じものが、例外でも使用可能です。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメッセージにルール アクションが適用されないようにします。

- **Actions** : ルールの条件に一致するメッセージに対して行う操作を指定し、いずれの例外にも一致しないようにします。 例外は条件より優先され、メッセージが構成されているすべての条件に一致していても、そのメール メッセージにアクションが適用されないようにします。

スタンドアロン EOP で使用できるメールフロールールの処理の詳細については、「 [Exchange Online のメールフロールールのアクション](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」を参照してください。

- **プロパティ** : 条件、例外、またはアクションではない他のルール設定を指定します。 たとえば、いつルールを適用するか、ルールを強制するか、あるいはテストするかどうか、およびルールを有効化する期間などです。

  詳細に関しては、このトピックの「[メール フロー ルールのプロパティ](#mail-flow-rule-properties)」セクションを参照してください。

### <a name="multiple-conditions-exceptions-and-actions"></a>複数の条件、例外、アクション

Use a transport rule so messages can bypass Clutter

****

|コンポーネント|ロジック|コメント|
|---|---|---|
|コメント|および|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、特定のテキストを含んでいるメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。EAC においては、ルールは簡単にコピーできます。|
|メッセージは、ルールのすべての条件に一致しなければなりません。別々の条件に一致させる必要がある場合は、条件ごとに個別のルールを使用します。たとえば、ファイルが添付されたメッセージと、コンテンツがパターンと一致するメッセージに同じ免責事項を追加するには、それぞれの条件ごとに 1 つのルールを作成します。ルールは簡単にコピーできます。|または|条件によっては、複数の値を指定できる場合もあります。メッセージは指定された値の任意の 1 つ (すべてではない) に一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、 **[件名に次のいずれかの語が含まれている場合]** という条件が「 Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に値が少なくとも 1 つは含まれているので、この条件は満たされています。  |
|条件によっては、複数の値を指定できる場合もあります。1 つの条件に複数の値を入力できる場合、メッセージはその条件で指定された値のいずれかに一致する必要があります。たとえば、メール メッセージの件名が「株価情報」で、トランスポート ルールの [件名に次のいずれかの語が含まれている場合] という条件が「Contoso」または「株」のいずれかの単語に一致するよう構成されていたとすると、件名に条件の値が少なくとも 1 つは含まれているので、この条件は満たされています。|または|メッセージがいずれか 1 つの例外に一致すると、アクションはメッセージに適用されません。メッセージがすべての例外に一致する必要はありません。|
|メッセージがいずれかの例外に一致すると、アクションは実行されません。メッセージが、すべての例外に一致する必要はありません。|および|ルールの条件に一致するメッセージには、ルールに指定されるすべてのアクションが実行されます。たとえば、 **[メッセージの件名の先頭に付加する]** というアクションと、 **[受信者を BCC ボックスに追加する]** というアクションが選択されている場合、両方のアクションがメッセージに適用されます。  <p> ルールの条件に一致するメッセージには、そのルールで指定されたすべてのアクションが実行されます。たとえば、[メッセージの件名の先頭に付加する] というアクションと、[受信者を BCC ボックスに追加する] というアクションが選択されている場合、両方のアクションがメッセージに適用されます。メッセージには、メッセージの件名の先頭に指定の文字列が追加され、指定された受信者が BCC 受信者として追加されます。<p> ルールにアクションを設定して、そのルールが適用されたときに、メッセージにそれ以降のルールの適用されないようにすることもできます。|
|

### <a name="mail-flow-rule-properties"></a>メール フロー ルールのプロパティ

次の表で、メール フロー ルールで使用可能なルールのプロパティについて説明します。

****

|EAC におけるプロパティ名|PowerShell におけるパラメーター名|説明|
|---|---|---|
|**[優先度]**|_Priority_|メッセージにルールを適用する順番を示します。優先度の既定値はルールの作成時期に基づいています (古いルールのほうが新しいルールより優先度が高く、優先度の高いルールが優先度の低いルールよりも先に処理されます)。   <p> EAC 内でのルールの優先度は、ルール一覧内でそのルールを上下に移動させることで変更します。 PowerShell では、優先度番号を設定します (0 が最高優先度)。 <p> たとえば、クレジット カード番号が含まれるメッセージを拒否するルールと、承認を必要とする別のルールがある場合、拒否のルールを最初に適用して、他のルールの適用を停止する必要があります。  |
|**[モード]**|_Mode_|ルールにすぐにメッセージの処理を開始させるか、あるいはメッセージの配信に影響を与えずにルールをテストするかどうかを指定することができます (データ紛失防止、DLP ポリシー ヒントの有無を問わず)。 <p> ポリシー ヒントは、メッセージを作成しているユーザーにそれがポリシー違反の可能性があることを通知する短いメモを、Outlook または Web 上の Outlook で提示します。詳細については、「 **Policy Tips** 」を参照してください。  <p> モードの詳細については、「 **Test a mail flow rule** 」を参照してください。|
|**次の日付でこのルールを有効にする** <p> **次の日付に、このルールを無効にする**|_ActivationDate_ <p> _ExpiryDate_|ルールが有効化される日付の範囲を指定します。|
|選択されているかどうかに関わらず、チェック ボックスを **オン** にします。|新しいルール: **new-transportrule** コマンドレットの _Enabled_ パラメーター。 <p> 既存のルール: **Enable-TransportRule** または **Disable-TransportRule** コマンドレットを使用します。 <p> 値はルールの **State** プロパティに表示されます。|無効なルールを作成して、それをテストする準備ができたときに有効にすることができます。または、設定を保持するために削除することなくルールを無効にすることができます|
|**[ルール処理が完了しない場合メッセージを優先する]**|_RuleErrorAction_|ルール処理が完了しない場合にメッセージをどのように扱うかを指定することができます。既定値ではルールは無視されますが、処理のためにメッセージを再送信することを選択できます。|
|**メッセージの送信者アドレスを一致**|_SenderAddressLocation_|ルールが送信者のメール アドレスを確認する例外や条件を使用する場合、メッセージ ヘッダー、メッセージのエンベロープ、またはその両方の値を検索できます。|
|**[ルールの処理を中止する]**|_SenderAddressLocation_|これはルールのアクションですが、EAC でのプロパティのように見えます。ルールがメッセージを処理した後に、追加のルールが適用されないように選択できます。|
|**コメント**|_Comments_|ルールに関する説明的なコメントを入力することができます。|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>メッセージへのメール フロー ルールの適用方法

組織を通過するすべてのメッセージが、組織内の有効にされているメール フロー ルールについて評価されます。 ルールは、EAC の [ **メールフロー** ルール] ページに示されている順序で処理される \> **Rules** か、または PowerShell 内の対応する _Priority_ パラメーターの値に基づいて処理されます。

各ルールでは、そのルールが一致した場合に、以降のルールの処理を停止するオプションを選択できます。この設定は、メッセージが複数のメール フロー ルールの条件に一致する場合に重要です (メッセージにどのルールを適用しますか?すべてですか?1 つだけですか?)。

### <a name="differences-in-processing-based-on-message-type"></a>メッセージの種類による処理の違い

組織を通過するメッセージにはいくつかの種類があります。次の表に、メール フロー ルールで処理できるメッセージの種類を示します。

****

|組織を通過するメッセージにはいくつかの種類があります。次の表に、トランスポート ルールで処理できるメッセージの種類を示します。|メッセージの種類|
|---|---|
|**通常のメッセージ** : 単一のリッチテキスト形式 (RTF)、HTML、プレーンテキストのメッセージ本文、またはメッセージ本文のマルチパートまたは代替セットが含まれるメッセージ。|必要|
|**Office 365 メッセージ暗号化** : office 365 での Office 365 メッセージの暗号化によって暗号化されたメッセージ。 詳細については、「[Office 365 での暗号化](https://docs.microsoft.com/microsoft-365/compliance/encryption)」をご覧ください。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> 暗号化されたメッセージの内容を検査または変更するルールについては、トランスポート復号化が有効になっていることを確認する必要があります (必須またはオプション)。既定値はオプションです。 詳細については、「 [Office 365 で電子メールメッセージを暗号化または暗号化解除するルールを定義する](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)」を参照してください。|
|**S/MIME 暗号化されたメッセージ**|ルールは、エンベロープ ヘッダーにのみアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> メッセージ コンテンツの検査を必要とする条件を使用したルール、またはメッセージのコンテンツを変更するアクションを処理することはできません。|
|**RMS で保護されたメッセージ** : Active Directory Rights management サービス (AD RMS) または Azure Rights MANAGEMENT (RMS) ポリシーが適用されているメッセージ。|ルールは常にエンベロープ ヘッダーにアクセスでき、それらのヘッダーを検査する条件に基づいてメッセージを処理できます。 <p> RMS で保護されたメッセージの内容を検査または変更するルールについては、トランスポート復号化が有効になっていることを確認する必要があります (必須または任意、既定値はオプション)。|
|**クリア署名付きメッセージ** : 署名されているが、暗号化されていないメッセージ。|必要|
|**UM メッセージ** : ボイスメール、fax、不在着信通知などのユニファイドメッセージングサービスによって作成または処理されたメッセージ、および Microsoft Outlook voice Access を使用して作成または転送されたメッセージ。|必要|
|**匿名メッセージ** : 匿名送信者によって送信されたメッセージ。|必要|
|**閲覧レポート** : 送信者からの開封確認要求に対する応答として生成されるレポート。 閲覧レポートには、またはのメッセージクラスがあり `IPM.Note*.MdnRead` `IPM.Note*.MdnNotRead` ます。|必要|
|

## <a name="what-else-should-i-know"></a>その他の注意事項

- ルールの **バージョン** または **ruleversion** プロパティの値は、Exchange Online Protection では重要ではありません。

- メール フロー ルールを作成または変更した後に、新規または更新されたルールがメッセージに適用されるまで、最大で 30 分かかります。

## <a name="for-more-information"></a>詳細情報

[メールフロールールを使用して Exchange Online のメッセージの添付ファイルを検査する](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Office 365 での電子メールの暗号化](../../compliance/email-encryption.md)

[ジャーナル、トランスポート、受信トレイのルール上の制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
