---
title: インサイダー リスク管理通知のテンプレート
description: Microsoft 365 の insider リスク管理の通知テンプレートについて説明します。
keywords: Microsoft 365、insider リスク管理、リスク管理、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 3a74c62e84c1cb9e4c749a364c0e5b6da25a8af9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47416481"
---
# <a name="insider-risk-management-notice-templates"></a>インサイダー リスク管理通知のテンプレート

Insider リスク管理の通知テンプレートを使用すると、アクティビティがポリシーの一致とアラートを生成するときに、ユーザーに電子メールメッセージを送信することができます。 ほとんどの場合、警告を生成するユーザー操作は、誤りまたは不注意な操作の結果として、意図したとおりにはなりません。 通知は、ユーザーに対して簡単な通知を提供し、リフレッシャートレーニングの情報へのリンク、または企業ポリシーリソースへのリンクを提供します。 通知は、内部のコンプライアンストレーニングプログラムの重要な部分であり、定期的なリスクアクティビティを持つユーザーのために文書化された監査証跡を作成するのに役立ちます。

問題解決プロセスの一環として、ポリシーの一致に関する電子メール通知通知をユーザーに送信する場合は、通知テンプレートを作成します。 通知は、確認されている特定の通知に関連付けられたユーザーのメールアドレスにのみ送信できます。 ポリシー一致に適用する通知テンプレートを選択するときは、テンプレートで定義されているフィールド値を受け入れるか、必要に応じてフィールドを上書きするかを選択できます。

## <a name="notice-templates-dashboard"></a>通知テンプレートダッシュボード

**通知テンプレートダッシュボード**には、構成された通知テンプレートのリストが表示され、新しい通知テンプレートを作成できます。 通知テンプレートは、最新の通知テンプレートを最初に、日付の逆順でリストに表示されます。

![Insider リスク管理の通知テンプレートダッシュボード](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>通知用の HTML

通知用の単純なテキストベースの電子メールメッセージを作成する場合は、通知テンプレートの [メッセージ本文] フィールドで HTML を使用して、より詳細なメッセージを作成できます。 次の例では、基本的な HTML ベースの電子メール通知テンプレートのメッセージ本文の形式を示します。

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> Insider リスク管理の通知テンプレートの HTML href 属性の実装では、現在、URL 参照の二重引用符の代わりに単一引用符のみがサポートされています。

## <a name="create-a-new-notice-template"></a>新しい通知テンプレートを作成する

新しい insider リスク管理の通知テンプレートを作成するには、Microsoft 365 コンプライアンスセンターで、 **insider リスク管理** ソリューションの通知ウィザードを使用します。

新しい insider リスク管理通知テンプレートを作成するには、次の手順を実行します。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。
2. [ **通知テンプレートの作成** ] を選択して、通知ウィザードを開きます。
3. [ **新しい通知テンプレートの作成** ] ページで、以下のフィールドに入力します。
    - **テンプレート名**: 通知のフレンドリ名を入力します。 この名前は、ケースから通知を送信するときに、通知ダッシュボードと通知選択リストに通知の一覧に表示されます。
    - **送信元**: 通知の送信者の電子メールアドレスを入力します。 このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信されるすべての通知の [ **差出人:** ] フィールドに表示されます。
    - **Cc および Bcc** フィールド: サブスクリプションの Active Directory から選択された、ポリシーの一致の通知対象となるオプションのユーザーまたはグループ。
    - **件名**: メッセージの件名行に表示される情報。テキスト文字をサポートします。
    - **メッセージ本文**: メッセージ本文に表示される情報は、テキストまたは HTML 値をサポートします。
4. [ **作成** ] を選択して通知テンプレートを作成および保存するか、[ **キャンセル** ] を選択して通知テンプレートを保存せずに閉じます。

## <a name="update-a-notice-template"></a>通知テンプレートを更新する

既存の insider リスク管理の通知テンプレートを更新するには、次の手順を実行します。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。
2. 通知ダッシュボードで、管理する通知テンプレートを選択します。
3. [通知の詳細] ページで、[**編集**] を選択します。
4. **編集**ページでは、次のフィールドを編集できます。
    - [**テンプレート名**: 新しいわかりやすい名前を入力してください。 この名前は、ケースから通知を送信するときに、通知ダッシュボードと通知選択リストに通知の一覧に表示されます。
    - **送信元**: 通知の送信者の電子メールアドレスを更新します。 このアドレスは、ケースから通知を送信するときに変更されない限り、ユーザーに送信されるすべての通知の [ **差出人:** ] フィールドに表示されます。
    - **Cc および Bcc** フィールド: サブスクリプションの Active Directory から選択されたポリシーの一致を通知するオプションのユーザーまたはグループを更新します。
    - **件名**: メッセージの件名行に表示される更新情報。テキスト文字をサポートします。
    - **メッセージ本文**: メッセージ本文に表示される更新情報。テキストまたは HTML 値をサポートします。
5. [ **保存** ] を選択して通知を更新して保存するか、[ **キャンセル** ] を選択して通知テンプレートを保存せずに閉じます。

## <a name="delete-a-notice-template"></a>通知テンプレートを削除する

既存の insider リスク管理の通知テンプレートを削除するには、次の手順を実行します。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で、[ **Insider リスク管理**] に移動し、[**通知テンプレート**] タブを選択します。
2. 通知ダッシュボードで、削除する通知テンプレートを選択します。
3. ツールバーの [ **削除** ] アイコンを選択します。
4. 通知テンプレートを削除するには、[削除] ダイアログで [ **はい** ] を選択します。 削除を取り消すには、[ **キャンセル**] を選択します。
