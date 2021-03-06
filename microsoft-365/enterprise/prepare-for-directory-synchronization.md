---
title: Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: ディレクトリ同期を使用して Microsoft 365 にユーザーをプロビジョニングするための準備方法と、この方法を使用する長期的な利点について説明します。
ms.openlocfilehash: e49cc4472b47320650d8a0ca90395b69ae5b6df7
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371626"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a>Prepare for directory synchronization to Microsoft 365 (Microsoft 365 へのディレクトリ同期を準備する)

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

組織のハイブリッド id とディレクトリ同期の利点は次のとおりです。

- 組織内の管理プログラムを減らす
- オプションでシングルサインオンのシナリオを有効にする
- Microsoft 365 でのアカウントの変更の自動化

ディレクトリ同期を使用する利点の詳細については、「 [Azure Active directory (AZURE AD) を使用したハイブリッド id](https://go.microsoft.com/fwlink/p/?LinkId=525398) 」および「 [Microsoft 365 のハイブリッド id](plan-for-directory-synchronization.md)」を参照してください。

ただし、ディレクトリ同期では、Active Directory ドメインサービス (AD DS) が、少なくとも1つのエラーを含む Microsoft 365 サブスクリプションの Azure AD テナントに同期するように計画と準備を行う必要があります。

最適な結果を得るために、以下の手順を実行します。

## <a name="1-directory-cleanup-tasks"></a>1. ディレクトリクリーンアップタスク

AD DS を Azure AD テナントと同期する前に、AD DS をクリーンアップする必要があります。

> [!IMPORTANT]
> 同期する前に AD DS のクリーンアップを実行しないと、展開プロセスに重大な悪影響を与える可能性があります。 ディレクトリ同期のサイクルを経て、エラーを特定し、再同期を実行するまでに、数日または数週間かかる場合があります。

AD DS で、Microsoft 365 ライセンスが割り当てられる各ユーザーアカウントに対して次のクリーンアップタスクを実行します。

1. **ProxyAddresses** 属性に、有効な一意の電子メールアドレスを指定します。

2. **ProxyAddresses** 属性の重複する値を削除します。

3. 可能であれば、ユーザーの **ユーザー** オブジェクトの **userPrincipalName** 属性の有効な一意の値を確認してください。 最適な同期処理を行うには、AD DS UPN が Azure AD UPN に一致していることを確認してください。 ユーザーが **userPrincipalName** 属性の値を持っていない場合は、 **ユーザー** オブジェクトに **sAMAccountName** 属性の有効な一意の値が含まれている必要があります。 **UserPrincipalName** 属性の重複する値を削除します。

4. グローバルアドレス一覧 (GAL) を最適に使用するには、AD DS ユーザーアカウントの次の属性の情報が正しいことを確認してください。

   - givenName
   - surname
   - displayName
   - 役職
   - 部署
   - 事業所
   - 事業所電話番号
   - 携帯電話番号
   - FAX 番号
   - 番地
   - 都市
   - 都道府県
   - 郵便番号
   - 国または地域

## <a name="2-directory-object-and-attribute-preparation"></a>2. ディレクトリオブジェクトと属性の準備

AD DS と Microsoft 365 の間のディレクトリ同期を正常に行うには、AD DS 属性が適切に準備されている必要があります。 たとえば、Microsoft 365 環境と同期されている特定の属性に特定の文字が使用されないようにする必要があります。 予期しない文字によってディレクトリ同期が失敗することはありませんが、警告が返されることがあります。 無効な文字は、ディレクトリ同期が失敗する原因となります。

一部の AD DS ユーザーが1つ以上の重複した属性を持っている場合も、ディレクトリ同期は失敗します。 各ユーザーは固有の属性を持つ必要があります。

準備する必要がある属性を以下に示します。

- **displayName**

  - 属性が user オブジェクトに存在する場合は、Microsoft 365 と同期されます。
  - この属性が user オブジェクトに存在する場合は、その値を指定する必要があります。 つまり、属性を空白にすることはできません。
  - 最大文字数: 256

- **givenName**

  - 属性が user オブジェクトに存在する場合、その属性は Microsoft 365 と同期されますが、Microsoft 365 では要求も使用もされません。
  - 最大文字数:64

- **mail**

  - この属性の値は、ディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 重複する値がある場合、値を持つ最初のユーザーが同期されます。 今後のユーザーは、Microsoft 365 に表示されません。 Microsoft 365 の値を変更するか、両方のユーザーを Microsoft 365 に表示するために、AD DS の両方の値を変更する必要があります。

- **mailNickname** (Exchange エイリアス)

  - 属性値はピリオド (.) で始めることはできません。
  - この属性の値は、ディレクトリ内で一意である必要があります。

    > [!NOTE]
    > 同期名のアンダスコア ("_") は、この属性の元の値に無効な文字が含まれていることを示します。 この属性の詳細については、「 [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)」を参照してください。
    >

- **proxyAddresses**

  - 複数値の属性
  - 値あたりの最大文字数: 256
  - 属性の値にスペースを含めることはできません。
  - この属性の値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: \< \> ();, [] "'

    無効な文字は、SMTP:User@contso.com が許可されていても、SMTP:user:M@contoso.com は許可されていませんが、型区切り記号の後の文字と ":" に適用されることに注意してください。

    > [!IMPORTANT]
    > すべての簡易メール転送プロトコル (SMTP) アドレスは、電子メールメッセージング標準に準拠している必要があります。 重複しているまたは不要なアドレスがある場合は削除します。

- **sAMAccountName**

  - 最大文字数:20
  - この属性の値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: [\ "|,/: \< \> + =;? \* ']
  - ユーザーの **sAMAccountName** 属性が無効で、 **userPrincipalName** 属性が有効な場合、ユーザーアカウントは Microsoft 365 で作成されます。
  - **SAMAccountName** と **userPrincipalName** の両方が無効な場合は、AD DS **userPrincipalName** 属性を更新する必要があります。

- **sn** (姓)

  - 属性が user オブジェクトに存在する場合、その属性は Microsoft 365 と同期されますが、Microsoft 365 では要求も使用もされません。

- **targetAddress**

    ユーザーに対して設定されている **targetAddress** 属性 (たとえば、SMTP:tom@contoso.com) を MICROSOFT 365 GAL に表示する必要があります。 サードパーティ製のメッセージング移行シナリオでは、AD DS の Microsoft 365 スキーマ拡張が必要になります。 また、Microsoft 365 スキーマ拡張機能は、AD DS からのディレクトリ同期ツールを使用して設定された Microsoft 365 オブジェクトを管理するための便利な属性も追加します。 たとえば、非表示のメールボックスまたは配布グループを管理する **msExchHideFromAddressLists** 属性が追加されます。

  - 最大文字数: 256
  - 属性の値にスペースを含めることはできません。
  - この属性の値は、ディレクトリ内で一意である必要があります。
  - 無効な文字: \ \< \> ();, [] "
  - すべての簡易メール転送プロトコル (SMTP) アドレスは、電子メールメッセージング標準に準拠している必要があります。

- **userPrincipalName**

  - **UserPrincipalName** 属性は、ユーザー名の後にアットマーク記号 (@) とドメイン名が続く、インターネットスタイルのサインイン形式にする必要があります。たとえば、user@contoso.com のようにします。 すべての簡易メール転送プロトコル (SMTP) アドレスは、電子メールメッセージング標準に準拠している必要があります。
  - **UserPrincipalName** 属性の最大文字数は113です。 アットマーク (@) の前後には、次のように特定の文字数が許可されます。
  - アットマーク (@) の前にあるユーザー名の最大文字数:64
  - アットマーク記号 (@) の後に続くドメイン名の最大文字数:48
  - 無効な文字: \% &amp; \* +/=? { } | \< \> ( ) ; : , [ ] "
  - 使用可能な文字: A ~ Z、a ~ z、0 ~ 9、'。 - _ ! # ^ ~
  - ウムラウト、アクセント、ティルダなどのアクセント記号の付いた文字は、無効な文字です。
  - 各 **userPrincipalName** 値には @ 文字が必要です。
  - 各 **userPrincipalName** 値の先頭文字に @ 文字を使用することはできません。
  - ユーザー名の末尾には、ピリオド (.)、アンパサンド ( &amp; )、スペース、アットマーク (@) を使用することはできません。
  - ユーザー名にスペースを含めることはできません。
  - ルーティング可能なドメインを使用する必要があります。たとえば、ローカルまたは内部のドメインを使用することはできません。
  - Unicode は、アンダースコア文字に変換されます。
  - **userPrincipalName** には、ディレクトリ内に重複する値を含めることはできません。

## <a name="3-prepare-the-userprincipalname-attribute"></a>3. userPrincipalName 属性を準備する

Active Directory は、組織内のエンドユーザーが **sAMAccountName** または **userPrincipalName** のいずれかを使用してディレクトリにサインインできるように設計されています。 同様に、エンドユーザーは、職場または学校のアカウントのユーザープリンシパル名 (UPN) を使用して、Microsoft 365 にサインインできます。 ディレクトリ同期では、AD DS 内の同じ UPN を使用して、Azure Active Directory で新しいユーザーを作成しようとしています。 UPN は、電子メールアドレスのように書式設定されます。

Microsoft 365 では、UPN は電子メールアドレスの生成に使用される既定の属性です。 **UserPrincipalName** (ad DS および Azure ad) と **proxyAddresses** のプライマリ電子メールアドレスは、異なる値に設定するのが簡単です。 複数の値が設定されている場合、管理者とエンドユーザーに混乱が生じることがあります。

これらの属性を調整して混乱を軽減することをお勧めします。 Active Directory フェデレーションサービス (AD FS) 2.0 を使用したシングルサインオンの要件を満たすには、Azure Active Directory と AD DS の Upn が一致し、有効なドメイン名前空間を使用していることを確認する必要があります。

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a>4. AD DS に代替 UPN サフィックスを追加する

ユーザーの会社の資格情報を Microsoft 365 環境に関連付けるには、代替 UPN サフィックスを追加する必要がある場合があります。 UPN サフィックスは、@ 文字の右側の UPN の一部です。 シングル サインオンに使用する UPN には文字、数字、ピリオド、ダッシュ、アンダースコアを含めることができますが、その他の種類の文字を含めることはできません。

Active Directory に代替 UPN サフィックスを追加する方法の詳細については、「 [ディレクトリ同期の準備]( https://go.microsoft.com/fwlink/p/?LinkId=525430)」を参照してください。

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a>5. AD DS UPN と Microsoft 365 UPN を一致させる

ディレクトリ同期が既にセットアップされている場合、Microsoft 365 用のユーザーの UPN は、AD DS で定義されているユーザーの AD DS UPN と一致しない可能性があります。 ドメインが確認される前にユーザーにライセンスを割り当てた場合、この状況が発生することがあります。 この問題を解決するには、PowerShell を使用して重複した [upn を修正](https://go.microsoft.com/fwlink/p/?LinkId=396730) し、MICROSOFT 365 upn が企業ユーザー名とドメインと一致するようにします。 AD DS で UPN を更新していて、Azure Active Directory id と同期する必要がある場合は、AD DS で変更を行う前に、Microsoft 365 でユーザーのライセンスを削除する必要があります。

また [、ディレクトリ同期にルーティング不能なドメイン (たとえば、ローカルドメイン) を準備する方法に](prepare-a-non-routable-domain-for-directory-synchronization.md)ついても説明します。

## <a name="next-steps"></a>次の手順

上記の手順 1 ~ 5 を実行した場合は、「 [ディレクトリ同期をセットアップ](set-up-directory-synchronization.md)する」を参照してください。
