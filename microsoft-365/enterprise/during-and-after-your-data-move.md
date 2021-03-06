---
title: データの移行中および移行後
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: データの移動は、Microsoft がテナントのサービスと関連データを新しいデータセンター geo に移動するときに発生するバックエンドの操作です。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca3159aeb951fb0cb3bf3aba953979dabc6ba024
ms.sourcegitcommit: 1db81b85d327fe423695ce675ad325e538417211
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2020
ms.locfileid: "49349258"
---
# <a name="during-and-after-your-data-move"></a>データの移行中および移行後

データの移行は、エンドユーザーへの影響を最小限に抑えたバックエンドの操作です。 Microsoft が各サービスとお客様のテナントの関連データを新しいデータセンター geo に移動する際には、何も行う必要はありません。 データの転送および検証は事前にバックグラウンドで行われ、ユーザーへの影響は最小限に抑えられます。
  
> [!NOTE]
> 移動はサービスごとに、異なる時間に行われます。結果として、サービスごとに異なる時間に、説明されているような機能制限がかかります。 
  
Exchange Online、SharePoint Online、Teams チャットサービスのそれぞれについて移行が完了したら、Microsoft 365 メッセージセンターで確認を行います。 次の表に示されているように、登録期間が終了してから最大24か月を経過して、新しいデータセンター geo に移動中のコア顧客データを完成させることができます。   

|**国がサインアップしているお客様**|**完了したすべての移動**|
|:-----|:-----|
|オーストラリア、ニュージーランド、フィジー  <br/> |2022年7月1日  <br/> |
|日本  <br/> |2022年7月1日  <br/> |
|インド  <br/> |2022年7月1日  <br/> |
|カナダ  <br/> |2022年7月1日  <br/> |
|韓国  <br/> |2022年7月1日  <br/> |
|英国  <br/> |2022年7月1日  <br/> |
|フランス  <br/> |2022年7月1日  <br/> |
|アラブ首長国連邦  <br/> |2022年7月1日  <br/> |
|南アフリカ  <br/> |2022年7月1日  <br/> |
|スイス、リヒテンシュタイン  <br/> |2022年7月1日  <br/> |
|ノルウェー  <br/> |2022年11月1日  <br/> |
|ドイツ  <br/> |2023年5月1  <br/> |
|ブラジル  <br/> |2023年6月1日  <br/> |

## <a name="exchange-online"></a>Exchange Online

各ユーザーをシングル テナントの新しいデータセンター geo に移動するのに時間がかかるため、移動中は一部のユーザーが古いデータセンター geo のまま、他のユーザーは新しいデータセンター geo という状態になります。 これは、複数のメールボックスへのアクセスを必要とする一部の機能が、移行プロセスの間に完全には機能しない場合があることを意味します。これは、先週まで可能です。 該当する機能については、この後のセクションで取り上げます。
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Outlook Web Access で "共有フォルダー" を開く

一部のユーザーは、Outlook Web Access で "共有フォルダー" 機能を使用して、別のメールボックスから共有メール フォルダー (ユーザーが読み取りまたは書き込みアクセス許可を持つフォルダー) を開きます。次の表に、メールボックスの移動中に、共有フォルダーへのアクセス権がどのように動作するかを取り上げます。共有メールボックスへのフル アクセス許可があるユーザーは、移動中に Outlook Web Access を使用してメールボックスを開くことができます。 
  
|**構成**|**説明**|
|:-----|:-----|
|別のメールボックスへのメールボックス フォルダー アクセス許可があるユーザー  <br/> |制限される可能性があります。  <br/> テナントの移動中にユーザー A とメールボックス B が同じ geo になく、ユーザー A が持っているアクセス許可がメールボックス B の特定のフォルダーに対してのみの場合、ユーザー A は Outlook Web Access でメールボックス B のフォルダーを開くことができません。  <br/> 共有フォルダーを追加するには、左側のナビゲーション ウィンドウでユーザー名を右クリックし、 **[共有フォルダーの追加]** を選択します。  <br/> |
|別のメールボックスへのメールボックス フル アクセス許可があるユーザー  <br/> |完全にサポートされます。  <br/> ユーザー A がメールボックス B に "フルアクセス" アクセス許可を持っている場合、ユーザー A は Outlook Web Access の左側のナビゲーションパネルで共有フォルダーをクリックして、メールボックス B が表示されているウィンドウを開くことができます。 ユーザーは、移動中に Outlook Web Access を使用して共有メールボックスを開くことができ、悪影響を与えることはありません。 制限は、メールボックス内のフォルダー レベルの共有だけに適用されます。           |
  
## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online を移行すると、以下のサービスのデータも移行されます。
  
- One Drive for Business
    
- Microsoft 365 Video services
    
- ブラウザー内の Office
    
- Microsoft 365 Apps for enterprise
    
- Visio Pro for Microsoft 365
    
SharePoint Online データの移行が完了すると、次に示す影響が現れる可能性があります。
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Video Services

- ビデオのデータの移動は、SharePoint Online にある残りのコンテンツの移動より時間がかかります。
    
- SharePoint Online のコンテンツを移行すると、ビデオが再生できない時間が生じます。
    
- 以前のデータセンターからコード変換されたコピーを削除し、新しいデータセンターでコードを再変換しています。
    
### <a name="search"></a>検索

SharePoint Online データを移行する過程で、検索インデックスと検索設定を新しい場所に移行します。SharePoint Onlineデータの移行が **完了** するまで、ユーザーは引き続き元の場所でインデックスを利用できます。SharePoint Online データの移行が完了すると、新しい場所で、検索機能によってコンテンツのクロールが自動的に再開されます。これより以降、ユーザーは移行したインデックスを利用できます。移行後に生じたコンテンツの変更は、クロールで反映されるまで移行したインデックスに組み込まれません。SharePoint Online データの移行が完了した直後に結果の鮮度が低いと感じる顧客はほとんどいませんが、その後の 24 時間から 48 時間には一部の顧客が鮮度の低下に気付く可能性があります。 
  
次の検索機能が影響を受けます。
  
- 検索結果と検索 Web パーツ:移行後に生じた変更は、クロールで反映されるまで結果に含まれません。 
    
- Delve:移行後に生じた変更は、クロールで反映されるまで Delve に含まれません。
    
- サイトの人気と検索に関するレポート: 新しい場所での Excel レポートのカウントには、移行した数、および SharePoint Online データの移行完了後に実行された利用状況レポートの数のみが含まれます。中間の期間の数はすべて失われ、回復することはできません。この期間は、通常、2、3 日です。顧客によっては情報が失われている期間が増減することもあります。
    
- ビデオ ポータル:ビデオ ポータルの表示回数と統計情報は Excel レポートの統計情報に基づいているため、ビデオ ポータルの表示回数と統計情報は、Excel レポートと同じ期間失われます。
    
- 電子情報開示:移行中に変更されたアイテムは、クロールで変更が反映されるまでは表示されません。
    
- データ損失防止 (DLP):クロールで変更が反映されるまで、変更されたアイテムに対してポリシーは適用されません。

## <a name="microsoft-teams"></a>Microsoft Teams

Microsoft は、Exchange Online、SharePoint Online、OneDrive for Business に加えて、Teams chat service のデータをローカルデータセンターに移行します。

- Teams のチャットメッセージ (プライベートメッセージやチャネルメッセージを含む)。
- チャットで使用される Teams 画像。

Teams ファイルは SharePoint Online に格納され、Teams チャットファイルは OneDrive for Business に保存されます。 ボイスメール、予定表、チャット履歴、および連絡先は、Exchange Online に格納されます。 多くの場合、Exchange Online、SharePoint Online、OneDrive for Business は、ローカルのデータセンター geo のお客様によって既に使用されており、資格のあるお客様の国の Microsoft 365 移行プログラムの一部でもあります。

## <a name="skype-for-business"></a>Skype for Business

Skype for Business の移動は利用できなくなりました。  [Skype For Business Online は](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) 、2021年7月31日に廃止されます。 その時間が過ぎると、サービスにアクセスできなくなります。 
  
## <a name="related-topics"></a>関連項目 
 
[データ移行を申請する方法](request-your-data-move.md)
    
[データ移行についての一般的な FAQ](data-move-faq.md)
  
[Microsoft Dynamics CRM Online の新しいデータ センター geo](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure のリージョン](https://azure.microsoft.com/regions/)
