---
title: Microsoft 365 で WhatsApp データをアーカイブするためのコネクタをセットアップする
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
description: 管理者は、TeleMessage コネクタを設定して、Microsoft 365 で WhatsApp データをインポートおよびアーカイブすることができます。 これにより、Microsoft 365 でサードパーティのデータソースのデータをアーカイブできるようになるため、法的情報保留、コンテンツ検索、アイテム保持ポリシーなどのコンプライアンス機能を使用して、組織のサードパーティデータを管理できます。
ms.openlocfilehash: 2600356fc2628d5832f93f7dbe4fc247d8812410
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087184"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>WhatsApp データをアーカイブするためのコネクタの設定

Microsoft 365 コンプライアンスセンターの TeleMessage コネクタを使用して、WhatsApp 通話、チャット、添付ファイル、ファイル、および削除されたメッセージのインポートとアーカイブを行います。 コネクタをセットアップして構成した後は、組織の TeleMessage アカウントに毎日接続し、Microsoft 365 の TeleMessage WhatsApp 電話アーカイバまたは TeleMessage WhatsApp Cloud Archiver を使用して従業員のモバイルコミュニケーションをインポートします。

WhatsApp データがユーザーのメールボックスに格納された後は、訴訟ホールド、コンテンツ検索、Microsoft 365 のアイテム保持ポリシーなどの Microsoft 365 コンプライアンス機能を WhatsApp データに適用することができます。 たとえば、コンテンツ検索を使用して WhatsApp メッセージを検索したり、WhatsApp メッセージを含むメールボックスを高度な電子情報開示ケースの保管担当者に関連付けることができます。 WhatsApp コネクタを使用して Microsoft 365 のデータをインポートおよびアーカイブすることで、組織は政府および規制ポリシーに準拠し続けることができます。

## <a name="overview-of-archiving-whatsapp-data"></a>WhatsApp データのアーカイブの概要

次の概要では、コネクタを使用して Microsoft 365 の WhatsApp データをアーカイブするプロセスについて説明します。

![WhatsApp アーカイブワークフロー](../media/WhatsAppConnectorWorkflow.png)

1. 組織は TeleMessage を使用して、WhatsApp Archiver コネクタを設定します。 詳細については、「 [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver)」を参照してください。

2. 24時間ごとに、組織の WhatsApp データが TeleMessage サイトにコピーされます。

3. Microsoft 365 コンプライアンスセンターで作成した WhatsApp コネクタは、毎日 TeleMessage サイトに接続し、WhatsApp データを以前の24時間から Microsoft クラウド内のセキュアな Azure ストレージの場所に転送します。 また、コネクタは、コンテンツ WhatsApp データを電子メールメッセージ形式に変換します。

4. コネクタは WhatsApp データを特定のユーザーのメールボックスにインポートします。 **WhatsApp Archiver** という名前の新しいフォルダーが、特定のユーザーのメールボックス内に作成され、アイテムがインポートされます。 コネクタは、 *ユーザーの電子メールアドレス* プロパティの値を使用して、このマッピングを行います。 すべての WhatsApp メッセージには、このプロパティが含まれています。このプロパティには、メッセージのすべての参加者の電子メールアドレスが設定されます。

   *ユーザーの電子メールアドレス* プロパティの値を使用した自動ユーザーマッピングに加えて、CSV マッピングファイルをアップロードしてカスタムマッピングを実装することもできます。 このマッピングファイルには、組織内のユーザーの携帯電話番号と、対応する Microsoft 365 メールアドレスが含まれています。 自動ユーザーマッピングとカスタムマッピングの両方を有効にした場合、WhatsApp アイテムごとに、コネクタは最初にカスタムマッピングファイルを参照します。 ユーザーの携帯電話番号に対応する有効な Microsoft 365 ユーザーが見つからない場合、コネクタはインポートしようとしているアイテムの [電子メールアドレス] プロパティの値を使用します。 コネクタがカスタムマッピングファイルまたは WhatsApp item の電子メールアドレスプロパティに有効な Microsoft 365 ユーザーを見つけられない場合、アイテムはインポートされません。

## <a name="before-you-begin"></a>開始する前に

WhatsApp 通信データをアーカイブするために必要ないくつかの実装手順は、Microsoft 365 の外部にあり、コンプライアンスセンターでコネクタを作成する前に完了する必要があります。

- [WhatsApp Archiver service を TeleMessage から](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365)オーダーし、組織の有効な管理アカウントを取得します。 コンプライアンスセンターでコネクタを作成するときに、このアカウントにサインインする必要があります。

- TeleMessage アカウントで、WhatsApp アーカイブを必要とするすべてのユーザーを登録します。 ユーザーを登録する場合は、Microsoft 365 アカウントに使用しているのと同じ電子メールアドレスを使用してください。

- 従業員の携帯電話に TeleMessage [WhatsApp Phone Archiver アプリ](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) をインストールして、それを有効にします。 または、一般の WhatsApp または WhatsApp のビジネスアプリを従業員の携帯電話にインストールし、TeleMessage web サイトの QR コードをスキャンして、WhatsApp Cloud Archiver サービスをアクティブ化することもできます。 詳細については、「 [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/)」を参照してください。

- 組織は、Office 365 インポートサービスが組織内のメールボックスデータにアクセスできるようにするための同意を得る必要があります。 この同意を得るには、コネクタを作成する必要があります。 この要求に同意するには、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)に移動して、Microsoft 365 グローバル管理者の資格情報でサインインし、要求を承諾します。 Verizon ネットワークコネクタを正常に作成するには、この手順を完了する必要があります。

- Verizon ネットワークコネクタを作成したユーザーには、Exchange Online のメールボックスのインポートのエクスポート役割が割り当てられている必要があります。 これは、Microsoft 365 コンプライアンスセンターの [ **データコネクタ** ] ページでコネクタを追加するために必要です。 既定では、この役割は Exchange Online のどの役割グループにも割り当てられていません。 Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加することができます。 または、役割グループを作成し、メールボックスインポートエクスポート役割を割り当ててから、適切なユーザーをメンバーとして追加することもできます。 詳細については、記事「Manage role groups in Exchange Online」の「 [役割グループの作成](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 」または「 [役割グループの変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 」のセクションを参照してください。

## <a name="create-a-whatsapp-archiver-connector"></a>WhatsApp Archiver コネクタを作成する

前のセクションで説明した前提条件を完了したら、Microsoft 365 コンプライアンスセンターで WhatsApp コネクタを作成できます。 コネクタは、提供された情報を使用して、TeleMessage サイトに接続し、WhatsApp データを Microsoft 365 の対応するユーザーメールボックスに転送します。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[**データコネクタ**  >  **WhatsApp Archiver**] をクリックします。

2. [ **WhatsApp Archiver** product description] ページで、[**コネクタの追加**] をクリックします。

3. [ **サービス利用規約** ] ページで、[ **同意** する] をクリックします。

4. [ **TeleMessage へのログイン** ] ページの [ステップ 3] で、必要な情報を次のボックスに入力し、[ **次へ**] をクリックします。

   - **ユーザー名:** TeleMessage ユーザー名。

   - **パスワード:** TeleMessage のパスワードを入力します。

5. コネクタが作成されたら、ポップアップウィンドウを閉じて次のページに進むことができます。

6. [ **ユーザーマッピング** ] ページで、[ユーザーマッピングの自動設定] を有効にして、[ **次へ**] をクリックします。 カスタムマッピングが必要な場合は、CSV ファイルをアップロードし、[ **次へ**] をクリックします。

7. 管理者の同意を得てから、[ **次へ**] をクリックします。

   管理者の同意を得るには、Office 365 グローバル管理者の資格情報を使用してサインインし、同意要求を承諾する必要があります。 グローバル管理者としてサインインしていない場合は、 [このページ](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) に移動して、グローバル管理者の資格情報を使用してサインインし、要求を承諾することができます。

8. 設定内容を確認し、[ **完了** ] をクリックしてコネクタを作成します。

9. [ **データコネクタ** ] ページの [コネクタ] タブに移動して、新しいコネクタのインポート処理の進行状況を確認します。

## <a name="known-issues"></a>既知の問題

- 現時点では、10 MB を超える添付ファイルやアイテムのインポートはサポートされていません。 より大きいアイテムのサポートは、後日提供されます。
