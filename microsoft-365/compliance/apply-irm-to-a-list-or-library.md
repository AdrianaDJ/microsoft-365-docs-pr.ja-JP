---
title: リストまたはライブラリに Information Rights Management (IRM) を適用する
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御し、保護することができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de0105bf61b4abbddd938a4ec7286c1919bf3985
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948485"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>リストまたはライブラリに Information Rights Management (IRM) を適用する

Information Rights Management (IRM) を使用すると、リストまたはライブラリからダウンロードされたファイルを制御し、保護することができます。
  
## <a name="administrator-preparations-before-applying-irm"></a>IRM を適用する前の管理者の準備

- Azure Information Protection からの azure Rights Management サービス (Azure RMS) と、オンプレミスの Active Directory Rights Management サービス (AD RMS) は、サイトの Information Rights Management をサポートしています。 個別または追加のインストールは必要ありません。
    
- IRM をリストまたはライブラリに適用する前に、サイトの管理者が IRM を有効にする必要があります。
    
- リストまたはライブラリに IRM を適用するには、そのリストまたはライブラリに対する管理者権限が必要です。
    
- SharePoint Online を使用している場合は、IRM で保護された大規模なファイルをダウンロードするときにタイムアウトが発生することがあります。 このような場合は、Office プログラムを使用して IRM 保護を適用し、IRM を使用しない SharePoint ライブラリに大きなファイルを保存します。
    
> [!NOTE]
> SharePoint Server 2013 を使用している場合は、組織内のユーザーが IRM を使用して保護するすべてのファイルの種類について、サーバー管理者がすべてのフロントエンド Web サーバーにプロテクターをインストールする必要があります。 
  
## <a name="apply-irm-to-a-list-or-library"></a>リストまたはライブラリに IRM を適用する
<a name="__toc256598179"> </a>

![Information Rights Management の設定](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. IRM を構成するリストまたはライブラリに移動します。
    
2. リボンの [ **ライブラリ** ] タブをクリックし、[ **ライブラリの設定**] をクリックします。 (リストで作業している場合は、[ **リスト** ] タブをクリックし、[ **リストの設定**] をクリックします)。
    
    ![リボンの [SharePoint ライブラリの設定] ボタン](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. [ **権限と管理**] で、[ **Information Rights Management**] をクリックします。 Information Rights Management のリンクが表示されない場合は、サイトで IRM が有効になっていない可能性があります。 サイトで IRM を有効にできるかどうかを確認するには、サーバー管理者に問い合わせてください。 画像ライブラリの Information Rights Management リンクは表示されません。
    
4. [ **Information Rights Management の設定** ] ページで、[ **このライブラリ内のドキュメントに対するアクセスをダウンロード時に制限** する] チェックボックスをオンにして、このリストまたはライブラリからダウンロードされるドキュメントに制限されたアクセス許可を適用します。 
    
5. [ **アクセス許可ポリシーのタイトルの作成** ] ボックスに、このポリシーを他のポリシーと区別するために後で使用できる、わかりやすい名前を入力します。 たとえば、機密扱いの会社のドキュメントが含まれるリストまたはライブラリに制限付きアクセス許可を適用する場合は、「 **会社の機密** 」と入力できます。 
    
6. [ **アクセス許可ポリシーの説明を追加** します] ボックスに、このリストまたはライブラリを使用するユーザーに表示される説明を入力します。このリストまたはライブラリでドキュメントをどのように処理するかを説明します。 たとえば、これらのドキュメントの情報へのアクセスを内部の従業員に制限する必要がある場合は、[ **他の従業員とのみ、このドキュメントの内容について意見** を入力できます。 
    
7. このリストまたはライブラリ内のドキュメントに追加の制限を適用するには、[ **オプションの表示**] をクリックして、次のいずれかの操作を行います。
    
|**これを行うには、次の手順を実行します。**|**次の手順を実行します。**|
|:-----|:-----|
|ユーザーにこのリストまたはライブラリからのドキュメントの印刷を許可する  <br/> |[ **閲覧者に印刷を許可** する] チェックボックスをオンにします。  <br/> |
|少なくとも、アイテムの表示権限を持つユーザーがドキュメントに対して埋め込みコードまたはマクロを実行できるようにします。  <br/> |[ **閲覧者に、ダウンロードしたドキュメントで機能するようにスクリーンリーダーを許可** する] チェックボックスをオンにします。  <br/> このオプションを選択すると、ユーザーはコードを実行してドキュメントのコンテンツを抽出することができます。           |
|指定した期間だけコンテンツへのアクセスを制限する場合は、このオプションを選択します。 このオプションを選択すると、指定した日数が経過すると、ユーザーの発行ライセンスが有効期限切れになり、ユーザーはサーバーに戻って資格情報を確認し、新しいコピーをダウンロードする必要があります。  <br/> |[ **ダウンロード後] を選択し、[ドキュメントのアクセス権は次の日数 (1-365) の後に期限切れになり** ます] チェックボックスをオンにして、ドキュメントを表示可能にする日数を指定します。  <br/> |
| IRM をサポートしていないドキュメントをこのリストまたはライブラリにアップロードできないようにします。  <br/>  このオプションを選択すると、ユーザーは次のファイルの種類をアップロードできなくなります。  <br/>  対応する IRM プロテクターがすべてのフロントエンド web サーバーにインストールされていないファイルの種類。  <br/>  SharePoint Server 2010 が復号化できないファイルの種類。  <br/>  他のプログラムで IRM で保護されているファイルの種類  <br/> |[ **IRM をサポートしないドキュメントのアップロードをユーザーに許可** しない] チェックボックスをオンにします。  <br/> |
|特定の日付のこのリストまたはライブラリから制限付きアクセス許可を削除します。  <br/> |[ **ライブラリへのアクセスの制限を解除** する] チェックボックスをオンにして、目的の日付を選択します。  <br/> |
|ドキュメントを開くためにライセンスが付与されているプログラムの資格情報がキャッシュされる間隔を制御します。  <br/> |[ **ユーザーはこの間隔 (日数) を使用して資格情報を確認する必要があり** ます] チェックボックスをオンにして、資格情報をキャッシュする間隔を日数で入力します。  <br/> |
|グループ保護を許可して、ユーザーが同じグループのメンバーと共有できるようにします。  <br/> |[ **グループ保護の許可**] を選択し、共有するグループの名前を入力します。  <br/> |
   
8. 必要なオプションを選択したら、[ **OK]** をクリックします。
  
## <a name="what-is-information-rights-management"></a>Information Rights Management とは
<a name="__toc256598175"> </a>

Information Rights Management (IRM) を使用すると、ユーザーがリストまたはライブラリからダウンロードされたファイルに対して実行できる操作を制限できます。 IRM は、ダウンロードされたファイルを暗号化し、それらのファイルの暗号化を解除できる一連のユーザーおよびプログラムを制限します。 また、IRM は、ファイルを読み取ることができるユーザーの権限を制限し、ファイルの印刷、ファイルからのテキストのコピーなど、そのユーザーがアクションを実行することを禁止することもできます。
  
リストまたはライブラリで IRM を使用して、機密コンテンツの伝達を制限することができます。 たとえば、今後の製品に関する情報を選択されたマーケティング担当者と共有するためにドキュメントライブラリを作成している場合は、IRM を使用して、このようなユーザーが会社の他の従業員とこのコンテンツを共有できないようにすることができます。
  
サイトでは、個々のファイルではなく、リストまたはライブラリ全体に IRM を適用します。 これにより、ドキュメントやファイルのセット全体に対して一貫したレベルの保護を実現することが容易になります。 これにより、IRM により、機密情報の使用と伝達を管理する企業ポリシーを適用することができます。
  
> [!NOTE]
> Information Rights management に関するこのページの情報は、Microsoft SharePoint Server 2013 および SharePoint Server 2016 ライセンス条項契約で「Information Rights Management」を参照している用語よりも優先されます。 
  
### <a name="how-irm-can-help-protect-content"></a>IRM がコンテンツを保護するための方法
<a name="__toc256598176"> </a>

IRM では、制限されたコンテンツを次の方法で保護することができます。
  
- 権限のない使用のためにコンテンツのコピー、変更、印刷、fax 送受信、またはコピーと貼り付けが行われないようにするために役に立ちます。
    
- Microsoft Windows の印刷画面機能を使用して、承認済みの閲覧者がコンテンツをコピーできないようにするために使用します。
    
- サーバーからダウンロードされた後に電子メールで送信された場合に、承認されていない閲覧者がコンテンツを表示できないようにするために役に立ちます。
    
- 指定した期間だけコンテンツへのアクセスを制限します。その後、ユーザーが資格情報を確認してからコンテンツを再度ダウンロードする必要があります。
    
- 組織内のコンテンツの使用と配布を管理する企業ポリシーを適用するのに役立つ
    
### <a name="how-irm-cannot-help-protect-content"></a>IRM でコンテンツを保護する方法
<a name="__toc256598177"> </a>

IRM では、制限されたコンテンツを次のように保護することはできません。
  
- 悪意のあるプログラム (トロイの木馬、キー操作ロガー、特定の種類のスパイウェアなど) による消去、盗難、取り込み、送信
    
- コンピューターウイルスの処理による損失または破損
    
- 画面に表示されるコンテンツを手動でコピーまたは再入力する
    
- 画面に表示されるコンテンツのデジタルまたはフィルムの写真
    
- サードパーティ製の画面キャプチャプログラムを使用してコピーする
    
- サードパーティ製の画面キャプチャプログラムまたはコピーと貼り付けの操作を使用したコンテンツメタデータ (列の値) のコピー
    
[Information Rights Management をリストまたはライブラリに適用する](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>リストとライブラリの IRM のしくみ
<a name="__toc256598178"> </a>

IRM 保護は、リストまたはライブラリレベルでファイルに適用されます。 ライブラリで IRM が有効になっている場合、rights management はそのライブラリ内のすべてのファイルに適用されます。 リストに対して IRM が有効になっている場合、rights management は、実際のリストアイテムではなく、リストアイテムに添付されているファイルにのみ適用されます。
  
ユーザーが IRM 対応リストまたはライブラリにファイルをダウンロードすると、承認されたユーザーのみがファイルを表示できるように、ファイルが暗号化されます。 また、各権限管理ファイルには、ファイルを表示するユーザーに制限を課す発行ライセンスが含まれています。 一般的な制限としては、ファイルを読み取り専用にし、テキストのコピーを無効にして、ユーザーがローカルコピーを保存しないようにしたり、ファイルを印刷できないようにしたりすることがあります。 IRM がサポートするファイルの種類を読み取ることができるクライアントプログラムは、権限が管理されたファイル内の発行ライセンスを使用して、これらの制限を適用します。 これは、権限が管理されたファイルがサーバーからダウンロードされた後でも、保護を保持する方法です。
  
リストまたはライブラリからファイルをダウンロードするときに適用される制限の種類は、そのファイルを含むサイトに対する個々のユーザーのアクセス許可に基づいています。 次の表では、サイトのアクセス許可が IRM アクセス許可とどのように対応するかについて説明します。
  
|**アクセス許可**|**IRM アクセス許可**|
|:-----|:-----|
|権限の管理、Web サイトの管理  <br/> |**フルコントロール** (クライアントプログラムによって定義されている): この権限では、通常、権限が管理されたコンテンツの読み取り、編集、コピー、保存、および変更のアクセス許可がユーザーに許可されます。  <br/> |
|アイテムの編集、リストの管理、ページの追加とカスタマイズ  <br/> |[**編集**]、[**コピー**]、[**保存**]: リストまたはライブラリの [Information Rights Management の設定] ページで、[**ユーザーにドキュメントの印刷を許可する**] チェックボックスがオンになっている場合にのみ、ファイルを印刷できます。  <br/> |
|アイテムの表示  <br/> |**読み取り**: ユーザーはドキュメントを読み取ることはできますが、コンテンツをコピーまたは変更することはできません。 リストまたはライブラリの [Information Rights Management の設定] ページで、[ユーザー **にドキュメントの印刷を許可する** ] チェックボックスがオンになっている場合にのみ、印刷を行うことができます。  <br/> |
|その他  <br/> |IRM アクセス許可に直接対応するその他のアクセス許可はありません。  <br/> |
   
SharePoint Server 2013 のリストまたはライブラリで IRM を有効にする場合、すべてのフロントエンド web サーバーにプロテクターがインストールされているリストまたはライブラリ内のファイルの種類のみを保護できます。 プロテクターは、特定のファイル形式の権限が管理されたファイルの暗号化と復号化を制御するプログラムです。 SharePoint には、次のファイルの種類のプロテクターが含まれています。
  
- Microsoft Office InfoPath フォーム
    
- 次の Microsoft Office プログラムの97-2003 ファイル形式: Word、Excel、および PowerPoint
    
- Office Open XML 形式の次の Microsoft Office プログラム: Word、Excel、および PowerPoint
    
- XML Paper Specification (XPS) 形式
    
前述のファイル形式に加えて、IRM を使用して他のファイルの種類を保護することを組織で計画している場合は、サーバー管理者がその他のファイル形式用にプロテクターをインストールする必要があります。
  

