---
title: Microsoft 365 でアーカイブの余裕期間のデータにコネクタを設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 管理者は、Globanet の余裕期間から Microsoft 365 にデータをインポートしてアーカイブするためのコネクタを設定できます。 このコネクタを使用すると、Microsoft 365 でサードパーティのデータソースからデータをアーカイブできるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 6466beb6115037ff726b1e5fd3350032bceb2230
ms.sourcegitcommit: a3c2c737995088c1bad3b12ab401a7ef242b0272
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47957041"
---
# <a name="set-up-a-connector-to-archive-slack-data-preview"></a>アーカイブの余裕期間のデータへのコネクタの設定 (プレビュー)

Microsoft 365 コンプライアンスセンターの Globanet コネクタを使用して、ソーシャルメディア、インスタントメッセージング、およびドキュメントコラボレーションプラットフォームから Microsoft 365 組織のメールボックスにサードパーティのデータをインポートし、アーカイブします。 Globanet は、Microsoft 365 コンプライアンスセンターで、サードパーティのデータソースからアイテムを取得するように構成できる (定期的に) [余裕期間データコネクタ](https://globanet.com/slack/) コネクタを提供し、それらのアイテムを microsoft 365 にインポートします。 余裕期間は、メッセージとファイルを余裕期間 API から取得し、電子メールメッセージ形式を変換して、Microsoft 365 のユーザーメールボックスにインポートします。

余裕期間のデータがユーザーのメールボックスに格納されている場合は、訴訟ホールド、電子情報開示、アイテム保持ポリシー、保持ラベル、および通信コンプライアンスなどの Microsoft 365 コンプライアンス機能を適用できます。 余裕期間コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることにより、組織は政府および規制ポリシーに準拠したままにすることができます。

## <a name="overview-of-archiving-slack-data"></a>アーカイブ余裕期間データの概要

次の概要では、コネクタを使用して、Microsoft 365 で余裕期間情報をアーカイブするプロセスについて説明します。

![余裕期間のアーカイブワークフロー](../media/SlackConnectorWorkflow.png)

1. 組織は余裕期間を使用して、余裕期間サイトを設定および構成します。

2. 24時間ごとに、余裕期間からのチャットメッセージは Globanet Merge1 サイトにコピーされます。 また、コネクタは、チャットメッセージの内容を電子メールメッセージの形式に変換します。

3. Microsoft 365 コンプライアンスセンターで作成する余裕期間コネクタは、毎日 Globanet Merge1 サイトに接続し、チャットメッセージを Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。

4. 手順3で説明されているように、コネクタは、 *電子メール* プロパティの値と自動ユーザーマッピングを使用して、変換されたチャットメッセージアイテムを特定のユーザーのメールボックスにインポートします。 " **余裕期間** " という名前の受信トレイフォルダーに新しいサブフォルダーがユーザーのメールボックスに作成され、チャットメッセージアイテムがそのフォルダーにインポートされます。 コネクタは、 *Email* プロパティの値を使用してこれを実行します。 すべてのチャットメッセージには、このプロパティが含まれており、チャットメッセージのすべての参加者の電子メールアドレスが設定されます。

## <a name="before-you-begin"></a>開始する前に

- Microsoft コネクタ用の Globanet Merge1 アカウントを作成します。 これを行うには、 [Globanet カスタマーサポート](https://globanet.com/ms-connectors-contact)にお問い合わせください。 手順1でコネクタを作成するときに、このアカウントにサインインする必要があります。

- 組織の余裕期間エンタープライズアカウントのユーザー名とパスワードを取得します。 余裕期間を構成するときは、手順2でこのアカウントにサインインする必要があります。

- 手順1で余裕期間コネクタを作成する (および手順3で完了する) ユーザーは、Exchange Online のメールボックスインポートエクスポート役割に割り当てられている必要があります。 この役割は、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="step-1-set-up-the-slack-connector"></a>手順 1: 余裕期間コネクタを設定する

最初の手順として、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページにアクセスし、余裕期間データ用のコネクタを作成します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) して、[**データコネクタ**  >  の**余裕期間**] をクリックします。

2. [ **余裕期間** の製品の説明] ページで、[ **コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意**する] をクリックします。

4. コネクタを識別する一意の名前を入力し、[ **次へ**] をクリックします。

5. Merge1 アカウントにサインインして、コネクタを構成します。

## <a name="step-2-configure-slack"></a>手順 2: 余裕期間を構成する

2番目の手順は、Merge1 サイトで余裕期間コネクタを構成することです。 Globanet Merge1 サイトで余裕期間コネクタを構成する方法の詳細については、「 [Merge1 サードパーティコネクタユーザーガイド](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf)」を参照してください。

[ **保存 & 完了**] をクリックすると、Microsoft 365 コンプライアンスセンター (コネクタウィザードの [ **ユーザーマッピング** ] ページ) に戻ることができます。

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>手順 3: ユーザーをマップしてコネクタのセットアップを完了する

1. [ **外部ユーザーを Microsoft 365 ユーザーにマップする** ] ページで、[自動ユーザーマッピング] を有効にします。

   余裕期間アイテムには、組織内のユーザーの電子メールアドレスを含む *email*というプロパティが含まれています。 コネクタがこのアドレスを Microsoft 365 ユーザーに関連付けることができる場合は、そのユーザーのメールボックスにアイテムがインポートされます。

2. [ **管理者の同意** ] ページで、[ **同意を与える** ] ボタンをクリックします。 Microsoft サイトにリダイレクトされます。 同意を得るには、[ **承諾** ] をクリックします。

   組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 管理者の同意を得るには、Microsoft 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

3. [ **次へ**] をクリックして設定を確認し、[ **データコネクタ** ] ページに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="step-4-monitor-the-slack-connector"></a>手順 4: 余裕期間コネクタを監視する

余裕期間コネクタを作成した後、Microsoft 365 コンプライアンスセンターでコネクタの状態を表示できます。

1. [https://compliance.microsoft.com](https://compliance.microsoft.com)左側のナビゲーションに移動し、[**データコネクタ**] をクリックします。

2. [ **コネクタ** ] タブをクリックし、[ **余裕期間** ] コネクタを選択して、フライアウトページを表示します。このページには、コネクタに関するプロパティと情報が含まれています。

3. [ **コネクタの状態 (ソース付き**)] の下で、[ **ログのダウンロード** ] リンクをクリックしてコネクタの状態ログを開く (または保存) します。 このログには、Microsoft クラウドにインポートされたデータに関する情報が含まれています。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルとアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。