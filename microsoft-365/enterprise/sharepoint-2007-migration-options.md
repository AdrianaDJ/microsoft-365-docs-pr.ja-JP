---
title: 検討する SharePoint 2007 移行オプション
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: この記事には、SharePoint Server 2007 を使用してアップグレードを計画するユーザー向けの情報が記載されています。
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694956"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>検討する SharePoint 2007 移行オプション

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft SharePoint 2007 と SharePoint Server 2007 のサポートが終了しました。 アップグレード時間 この記事では、移行オプションに関する情報を提供します。
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>SharePoint の一般的なアップグレード戦略

SharePoint Server 環境をアップグレードするには、複数の方法があります。 Microsoft Office SharePoint Server 2007 ファームを使用している場合は、次のアップグレード方法の例を参照してください。
  
- データベース接続
    
- 並行アップグレード
    
- 一括アップグレード
    
- ハイブリッドアップグレード (切断されたデータベースを使用したインプレース/データベースの接続)
    
- SharePoint ハイブリッド (オンプレミスの SharePoint へのオンライン接続)
    
- サイトコレクションまたはライブラリ間でデータを手動で移動する
    
- FastTrack ウィザードを Microsoft 365 にアップグレードする ([SharePoint Online 展開アドバイザー](https://aka.ms/spoguidance))
    
- Microsoft 365 での SharePoint Online (SPO) への移行 API
    
最適な機能
  
ファームがどのような目的で使用されているかについての知識は、アップグレードに関しての戦術的な強度です。 ユーザーが SharePoint ファームを使用する方法は、オプションから選択するのに役立ちます。
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 にも段階的なアップグレードがありますが、ここでは説明していません。 手順固有のアップグレードに関する記事の一覧については、「 [SharePoint Server 2007 のサポート終了ロードマップ](sharepoint-2007-end-of-support.md)」を参照してください。 
  
アップグレードする SharePoint のバージョンについて、 [製品のライフサイクル](https://support.microsoft.com/lifecycle/search) およびシステム要件を必ず確認してください。 これは、次のアップグレードが必要になる場合があることに注意してください (たとえば、SharePoint Server 2010 のような従来の製品を使用してアップグレードを計画し、サポートの終了日を知っていることを確認してください)。また、プランをサポートするハードウェアがあるかどうかを確認してください。 
  
クラウド内の一部の SharePoint サイトを Microsoft 365 に移行することを計画している場合は、 [microsoft 365 および Office 365 サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)へのリンクをブックマークにする必要があります。 SharePoint Online の機能と、それらがオンプレミスの SharePoint Server とどのように異なるかについては、サービスの説明を参照してください。 機能している Microsoft Office SharePoint Server 2007 ファームをアップグレードします。 インストールに壊れたサイトがある場合は、アップグレード前に修正してください。
  
## <a name="a-note-about-managing-risk"></a>リスク管理に関する注意事項

' Side-by-side ' などのメソッドは、アップグレードロジックのスキームで重要です。 並行してアップグレードする場合は、Microsoft Office SharePoint Server 2007 ファームを維持していますが、新しいハードウェアでそのファームの次のバージョン (SharePoint Server 2010) をビルドします。 これは、次の3つの方法で役に立ちます。
  
1. データベース接続を使用して、Microsoft Office SharePoint Server 2007 データベースのバックアップを作成し、それらを個別にアップグレードする場所があります。
    
2. Microsoft Office SharePoint Server 2007 ファームで使用されている重要なドキュメントライブラリとその他の情報が少数しかないことがわかった場合は、Microsoft Office SharePoint Server 2007 から SharePoint Server 2010 にデータを手動で移動するか、または特定のサイトと web のみを次のバージョンに移動することを選択できます
    
3. Microsoft Office SharePoint Server 2007 のサーバーファームの方が、アップグレードの間にファームに格納されているデータをより安全なものにすることができます。
    
一括アップグレードなどの方法は、Microsoft Office SharePoint Server 2007 ファーム上で直接動作し、パスを破棄して pristine 環境で再度開始する簡単なオプションを提供します。 可能な限り、安全策をいくつか (元の環境のバックアップの実行とテストなど) に構築します。 たとえば、Microsoft Office SharePoint Server 2007 ファームが仮想で、バックアップと復元の目的で複製されている場合は、アップグレードのためにサービス時間の前に、最新のデータベースをバックアップして復元します。 データベースバックアップを復元するオプションを選択すると、フェイルセーフが提供されるだけでなく、安心感を得ることができます。
  
> [!TIP]
> ベストプラクティスアップグレードに関するドキュメントは、 [Microsoft Office SharePoint server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx)、 [sharepoint server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx)、 [Sharepoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)、および [sharepoint server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx)に存在します。 また、アップグレードまたは Microsoft 365 移行に携わっている [Microsoft パートナー](https://partnercenter.microsoft.com/pcv/search) を検索することもできます。 
  
## <a name="make-your-plan"></a>プランを作成する

アップグレードが必要な場合は、プランが必要であり、これらの場合に1つのサイズが調整されません。 プランは、「SharePoint Online を使用して Microsoft 365 サブスクリプションを作成する」、「ドメインを登録して、自分のファイルを保存するようにユーザーをリダイレクトする」という簡単なものにすることができます。 になっていない可能性があります。 その決定は自分とユーザーが実際に必要とするものになります。
  
> [!NOTE]
> ライフサイクルが終了したソフトウェアで実行するのは危険です。 サポートされていない製品は、問題が見つかったときにパッチが適用されなくなりました。 これは、新しいセキュリティの脅威が発生した場合に、ライフサイクル終了製品がサポートされなくなるため、セキュリティ更新プログラムや修正プログラムが適用されないことも意味します。 このような状況は避けてください。 
  
### <a name="first-know-your-farm"></a>最初に、ファームを把握します。

アップグレード時には、組織でのファームの動作に基づいて意思決定を行う必要があります。 満たす必要があるもの 役割とは 会社内の各ファームは、異なる役割を持つ場合があります。 SharePoint ファームの一部は  *重要な*  場合があり、ファイルアーカイブの場合もあります。 または、ファームで多数の役割が一度にいっぱいになっている場合は、サイトコレクション、web、またはドキュメントライブラリの種類、カスタマイズ、およびそれらの重要度について知る必要があります。 このレベルでデータを分析することは多くの作業と似ていますが、アップグレードや移行を行う前に、ドメインをマスタ化するための時間と労力を節約できます。 すべての可動パーツと、最も重要なビットを把握したら、outgrown が何をしているかを把握して、そのまま残しておくこともできます。 この点については、お話を進めることができます。 
  
そのため、SharePoint Server ファームに関して、ユーザーにとって最も重要なことは何ですか。
  
- 組み込みの SharePoint 機能
    
- 大規模データコーパス (ファイルのアーカイブなど)
    
- 可用性
    
- ファーム内の重要なアプリ、web パーツ、またはドキュメント (ミッションクリティカルなファーム)
    
- コンプライアンス標準が満たされている
    
- カスタマイズ
    
SharePoint ファームからビジネスに不可欠なものを実行する場合、クライアントサービス要件に関する重要なデータの大規模なカタログのように動作すると、「重要なアプリ」の横にチェックマークを置くことができます。また、「可用性」にもかかわらず、SharePoint をしばらく使用していない場合は、ビジネスに影響を与えます。 同様に、ファームが提供する重要なサービスは、カスタムコード、サイト定義、または共同作業する多数のカスタマイズに基づいているため、[カスタマイズ] をチェックすることもできます。
  
ソフトウェアに組み込まれている機能を使用せずに SharePoint の要件を満たしていて、通常の管理と保守を行う必要がある場合は、「組み込みの SharePoint」が選択されている可能性があります。これは、以前のバージョンの SharePoint を使用していた可能性もあります。 つまり、必要なものは既に存在しており、現時点では、Microsoft Office SharePoint Server 2007 のサポート終了時までアップグレードする必要はありません。
  
これらの項目を行頭文字に使用する場合は、アップグレードの基準を作成します。 言い換えると、アップグレードではこのバーを考慮する必要があります。 これにより、現在のニーズに合わない方法を除外することができます。
  
### <a name="a-simple-sample-plan"></a>簡単なサンプルプラン

リーダーやその他の管理者との間で、SharePoint のアップグレードにかかる可能性があるため、より多くの合意が必要になることがあります。 SharePoint Server 管理者は、多くの場合、Microsoft SQL Server 管理者と協力して、ネットワークおよびセキュリティチームなどを共同作業します。 関係者が多い場合は、アップグレードと移行の計画を作成するか、調整する必要があります。 たとえば、データを移行して、会社の一部が Microsoft 365 の SharePoint Online を使用するようにした場合、ネットワーク内でパフォーマンスを調整またはテストする必要が生じる可能性があります。 影響を受ける teams について事前に通知する必要があります。
  
この簡単なサンプルでは、SharePoint 管理者の提案を示し、関係者全員が同意した計画を示します。 わかりやすくするために、契約と決定事項を文書化します。
  
この計画は、ファームの詳細な分析の後から開始し、ファーム、ペインポイント、およびその他の重要な情報を特定して、いくつかのアップグレードオプションを絞り込むことができるようにします。 その後、SharePoint 管理者によるアップグレード提案が行われ、関係者はアクションプランに同意します。
  
My ' 最も重要な行頭文字リスト:
  
- 可用性、SharePoint に組み込まれている機能、コンプライアンス基準。
    
- データのほとんどは3つのサイトコレクション上にあり、開発チームによって使用される1つの会議ワークスペースと、世界中の複数のタイムゾーンにおいて特に重要であり、頻繁に使用されています。
    
- 広く使用されている seventeen 他のサイトがあります。
    
- 2つのドキュメントライブラリ (ルートサイトコレクション上の会議ワークスペースとドキュメント) は、最大でも、8000個を超えるドキュメントがあります。 アーカイブされたドキュメントとリストが多数あり、スプレッドシートの添付ファイルが含まれています。
    
- 機密データを保有する必要があるライブラリには、14個の一覧があります。
    
- どこにいても、ホールドを行い、電子情報開示を行うことができる必要があります。
    
- このようなデータの一部は、InfoSec ルールのため、オンプレミスのままにしておく必要があります。
    
 **アップグレードと移行の選択肢:**
  
| はい | いいえ |
|:-----|:-----|
|データベース接続を使用してデータベースをアップグレードする  <br/> |一括アップグレード  <br/> |
|ファームを並行してアップグレードする  <br/> |ハイブリッドアップグレード  <br/> |
|Microsoft 365 での SPO への移行 API (個人用サイトデータの場合)  <br/> |SharePoint ハイブリッド (まだ必要ではありません)  <br/> |
|重要なデータを SharePoint Online に手動で移行することがある  <br/> |FastTrack ウィザードの Microsoft 365 へのアップグレード  <br/> |
   
 **提案されているプラン:**
  
最初にデータベースをアップグレードできるように、オンプレミスのバージョンの SharePoint と共存して、いくつかの仮想化を行います。 SharePoint 2007 から SharePoint 2010 に移動します。 管理者と開発結果のファームをテストします。 ユーザーが結果のファームをテストします。 この間に発生するすべての停止の問題を修正します。 再び並行して、SharePoint 2010 データベースを SharePoint 2013 にアップグレードします。 テストします。 ユーザーテスト/パイロット。 この間に発生するすべての停止の問題を修正します。
  
- SPO とのフェデレーションハイブリッド検索がニーズを満たしているかどうかを検討します。
    
- ここから SharePoint Online にアップグレードする場合は、 [Fasttrack アシスタンス](https://fasttrack.microsoft.com) をご検討ください。 
    
- Microsoft 365 サブスクリプションにオフロードできるサイトコレクションがあるかどうかを判断します。 (Microsoft 365 は、多くの [コンプライアンス基準](https://technet.microsoft.com/library/office-365-compliance.aspx)を満たしています。 Microsoft 365 は、 [電子情報開示](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) を行い、コンプライアンスセンターを通じて [保持](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) することができます。) 
    
それ以外の場合は、SharePoint Server 2016 への並行アップグレードを続行します。
  
> [!NOTE]
> アップグレードを計画している管理者による推奨事項と実際のプロセスの間に、その他の関係者との間で行われる会話があります。 たとえば、経済的な管理者がプランを変更する場合があります。 最終的な決定事項については、合意された計画が進む前に、その計画を文書化する必要があります。 これは次のようなものになります。 
  
 **自分のアクションプラン:**
  
オンプレミスでは、仮想環境を使用して既定の SharePoint Server 2010 および2013を構築しています。 SharePoint Server 2016 は、2016のシステム要件を満たす新しいハードウェア上に構築されます。 データベース接続を使用して、SharePoint 2007 から、データベースと SharePoint Server 2016 のすべてのバージョンをアップグレードします。 ネイティブの機能がニーズを満たしていない場合、コアのカスタマイズは SharePoint Server 2016 環境で再作成およびテストされます。 成功した場合は、アップグレードされたデータベースを備えた新しいハードウェア上にオンプレミスのファームが存在し、カスタマイズが少なくなります。 ここでは、アップグレードされたコンテンツデータベースを SharePoint Server 2013 の新しいサイトコレクションに接続し、テスト、ユーザーテスト/パイロットを実行してから、新しい SharePoint Server 2016 環境への DNS カットオーバーを実際に使用できるようにします。
  
- 現時点では、SharePoint Server 2016 と SharePoint Online の間のフェデレーションハイブリッドは考慮されません。
    
- バニティドメインを使用して新しい SPO サイトに、または最終的に OneDrive for Business ストレージに移行することができるサイトの見積もり35% サイトを変換する他の機会を探したり、新しいサイトを SPO にルーティングしたりできます。
    
- 移行の一部の一部は、OneDrive for Business の個人用サイトにドラッグアンドドロップするか、または移行 API を使用して手動で行う必要があります。
    
詳細な手順、または特定のアップグレード手順へのリンクの数は、計画に従う必要があります。 MOSS 2007 コンピューターを使用停止にしないでください。比較するために、仮想環境を維持する必要があります。ただし、ユーザーが SharePoint Server 2016 にリダイレクトされると、アップグレードが完了します。
  
メソッドを選択する主な要因として、アップグレードの総コストと時間単位のコストがあります (これについては、「SharePoint 移行ロードマップ」の記事を参照してください)。 しかし、前もって計画を立てることにより、期待値を設定し、適切に選択し、成功を予測することができます。
  
## <a name="related-links"></a>関連リンク

[Office 2007 のサーバーとクライアントからのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft のライフサイクルポリシーとライフサイクルの検索](https://support.microsoft.com/lifecycle)
  
[アップグレードまたは移行に役立つ Microsoft パートナーを検索する](https://partnercenter.microsoft.com/pcv/search)
  

