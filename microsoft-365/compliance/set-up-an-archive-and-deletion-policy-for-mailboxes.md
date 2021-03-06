---
title: 組織のメールボックスについて、アーカイブ削除ポリシーを設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom: seo-marvel-apr2020
description: ユーザーのアーカイブメールボックスにアイテムを自動的に移動するためのアーカイブおよび削除ポリシーを Microsoft 365 で作成する方法について説明します。
ms.openlocfilehash: 7bbd4a2f4a5b9c35695b5e0630020a0f39224324
ms.sourcegitcommit: f941495e9257a0013b4a6a099b66c649e24ce8a1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993367"
---
# <a name="set-up-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>組織のメールボックスについて、アーカイブ削除ポリシーを設定する

Microsoft 365 では、管理者は、ユーザーのアーカイブメールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。 管理者は、メールボックスに割り当てられたアイテム保持ポリシーを作成し、一定の期間後にユーザーのアーカイブメールボックスにアイテムを移動します。また、特定の保存期間に達した後もメールボックスからアイテムを削除します。 移動または削除されたアイテム、およびその発生時に保持タグと呼ばれるアイテムを決定する実際のルール。 保持タグは、ユーザーのメールボックスに割り当てられるアイテム保持ポリシーにリンクされます。 保持タグは、ユーザーのメールボックス内の個々のメッセージおよびフォルダーに保持設定を適用します。 メッセージがメールボックス内に残っている期間と、指定された保持期限に達したときに実行される処理を定義します。 メッセージが保存期限に達すると、メッセージはユーザーのアーカイブメールボックスに移動されるか、削除されます。
  
この記事の手順では、Alpine House という架空の組織のアーカイブとアイテム保持ポリシーを設定します。 このポリシーの設定には、次のタスクが含まれます。
  
- 組織内のすべてのユーザーに対してアーカイブメールボックスを有効にします。 これにより、ユーザーにメールボックスストレージが追加され、アイテム保持ポリシーがアーカイブメールボックスにアイテムを移動できるようにする必要があります。 また、アーカイブメールボックスにアイテムを移動することで、ユーザーがアーカイブ情報を格納することもできます。

- 次の操作を実行する3つのカスタム保持タグを作成します。

  - 3年以上経過したアイテムをユーザーのアーカイブメールボックスに自動的に移動します。 アイテムをアーカイブメールボックスに移動すると、ユーザーのプライマリメールボックス内の領域が解放されます。

  - 5年前のアイテムを削除済みアイテムフォルダーから自動的に削除します。 これにより、ユーザーのプライマリメールボックス内のスペースも解放されます。 ユーザーは、必要に応じてこれらのアイテムを復元できます。 詳細については、「 [more information](#more-information) 」セクションの脚注を参照してください。 

  - 7年前のアイテムをプライマリメールボックスとアーカイブメールボックスの両方から、自動的に (および完全に) 削除します。 コンプライアンス規制のため、一部の組織では、一定期間電子メールを保持する必要があります。 この期間が過ぎると、組織はこれらのアイテムのユーザーメールボックスを完全に削除することができます。

- 新しいアイテム保持ポリシーを作成し、それに新しいカスタム保持タグを追加します。 また、組み込み保持タグを新しいアイテム保持ポリシーに追加することもできます。 これには、ユーザーが自分のメールボックス内のアイテムに割り当てることができる個人タグが含まれています。 また、ユーザーのプライマリメールボックス内の [回復可能なアイテム] フォルダーからアーカイブメールボックス内の [回復可能なアイテム] フォルダーにアイテムを移動する保持タグを追加します。 これにより、ユーザーのメールボックスが保持されているときに、回復可能なアイテムフォルダーの空き領域を増やすことができます。

この記事の手順の一部またはすべてを実行して、組織内のメールボックスのアーカイブおよび削除ポリシーを設定できます。 このプロセスは、組織内のすべてのメールボックスに実装する前に、少数のメールボックスに対してテストすることをお勧めします。
  
## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>アーカイブと削除のポリシーを設定する前に

- このトピックの手順を実行するには、組織の全体管理者である必要があります。 

- 新しいユーザーアカウントを作成し、ユーザーに Exchange Online のライセンスを割り当てると、そのユーザーのメールボックスが自動的に作成されます。 メールボックスが作成されると、default MRM Policy という名前の既定のアイテム保持ポリシーが自動的に割り当てられます。 この記事では、新しいアイテム保持ポリシーを作成し、それをユーザーのメールボックスに割り当てて、既定の MRM ポリシーを置き換えます。 メールボックスには、一度に1つだけ保持ポリシーを割り当てることができます。

- Exchange Online の保持タグとアイテム保持ポリシーの詳細については、「 [retention tags and retention policies](https://go.microsoft.com/fwlink/p/?LinkId=404424)」を参照してください。

## <a name="step-1-enable-archive-mailboxes-for-users"></a>手順 1: ユーザーのアーカイブメールボックスを有効にする

最初の手順として、組織内の各ユーザーのアーカイブメールボックスを有効にします。 ユーザーのアーカイブメールボックスを有効にして、保持期間の期限が切れた後に "アーカイブに移動する" 保持アクションを実行するアイテムを移動できるようにする必要があります。
  
> [!NOTE]
> このプロセスの実行中は、いつでもアーカイブメールボックスを有効にすることができます。これは、プロセスが完了する前に、ある時点で有効になっている限りです。 アーカイブメールボックスが有効になっていない場合は、アーカイブまたは削除ポリシーが割り当てられているアイテムに対しては何も実行されません。
  
1. [https://protection.office.com](https://protection.office.com) に移動します。

2. グローバル管理者アカウントを使用してサインインします。
    
3. セキュリティ & コンプライアンスセンターで、[ **情報ガバナンス** \> **アーカイブ** ] に移動します。

    組織内のメールボックスの一覧、および対応するアーカイブメールボックスが有効になっているかどうかが表示されます。

4. 一覧の最初のメールボックスをクリックし、 **Shift** キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。

    > [!TIP]
    > この手順は、アーカイブメールボックスが有効になっていないことを前提としています。 アーカイブが有効になっているメールボックスがある場合は、 **Ctrl** キーを押したまま、無効にされたアーカイブメールボックスを持つ各メールボックスをクリックします。 または、 **アーカイブメールボックスの列ヘッダー** をクリックして、アーカイブメールボックスが有効か無効かに基づいて行を並べ替え、メールボックスを簡単に選択できるようにすることもできます。
  
5. 詳細ウィンドウの [ **一括編集** ] で、[ **有効にする** ] をクリックします。

    2年間以上経過したアイテムが新しいアーカイブメールボックスに移動されるという警告が表示されます。 これは、作成時に新しいユーザーメールボックスに割り当てられる既定の保持ポリシーに、2年間の保持期間が設定された既定のアイテム保持ポリシーがあるからです。 手順2で作成するカスタムアーカイブの既定のポリシータグには、3年間の保持期限があります。 これは、3年間またはそれ以前のアイテムがアーカイブメールボックスに移動されることを意味します。

6. [ **はい]** をクリックして警告メッセージを閉じ、選択した各メールボックスのアーカイブメールボックスを有効にするプロセスを開始します。

7. 処理が完了したら **、[最新** の情報に更新] をクリックして、[ ![ ](../media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **アーカイブ** ] ページの一覧を更新します。

    アーカイブメールボックスは、組織内のすべてのユーザーに対して有効になっています。

    ![アーカイブメールボックスが有効になっているメールボックスの一覧](../media/61a7cb97-1bed-4808-aa5f-b6b761cfa8de.png)

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>手順 2: アーカイブポリシーと削除ポリシー用の新しい保持タグを作成する

この手順では、前に説明した3つのカスタム保持タグを作成します。
  
- Alpine House 3 年間のアーカイブへの移動 (カスタムアーカイブポリシー)

- Alpine House 7 年間完全に削除 (カスタム削除ポリシー)

- Alpine House Deleted Items 5 年間削除して回復を許可する (削除済みアイテムフォルダーのカスタムタグ)

新しい保持タグを作成するには、exchange Online 組織の Exchange 管理センター (EAC) を使用します。 EAC のクラシックバージョンを使用していることを確認してください。
  
1. に移動して [https://admin.protection.outlook.com/ecp/](https://admin.protection.outlook.com/ecp/) 、資格情報を使用してサインインします。
  
2. EAC で、[ **コンプライアンス管理** ] [  >  **保持タグ** ] に移動します。

    組織の保持タグの一覧が表示されます。

### <a name="create-a-custom-archive-default-policy-tag"></a>カスタムアーカイブの既定のポリシータグを作成する
  
最初に、3年後にアーカイブメールボックスにアイテムを移動するカスタムアーカイブの既定のポリシータグ (DPT) を作成します。
  
1. [ **保持タグ** ] ページで、[ **新しいタグ** の新規作成] アイコンをクリックし、[ ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **メールボックス全体に自動的に適用する (既定)** ] を選択します。

2. [ **メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。 

    ![新しいアーカイブの既定のポリシータグを作成するための設定](../media/41c0a43c-9c72-44e0-8947-da0831896432.png)
  
   1. **名前** 新しい保持タグの名前を入力します。 

   2. **保持アクション** 保持期間が経過したときにアーカイブメールボックスにアイテムを移動するには、[ **アーカイブに移動** する] を選択します。

   3. **保持期間****アイテムが次の期間 (日数) に達したときに** 選択し、保存期間の期間を入力します。 このシナリオでは、アイテムは1095日 (3 年) 後にアーカイブメールボックスに移動されます。

   4. **Comment** (省略可能) カスタム保持タグの目的を説明するコメントを入力します。

3. [ **保存** ] をクリックして、カスタムアーカイブ DPT を作成します。

    新しいアーカイブ DPT が保持タグの一覧に表示されます。

### <a name="create-a-custom-deletion-default-policy-tag"></a>カスタム削除の既定のポリシータグを作成する
  
次に、もう1つのカスタム DPT を作成しますが、これは7年後にアイテムを完全に削除する削除ポリシーとなります。
  
1. [ **保持タグ** ] ページで、[ **新しいタグ** の新規作成] アイコンをクリックし、[ ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **メールボックス全体に自動的に適用する (既定)** ] を選択します。

2. [ **メールボックス全体に自動的に適用される新しいタグ (既定)** ] ページで、以下のフィールドに入力します。 

    ![新しい削除の既定のポリシータグを作成するための設定](../media/f1f0ff62-eec9-4824-8e7c-d93dcfb09a79.png)
  
   1. **名前** 新しい保持タグの名前を入力します。 

   2. **保持アクション** 保持期間が経過したときにメールボックスからアイテムを削除するには、[ **完全に削除** ] を選択します。

   3. **保持期間****アイテムが次の期間 (日数) に達したときに** 選択し、保存期間の期間を入力します。 このシナリオでは、アイテムは2555日 (7 年) 後に削除されます。

   4. **Comment** (省略可能) カスタム保持タグの目的を説明するコメントを入力します。 

3. [ **保存** ] をクリックして、カスタム削除 DPT を作成します。 

    新しい削除 DPT が保持タグの一覧に表示されます。

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグを作成する
  
作成する最後の保持タグは、削除済みアイテムフォルダーのカスタムアイテム保持ポリシータグ (RPT) です。 このタグは、削除済みアイテムフォルダー内のアイテムを5年後に削除し、ユーザーが [削除済みアイテムを復元] ツールを使用してアイテムを復元するときの回復期間を提供します。
  
1. [ **保持タグ** ] ページで、[ **新しいタグ** の新規作成] アイコンをクリックし、[ ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) **既定のフォルダーに自動的に適用する** ] を選択します。

2. 既定の **フォルダーページに自動的に適用される新しいタグ** で、以下のフィールドに入力します。

    ![削除済みアイテムフォルダーの新しいアイテム保持ポリシータグを作成するための設定](../media/6f3104bd-5edb-48ac-884d-5fe13d81dd1d.png)
  
   1. **名前** 新しい保持タグの名前を入力します。 

   2. **[次の既定フォルダーにこのタグを適用する** ]ドロップダウンリストで、[ **削除済みアイテム** ] を選択します。

   3. **保持アクション** [ **削除して回復を許可** する] を選択して、保存期間の期限が切れたときにアイテムを削除します。ただし、ユーザーは削除済みアイテムの保存期間 (既定では14日) 内で削除されたアイテムを復元することができます。

   4. **保持期間****アイテムが次の期間 (日数) に達したときに** 選択し、保存期間の期間を入力します。 このシナリオでは、1825日 (5 年) 後にアイテムが削除されます。

   5. **Comment** (省略可能) カスタム保持タグの目的を説明するコメントを入力します。 

3. [ **保存** ] をクリックして、削除済みアイテムフォルダーのカスタム RPT を作成します。

    新しい RPT が保持タグの一覧に表示されます。

## <a name="step-3-create-a-new-retention-policy"></a>手順 3: 新しいアイテム保持ポリシーを作成する

カスタム保持タグを作成したら、次の手順として、新しいアイテム保持ポリシーを作成し、保持タグを追加します。 手順2で作成した3つのカスタム保持タグと、最初のセクションで説明した組み込みタグを追加します。 ステップ4では、この新しいアイテム保持ポリシーをユーザーメールボックスに割り当てます。
  
1. EAC で、[ **コンプライアンス管理** ] [  >  **アイテム保持ポリシー** ] に移動します。

2. [ **アイテム保持ポリシー** ] ページで、[ **新規** ![ 作成] アイコンをクリックし ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ます。

3. [ **名前** ] ボックスに、新しいアイテム保持ポリシーの名前を入力します。たとえば、 **Alpine House のアーカイブおよび削除ポリシー** です。

4. [ **保持タグ** ] で、[新規アイコンの **追加** ] をクリックし ![ ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) ます。

    組織内の保持タグの一覧が表示されます。 メモ手順2で作成したカスタムタグが表示されます。

5. 次のスクリーンショットで強調表示されている9つの保持タグを追加します (これらのタグの詳細については、「 [more information](#more-information) 」セクションを参照してください)。 保持タグを追加するには、それを選択して [ **追加** ] をクリックします。

    ![新しいアイテム保持ポリシーに保持タグを追加する](../media/d8e87176-0716-4238-9e6a-7c4af35541dc.png)
  
    > [!TIP]
    > 複数の保持タグを選択するには、 **Ctrl** キーを押しながら各タグをクリックします。 
  
6. 保持タグを追加したら、[ **OK]** をクリックします。

7. [ **新しいアイテム保持ポリシー** ] ページで、[ **保存** ] をクリックして新しいポリシーを作成します。

    新しいアイテム保持ポリシーが一覧に表示されます。 このチェックボックスをオンにすると、詳細ウィンドウにリンクされている保持タグが表示されます。

    ![新しいアイテム保持ポリシーとリンクされた保持タグのリスト](../media/63bc45e6-110b-4dc9-a85f-8eb1961a8258.png)
  
## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>手順 4: 新しいアイテム保持ポリシーをユーザーメールボックスに割り当てる

新しいメールボックスが作成されると、default MRM policy という名前のアイテム保持ポリシーが既定で割り当てられます。 この手順では、手順3で作成した新しいアイテム保持ポリシーを組織内のユーザーのメールボックスに割り当てることによって、このアイテム保持ポリシーを置き換えます (メールボックスに割り当てられる保持ポリシーは1つだけです)。 この手順では、組織内のすべてのメールボックスに新しいポリシーを割り当てることを前提としています。
  
1. EAC で、[ **受信者**  >  **メールボックス** ] に移動します。

    組織内のすべてのユーザーメールボックスの一覧が表示されます。

2. 一覧の最初のメールボックスをクリックし、 **Shift** キーを押しながら、一覧の最後のメールボックスをクリックして、すべてのメールボックスを選択します。 

3. EAC の右側にある詳細ウィンドウの [ **一括編集** ] で、[ **その他のオプション** ] をクリックします。

4. 
            **[アイテム保持ポリシー]** 下で **[更新]** をクリックします。

5. [ **アイテム保持ポリシーの一括割り当て** ] ページの [ **アイテム保持ポリシーの選択** ] ドロップダウンリストで、手順3で作成したアイテム保持ポリシーを選択します。たとえば、 **Alpine House のアーカイブとアイテム保持ポリシー** があります。

6. [ **保存** ] をクリックして、新しいアイテム保持ポリシーの割り当てを保存します。

7. 新しいアイテム保持ポリシーがメールボックスに割り当てられていることを確認するには、次の操作を行います。

   1. [ **メールボックス** ] ページでメールボックスを選択し、 **[編集] をクリックし** ![ ](../media/d7dc7e5f-17a1-4eb9-b42d-487db59e2e21.png) ます。

   2. 選択したユーザーのメールボックスのプロパティページで、[ **メールボックスの機能** ] をクリックします。

   メールボックスに割り当てられた新しいポリシーの名前が、[ **アイテム保持ポリシー** ] ドロップダウンリストに表示されます。

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>オプション手順 5: 管理フォルダーアシスタントを実行して新しい設定を適用する

手順4で新しいアイテム保持ポリシーをメールボックスに適用した後、メールボックスに新しいアイテム保持設定を適用するには、Exchange Online で最大7日かかることがあります。 これは、 *管理フォルダーアシスタント* と呼ばれるプロセスが、少なくとも7日ごとにメールボックスを処理するからです。 管理フォルダーアシスタントの実行を待機する代わりに、Exchange Online PowerShell で " **Start/ManagedFolderAssistant** " コマンドレットを実行することによって、これを強制的に実行することができます。

 **管理フォルダーアシスタントを実行するとどうなりますか。** アイテム保持ポリシーの設定を適用するには、メールボックス内のアイテムを調べて、保持の対象であるかどうかを判断します。 その後、適切な保持タグを使用してアイテムに保存期間をスタンプし、保存期間を過ぎたアイテムに対して指定された保持アクションを実行します。
  
Exchange Online PowerShell に接続し、組織内のすべてのメールボックスで管理フォルダーアシスタントを実行する手順を次に示します。

1. [Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/p/?LinkId=517283)。
  
2. 組織内のすべてのユーザーメールボックスに対して管理フォルダーアシスタントを開始するには、次の2つのコマンドを実行します。

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

するだけです。 Alpine House 組織のアーカイブと削除のポリシーを設定している。

> [!NOTE]
> 前述したように、管理フォルダーアシスタントは、少なくとも7日ごとにメールボックスを処理します。 そのため、管理フォルダーアシスタントによってメールボックスがより頻繁に処理される可能性があります。 また、管理者は、管理フォルダーアシスタントによってメールボックスが次回処理されたときに、管理者は予測できません。これは、手動で実行する必要がある理由の1つです。 ただし、管理フォルダーアシスタントがメールボックスに新しいアイテム保持設定を適用することを一時的に禁止する場合は、コマンドを実行して、 `Set-Mailbox -ElcProcessingDisabled $true` 管理フォルダーアシスタントがメールボックスの処理を一時的に無効にすることができます。 メールボックスの管理フォルダーアシスタントを再度有効にするには、コマンドを実行し `Set-Mailbox -ElcProcessingDisabled $false` ます。
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>オプション手順 6: 新しいアイテム保持ポリシーを組織の既定に設定する

手順4では、既存のメールボックスに新しいアイテム保持ポリシーを割り当てる必要があります。 ただし、今後作成される新しいメールボックスに新しいアイテム保持ポリシーが割り当てられるように、Exchange Online を構成することができます。 これを行うには、Exchange Online PowerShell を使用して組織の既定のメールボックスプランを更新します。 *メールボックス計画* は、新しいメールボックスのプロパティを自動的に構成するテンプレートです。  このオプションの手順では、メールボックスプランに割り当てられている現在のアイテム保持ポリシー (既定では、既定の MRM ポリシー) を手順3で作成したアイテム保持ポリシーに置き換えることができます。 メールボックスプランを更新すると、新しいアイテム保持ポリシーが新しいメールボックスに割り当てられます。

1. [Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/p/?LinkId=517283)。

2. 組織内のメールボックスプランに関する情報を表示するには、次のコマンドを実行します。

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```

    既定として設定されているメールボックスプランをメモします。

3. 次のコマンドを実行して、手順3で作成した新しいアイテム保持ポリシー (たとえば、 **Alpine House Archive And Retention policy** ) を既定のメールボックス計画に割り当てます。 この例では、既定のメールボックスプランの名前が **Exchangeonline enterprise** であると仮定しています。

    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. 手順2のコマンドを再実行して、既定のメールボックス計画に割り当てられたアイテム保持ポリシーが変更されたことを確認できます。

## <a name="more-information"></a>詳細情報

- 保存期間はどのように計算されますか? メールボックスアイテムの保持期間は、配信日または作成日 (送信されないが、ユーザーによって作成された下書きメッセージなど) から計算されます。 管理フォルダー アシスタントがメールボックス内のアイテムを処理する際、 [削除して回復を許可する] または [完全に削除する] の保存期間用アクション付き保持タグの付いたすべてのアイテムに開始日と有効期限をスタンプします。 アーカイブタグがあるアイテムには、移動日がスタンプされます。 

- 次の表では、このトピックの手順に従って作成されたカスタムアイテム保持ポリシーに追加される各保持タグの詳細について説明します。

    | 保持タグ | このタグの内容 | 組み込みまたはユーザー設定の場合 | 型 |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 年間のアーカイブへの移動  <br/> |過去1095日 (3 年) のアイテムをアーカイブメールボックスに移動します。  <br/> |Custom (「 [手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)  <br/> |既定のポリシータグ (アーカイブ)、このタグは、メールボックス全体に自動的に適用されます。  <br/> |
    |Alpine House 7 年間完全に削除  <br/> |7年前の時点でプライマリメールボックスまたはアーカイブメールボックスのアイテムを完全に削除します。  <br/> |Custom (「 [手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)  <br/> |既定のポリシータグ (削除)。このタグは、メールボックス全体に自動的に適用されます。  <br/> |
    |Alpine House Deleted Items 5 年間削除して回復を許可する  <br/> |5年前の削除済みアイテムフォルダーからアイテムを削除します。 ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup> <br/> |Custom (「 [手順 2: アーカイブポリシーと削除ポリシーの新しい保持タグを作成](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies)する」を参照)  <br/> |アイテム保持ポリシータグ (削除済みアイテム)、このタグは、[削除済みアイテム] フォルダー内のアイテムに自動的に適用されます。  <br/> |
    |回復可能なアイテム-14 日でアーカイブへ移動  <br/> |回復可能なアイテムフォルダーにあるアイテムを、14日間、アーカイブメールボックスの [回復可能なアイテム] フォルダーに移動します。  <br/> |組み込み  <br/> |アイテム保持ポリシータグ (回復可能なアイテム)、このタグは、[回復可能なアイテム] フォルダー内のアイテムに自動的に適用されます。  <br/> |
    |迷惑メール  <br/> |[迷惑メール] フォルダーに30日間含まれていたアイテムを完全に削除します。 ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup> <br/> |組み込み  <br/> |アイテム保持ポリシータグ (迷惑メール);このタグは、[迷惑メール] フォルダー内のアイテムに自動的に適用されます。  <br/> |
    |1 か月で削除  <br/> |30日以上経過したアイテムを完全に削除します。 ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup> <br/> |組み込み  <br/> |作成者このタグは、ユーザーが適用することができます。  <br/> |
    |1 年で削除  <br/> |過去365日のアイテムを完全に削除します。 ユーザーは、これらのアイテムを削除してから14日後に復元できます。<sup>\*</sup> <br/> |組み込み  <br/> |作成者このタグは、ユーザーが適用することができます。  <br/> |
    |削除しない  <br/> |このタグは、アイテム保持ポリシーによってアイテムが削除されないようにします。  <br/> |組み込み  <br/> |作成者このタグは、ユーザーが適用することができます。  <br/> |
    |個人 - 1 年でアーカイブへ移動  <br/> |1年後にアイテムをアーカイブメールボックスに移動します。  <br/> |組み込み  <br/> |作成者このタグは、ユーザーが適用することができます。  <br/> |

    > <sup>\*</sup> ユーザーは、Outlook および web 上の Outlook (旧称 Outlook Web App) で削除済みアイテムを復元するツールを使用して、削除済みアイテムの保存期間 (既定では、Exchange Online では14日) 内の削除済みアイテムを復元できます。 管理者は、Windows PowerShell を使用して、削除済みアイテムの保存期間を最大で30日に増やすことができます。 詳細については、「 [Windows 版 Outlook で削除済みアイテムを復元](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)する」および「 [Exchange Online のメールボックスの削除済みアイテムの保存期間を変更](https://www.microsoft.com/?ref=go)する」を参照してください。
  
- 回復可能なアイテムを使用して、 **14 日後にアーカイブ保持タグに移動する** と、ユーザーのプライマリメールボックス内の回復可能なアイテムフォルダーの記憶域を解放することができます。 これは、ユーザーのメールボックスが保持されている場合に便利です。つまり、ユーザーのメールボックスが完全に削除されることはありません。 アイテムをアーカイブメールボックスに移動せずに、プライマリメールボックスの [回復可能なアイテム] フォルダーの記憶域のクォータに到達できるようになります。 詳細については、「 [ホールド状態のメールボックスの回復可能なアイテムのクォータを増やす](https://go.microsoft.com/fwlink/p/?LinkId=786479)」を参照してください。
