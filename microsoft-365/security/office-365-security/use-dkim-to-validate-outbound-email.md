---
title: カスタム ドメインで DKIM をメールに使用する方法
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージが送信先のメール システムから信頼されるようにする方法を説明します。
ms.openlocfilehash: 7f9e33a6f117f5da592d875e40cefc6a0072fd4a
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126675"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a>DKIM を使用して、カスタム ドメインから送信される送信電子メールを検証する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 **概要:** この記事では、Microsoft 365 で DomainKeys Identified Mail (DKIM) を使用して、カスタム ドメインから送信されたメッセージを送信先のメール システムが信頼するようにする方法を説明します。

ドメインから送信されたように見えるメッセージをなりすまし者が送信できないようにするためには、SPF と DMARC に加え、DKIM を使用する必要があります。 DKIM を使用すると、送信電子メールのメッセージ ヘッダー内にデジタル署名を追加できるようになります。 複雑そうですが、実際には複雑ではありません。 DKIM の構成時に、関連付けるドメインを承認するか、または暗号化認証を使用して電子メール メッセージにその名前を署名します。 ドメインから電子メールを受信する電子メール システムでは、このデジタル署名を使用して、受け取った受信メールが正当であるかどうかを判断することができます。

基本的には、秘密キーを使用してドメインの送信メールのヘッダーを暗号化します。 受信側サーバーが署名のデコードに使用できるドメインの DNS レコードに、公開キーを発行します。 公開キーを使用することで、そのメッセージが送信者本人からのものであり、ドメインを *偽装* している他人からのものでないことを確認します。

Microsoft 365 では、初期ドメインの 'onmicrosoft.com' に対応する DKIM が自動的にセットアップされます。 つまり、初期ドメイン名に対応する DKIM のセットアップに関して、ユーザーは何もする必要がないということです (例: litware.onmicrosoft.com)。 ドメインの詳細については、「[ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

カスタム ドメインの DKIM に関しても、何も操作しなくて構いません。 カスタム ドメインに対応する DKIM をセットアップしていないと、Microsoft 365 が秘密キーと公開キーのペアを作成して、DKIM 署名を有効にし、カスタム ドメインに対応する Microsoft 365 の既定ポリシーを構成します。 ほとんどのユーザーの場合はこれで十分ですが、次の状況ではカスタム ドメインの DKIM を手動で構成する必要があります。

- Microsoft 365 に複数のカスタム ドメインがある場合

- DMARC も設定する場合 (推奨)

- 秘密キーを制御する場合

- CNAME レコードをカスタマイズする場合

- たとえば、サード パーティ製の大容量メーラーを使用する場合、サードパーティのドメインから発信される電子メールに DKIM キーを設定することがあります。

この記事の内容:

- [悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [DKIM を手動でセットアップする手順](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [DKIM の複数のドメインを構成するには](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [カスタム ドメインの DKIM 署名ポリシーを無効にする](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [次の手順: Microsoft 365 に SPF をセットアップした後](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a>悪意のあるスプーフィング防止の点で DKIM のしくみが SPF 単独よりも優れているといえる理由
<a name="HowDKIMWorks"> </a>

SPF ではメッセージ エンベロープに情報を追加しますが、DKIM は実際にメッセージ ヘッダー内の署名を暗号化します。メッセージを転送すると、そのメッセージのエンベロープの一部が転送サーバーによって取り除かれる可能性があります。デジタル署名は、電子メール ヘッダーの一部であるため、電子メール メッセージと共に残ります。したがって、DKIM はメッセージが転送された場合にも機能します。次の例で説明します。

![SPF チェックが失敗したときに DKIM 認証を通過した転送されたメッセージを示す図](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

この例で、ドメインに対して SPF TXT レコードしか発行しなかったとしたら、受信者のメール サーバーによってメールがスパムとしてマークされ、誤検知の結果になる可能性があります。このシナリオでは DKIM を追加することによって、誤検知のスパム報告が減少しています。DKIM は、IP アドレスだけではなく、公開キー暗号化を使って認証を行うので、SPF よりもはるかに強力な認証形態といえます。展開では DMARC だけでなく、SPF と DKIM の両方を使うことをお勧めします。

基本事項:DKIM では秘密キーを使用して、暗号化された署名をメッセージ ヘッダーに挿入します。署名ドメイン、つまり送信ドメインは、**d=** フィールドの値としてヘッダーに挿入されます。確認ドメイン、つまり受信者のドメインは、**d=** フィールドを使用して、DNS から公開キーを検索し、メッセージを認証します。メッセージが確認されれば、DKIM チェックは合格です。

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a>手動で 1024 ビット キーを 2048 ビット DKIM 暗号化キーにアップグレードする
<a name="1024to2048DKIM"> </a>

DKIM キーでは 1024 ビットと 2048 ビットの両方がサポートされています。次の手順では、1024 ビット キーを 2048 ビットにアップグレードする方法について説明します。 次の手順は、2 つのユース ケースに向けたものです。目的の構成に最適なものを選択してください。

1. **DKIM の構成が済んでいる** 場合は、次のようにしてビットを転換します。

   1. [PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。 (このコマンドレットは、Exchange Online のものです)。
   1. 次のコマンドを実行します。

      ```powershell 
      Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
      ```

1. **DKIM の新規実装** の場合は、次のようにします。

   1. [PowerShell で Office 365 のワークロードに接続します](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)。 (これは、Exchange Online コマンドレットです)。
   1. 次のコマンドを実行します。

      ```powershell
      New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True
      ```

Microsoft 365 への接続状態を維持して、構成を *検証* します。

1. 次のコマンドを実行します。

   ```powershell
   Get-DkimSigningConfig -Identity {Domain for which the configuration was set} | Format-List
   ```

> [!TIP]
> この新しい 2048 ビット キーは RotateOnDate の時点で有効になります。それまでの間は、1024 ビット キーの電子メールが送信されます。 4 日後に、2048 ビット キーで再度テストしてください (つまり、2 番目のセレクターへの転換が有効になってからテストします)。

2 番目のセレクターに転換する場合は、a) Microsoft 365 にセレクターの転換を任せて、6 か月以内に 2048 ビットへのアップグレードを実行するか、b) 4 日後に 2048 ビットが使用されていることを確認して、前述の該当するコマンドレットを使用して 2 番目のセレクター キーを手動で転換します。

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a>DKIM を手動でセットアップする手順
<a name="SetUpDKIMO365"> </a>

DKIM を構成するには、次の手順を完了します。

- [DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [カスタム ドメインに対して DKIM 署名を有効にする](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a>DNS でカスタム ドメインに対して 2 つの CNAME レコードを発行する
<a name="Publish2CNAME"> </a>

DNS の DKIM 署名を追加する各ドメインに対して、2 つの CNAME レコードを発行する必要があります。

以下のコマンドを実行してセレクター レコードを作成します。

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

Microsoft 365 の初期ドメインに加えてプロビジョニングされたカスタム ドメインがある場合には、追加の各ドメインに対して 2 つの CNAME レコードを発行する必要があります。 したがって、2 つのドメインがある場合は、2 つの追加 CNAME レコードなどを発行する必要があります。

CNAME レコードには次の形式を使用します。

> [!IMPORTANT]
> GCC High のお客様の場合、_domainGuid_ の計算方法が異なります。 _domainGuid_ を計算するために _initialDomain_ の MX レコードを参照する代わりに、カスタム ドメインから直接計算します。 たとえば、カスタム ドメインが "contoso.com" の場合、domainGuid は "contoso-com" となり、ピリオドはすべてダッシュに置き換えられます。 したがって、initialDomain が指し示す MX レコードに関係なく、CNAME レコードで使用する domainGuid は、常に上記の方法を使用して計算します。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

ここで、

- Microsoft 365 では、セレクターは常に "selector1" または "selector2" になります。

- _domainGUID_ は、mail.protection.outlook.com の前に表示される、カスタム ドメインのカスタム MX レコードの _domainGUID_ と同じです。 たとえば、次に示すドメイン contoso.com の MX レコードでは、_domainGUID_ は contoso-com です。

  > contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com

- _initialDomain_ は、Microsoft 365 へのサインアップ時に使用したドメインです。 初期ドメインの末尾は常に onmicrosoft.com です。 初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

たとえば、初期ドメイン (cohovineyardandwinery.onmicrosoft.com) と 2 つのカスタム ドメイン (cohovineyard.com と cohowinery.com) がある場合は、追加のそれぞれのドメインに対して 2 つの CNAME レコードをセットアップして、合計で 4 つの CNAME レコードをセットアップする必要があります。

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> 2 番目のレコードを作成することは重要ですが、作成時に使用できるのはセレクターのうち 1 つのみである場合があります。 本質的に、2 番目のセレクターはまだ作成されていないアドレスを指している可能性があります。 それでも、キーの交換がシームレスに行われるようになるため、2 番目の CNAME レコードを作成することをお勧めします。

> [!CAUTION]
> キーを作成する方法のいくつかのデザイン変更実装するため、自動キーのローテーションは一時的に無効になっています。 複数のキーを持つことで、定期的にローテーションさせることができます。 解読するのは困難ですが、なりすましなどから保護するための実用的な対策戦略です。 「[Rotate-DkimSigningConfig](https://docs.microsoft.com/powershell/module/exchange/rotate-dkimsigningconfig)」ドキュメントを参考にして、組織でこれを行うことができます。 自動ローテーションは 2020 年 8月より再度有効になる予定です。

### <a name="enable-dkim-signing-for-your-custom-domain"></a>カスタム ドメインに対して DKIM 署名を有効にする
<a name="EnableDKIMinO365"> </a>

DNS に CNAME レコードを発行したら、Microsoft 365 で DKIM 署名を有効にする準備が整ったことになります。 これは、Microsoft 365 管理センターか、PowerShell を使用して行うことができます。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a>管理センター経由でカスタム ドメインの DKIM 署名を有効にするには

1. 職場または学校のアカウントを使用して、[Microsoft 365 にサインイン](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)します。

2. 左上にあるアプリ起動ツールのアイコンを選択して、**[管理]** をクリックします。

3. 左下のナビゲーションで、**[管理者]** を展開し、**[Exchange]** を選択します。

4. **[保護]** \> **[dkim]** の順に移動します。

5. DKIM を有効にするドメインを選択してから、**[このドメインのメッセージに DKIM 署名で署名する]** で **[有効]** を選択します。各カスタム ドメインにこの手順を繰り返します。

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a>PowerShell を使用してカスタム ドメインの DKIM 署名を有効にするには

1. [Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. 次のコマンドを実行します。

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   ここで、 _domain_ は DKIM 署名を有効にするカスタム ドメインの名前です。

   たとえば、ドメイン名 contoso.com の場合は次のようになります。

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a>DKIM 署名が Microsoft 365 に対して適切に構成されていることを確認するには

数分待ってから、これらの手順に従って、DKIM が適切に構成されていることを確認してください。待っている間に、ドメインに関する DKIM 情報がネットワーク全体に広まります。

- Microsoft 365 の DKIM が有効になっているドメイン内のアカウントから、Outlook.com や Hotmail.com などの別の電子メール アカウントにメッセージを送信します。

- テスト目的には .aol.com アカウントは使用しないでください。AOL は SPF チェックに合格すると、DKIM チェックをスキップする場合があります。この場合、テストは成り立ちません。

- メッセージを開き、ヘッダーを確認します。メッセージのヘッダーを表示する方法は、メッセージング クライアントによって異なります。Outlook でメッセージ ヘッダーを表示する方法については、「[電子メール メッセージ ヘッダーを表示する](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)」をご覧ください。

  DKIM 署名されたメッセージには、CNAME エントリの発行時に定義したホスト名とドメインが含まれます。メッセージは、次の例のようになります。

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- 認証結果のヘッダーを確認します。各受信側のサービスでは受信メールのスタンプに若干異なる形式が使用されますが、結果には **DKIM=pass** や **DKIM=OK** などが含まれている必要があります。

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a>DKIM の複数のドメインを構成するには
<a name="DKIMMultiDomain"> </a>

後で別のカスタム ドメインを追加して、その新しいドメインに対して DKIM を有効にする場合は、各ドメインに対してこの記事の手順を完了する必要があります。 具体的には、「[DKIM を手動でセットアップする方法](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)」のすべての手順を完了します。

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a>カスタム ドメインの DKIM 署名ポリシーを無効にする 
<a name="DisableDKIMSigningPolicy"> </a>

署名ポリシーを無効にしても、DKIM は完全には無効になりません。 一定の期間が経過すると、Microsoft 365 はドメインの既定のポリシーを自動的に適用します。 詳細については「[DKIM と Microsoft 365 の既定の動作](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)」をご覧ください。

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a>Windows PowerShell を使用して DKIM 署名ポリシーを無効にするには

1. [Exchange Online PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

2. DKIM 署名を無効にする各ドメインに対して次のいずれかのコマンドを実行します。

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   次に例を示します。

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   または

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   ここで、 _number_ はポリシーのインデックスです。 以下に例を示します。

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a>DKIM と Microsoft 365 の既定の動作
<a name="DefaultDKIMbehavior"> </a>

DKIM を有効にしない場合、Microsoft 365 は既定のドメインに対して 1024 ビットの DKIM 公開キーと、それに関連する秘密キー (これはデータセンターに内部的に保存されます) を作成します。 既定では、Microsoft 365 は、所定のポリシーを持たないドメインに対して既定の署名構成を使用します。 これは、ユーザーが DKIM をセットアップしなければ、Microsoft 365 が、その既定のポリシーと、自らが作成するキーを使用して、そのドメインに対して DKIM を有効にすることを意味しています。

また、DKIM 署名を有効にしてから無効にした場合にも、一定の期間が過ぎると、Microsoft 365 が自動的にドメインに対して既定のポリシーを適用します。

次の例では、fabrikam.com の DKIM が、ドメインの管理者ではなく、Microsoft 365 によって有効にされていることを想定しています。 これは、必須の CNAME が DNS に存在しないことを意味します。 このドメインからのメールの DKIM 署名は、次のようなものになります。

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

この例のホスト名とドメインには、fabrikam.com の DKIM 署名がドメイン管理者によって有効にされた場合に CNAME が指し示す値が含まれています。 最終的には、Microsoft 365 から送信されるすべてのメッセージは DKIM 署名されたメッセージになります。 自分で DKIM を有効にしている場合、ドメインは From: アドレス内のドメインと同じになります (この場合は fabrikam.com)。 自分で DKIM を有効にしない場合は、ドメインは同じにならず、代わりに組織の初期ドメインが使用されます。 初期ドメインを決定する方法の詳細については、「 [ドメインに関する FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain)」を参照してください。

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a>サードパーティのサービスがカスタム ドメインに代わって電子メールを送信つまり偽装できるように DKIM を設定する
<a name="SetUp3rdPartyspoof"> </a>

一部の一括電子メール サービス プロバイダー、または Software-as-a-Service プロバイダーでは、サービスから送信される電子メールに DKIM キーを設定できます。この場合、必要な DNS レコードを設定するために自分とサードパーティの間で調整が必要です。一部のサードパーティ サーバーは、異なるセレクターを持つ独自の CNAME レコードを持つことがあります。まったく同じ方法を用いる組織は 2 つとなく、プロセスは完全に組織に依存します。

contoso.com および bulkemailprovider.com 用に適切に構成された DKIM を示すメッセージの例は、次のようになります。

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

この例では、この結果を達成するために、次を実行しました。

1. 一括電子メール プロバイダーは、Contosoc に DKIM の公開キーを付与しました。

2. Contoso は、その DNS レコードに DKIM キーを発行しました。

3. 電子メールを送信する場合、一括電子メール プロバイダーは対応する秘密キーを使用してキーに署名しました。これにより、一括電子メール プロバイダーはメッセージ ヘッダーに DKIM 署名を添付します。

4. 受信側の電子メールシステムでは、メッセージの From: (5322.from) アドレスのドメインに対して DKIM-Signature d=\<domain\> 値を認証することによって DKIM チェックを実行します。 この例では、次の値が一致します。

   > sender@**contoso.com**

   > d=**contoso.com**
   
## <a name="identify-domains-that-do-not-send-email"></a>メールを送信しないドメインを特定する

組織は、ドメインのDKIM レコードで`v=DKIM1; p=`を指定して、そのドメインがメールを送信しないことを明示的に述べる必要があります。 これにより、そのドメインには有効な公開鍵が存在しないことをメール受信サーバーに知らせ、そのドメインからのメールを拒否するように、要求します。 ワイルドカード DKIM を使用して、ドメインとサブドメインごとにこの操作を実行する必要があります。

たとえば、DKIM レコードは次のようになります。

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a>次の手順: Microsoft 365 に SPF をセットアップした後
<a name="DKIMNextSteps"> </a>

DKIM はスプーフィングを防止するように設計されていますが、SPF と DMARC を併用すると DKIM はより有効に機能します。 DKIM をセットアップした後、まだ SPF を構成していなければ、SPF を構成する必要があります。 SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。 Microsoft 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。 次は、「[DMARC を使用してメールを検証する](use-dmarc-to-validate-email.md)」を参照してください。 [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md)には、Microsoft 365 が KIM チェックに使用する構文とヘッダー フィールドが含まれています。
