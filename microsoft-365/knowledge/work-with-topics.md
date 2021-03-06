---
title: 'トピックセンターのトピックを操作する (プレビュー) '
description: トピックセンターのトピックを操作する方法について説明します。
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 464a926b99cceeb652756ad6d1456c5e17d2a925
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988740"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>トピックセンターのトピックを操作する (プレビュー)

> [!Note] 
> この記事の内容は、Project Cortex のプライベートプレビュー用です。 [Project Cortexについてもっと理解しよう](https://aka.ms/projectcortex)


トピックセンターでは、指定した SharePoint ソースの場所でマイニングされ、検出されたトピックを確認または拒否することができます。 ナレッジマネージャーは、トピック探索で見つからなかった場合に新しいトピックページを作成して発行したり、更新する必要がある場合は既存のページを編集したりすることもできます。

## <a name="requirements"></a>Requirements

トピックセンターで作業するには、必要なアクセス許可を持っている必要があります。 管理者は、 [ナレッジ管理のセットアップ](set-up-topic-experiences.md)時に、ユーザーを追加したり、 [後](give-user-permissions-to-the-topic-center.md)で新しいユーザーを追加したりできます。

トピックセンターのユーザーには、次の2つのアクセス許可のセットを与えることができます。

- トピックを作成および編集する: 新しいトピックを作成するか、説明、ドキュメント、関連する人物などのトピックコンテンツを更新します。

- トピックの管理: トピック管理ダッシュボードを使用して、組織全体のトピックをレビューします。 ユーザーは、トピックの確認や拒否などの操作を実行できます。


## <a name="review-suggested-topics"></a>推奨されるトピックを確認する

トピックセンターのホームページで、指定した SharePoint ソースの場所で検出されたトピックが [ **推奨** ] タブに一覧表示されます。トピックを管理するアクセス許可を持つユーザーは、未確認のトピックを確認して確認するか、拒否するかを選択できます。


推奨されるトピックを確認するには:

1. [ **推奨** される項目] タブで、トピックを選択して [トピック] ページを開きます。</br>

2. [トピック] ページで、トピックページを確認し、ページに変更を加える必要がある場合は [ **編集** ] を選択します。

3. ナレッジセンターのホームページで、選択したトピックに対して、次のことを行うことができます。

    1. トピックを保持することを確認するには、[確認] を選択します。
    
    1. トピックを拒否する場合は、[ **x** ] を選択します。

    確認されたトピックは **未確認** のリストから削除され、[ **確認** ] タブに表示されるようになります。

    却下されたトピックは **未確認** のリストから削除され、[ **拒否] または [除外** ] タブに表示されるようになります。

## <a name="review-confirmed-topics"></a>確認済みトピックを確認する

トピックセンターのホームページでは、指定した SharePoint ソースの場所で検出され、ナレッジマネージャーが2人以上のユーザーによって確認されたトピックと、カードフィードバックメカニズムによって crowdsourced によって確認されたトピックが、[ **確認** ] タブに表示されます。トピックを管理するアクセス許可を持つユーザーは、確認されたトピックを確認して、拒否するかどうかを選択できます。


確認済みトピックを確認するには、次のようにします。

1. [ **確認** ] タブで、トピックを選択して [トピック] ページを開きます。</br>

2. [トピック] ページで、トピックページを確認し、ページに変更を加える必要がある場合は [ **編集** ] を選択します。

3. 拒否することもできます。

## <a name="review-published-topics"></a>公開されたトピックを確認する
公開されたトピックは、ページを見つけた人に対して特定の情報が常に表示されるように編集されています。 手動で作成したトピックはここに表示されます。

   
## <a name="create-a-new-topic"></a>新しいトピックを作成する

[トピックの作成または編集のアクセス許可を持つユーザーは、必要に応じて新しいトピックを作成できます。 この手順を実行する必要があるのは、トピックが検出されなかった場合、または AI テクノロジがトピックとして設定するのに十分な証拠を見つけられなかった場合です。

新しいトピックを作成するには、次のようにします。

1. [トピックセンター] ページで、[ **新規** ] を選択し、[ **トピックページ** ] を選択します。

    ![新しいトピック](../media/content-understanding/k-new-topic.png)

2. [新しいトピック] ページで、新しいトピックテンプレートの情報を入力できます。

    1. [ **このトピックの名前** ] セクションに、新しいトピックの名前を入力します。
    
    1. [ **代替名** ] セクションで、トピックを参照するためにも使用される名前または頭字語を入力します。
    
    1. [ **短い説明** ] セクションに、トピックの1つまたは2つの文の説明を入力します。 このテキストは、関連付けられたトピックカードに使用されます。
    
    1. [ **人** ] セクションで、トピックの該当分野の専門家の名前を入力します。
    
    1. [ **ファイルとページ** ] セクションで、[ **追加** ] を選択し、次のページで、関連付けられた OneDrive ファイルまたは SharePoint Online ページを選択できます。
    
    1. [ **サイト** ] セクションで、[ **追加** ] を選択します。 表示される [  **サイト** ] ウィンドウで、トピックに関連付けられているサイトを選択します。

    ![新しいトピックページ](../media/content-understanding/k-new-topic-page.png)
    
3. テキスト、画像、web パーツ、リンクなど、他のコンポーネントをページに追加する必要がある場合は、ページの中央にあるキャンバスアイコンを選択して、それを見つけて追加します。

    ![ページにアイテムを追加する](../media/content-understanding/static-icon.png)

4. 完了したら、[ **発行** ] を選択して、トピックページを発行します。 公開したトピックページが [ **ページ** ] タブに表示されます。

> [!Note] 
> 新しいトピックページは、 *知識ネットワークに対応* した web パーツから構成されます。 そのため、このトピックでは、AI が詳細な情報を収集することを意味します。これらの web パーツの情報は、ユーザーにとってより便利なページになるように、提案に基づいて更新されます。


## <a name="edit-an-existing-topic-page"></a>既存のトピックページを編集する

既存のトピックページは、[ **ページ** ] ページにあります。 

1. [トピックセンター] ページで、[ **ページ** ] を選択します。

2. [ **ページ** ] ページに、トピックページの一覧が表示されます。 検索ボックスを使用して、更新するトピックページを検索します。 編集するトピックページの名前をクリックします。

3. [トピック] ページで、[ **編集** ] を選択します。

4. ページに対して必要な変更を行います。 これには、以下のフィールドの更新が含まれます。

    1. 代替名
    1. 説明
    1. People
    1. ファイルおよびページ
    1. サイト
    1. カンバスアイコンを選択して、テキスト、画像、リンクなどのページに静的アイテムを追加することもできます。

5. [ **再発行** ] を選択して変更を保存します。

<!--## See also-->


