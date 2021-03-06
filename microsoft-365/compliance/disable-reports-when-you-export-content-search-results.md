---
title: コンテンツ検索の結果をエクスポートするときにレポートを無効にする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
ms.custom:
- seo-marvel-apr2020
description: セキュリティ & コンプライアンスセンターからコンテンツ検索の結果をエクスポートするときにレポートを無効にするには、ローカルコンピューターの Windows レジストリを編集します。
ms.openlocfilehash: 0eaf9c9d1f70e03481b00d38d2e487709329c4cd
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817856"
---
# <a name="disable-reports-when-you-export-content-search-results"></a>コンテンツ検索の結果をエクスポートするときにレポートを無効にする

電子情報開示エクスポートツールを使用して、セキュリティ & コンプライアンスセンターのコンテンツ検索の結果をエクスポートすると、エクスポートされたコンテンツに関する追加情報を含む2つのレポートが自動的に作成およびエクスポートされます。 これらのレポートは Results.csv ファイルと Manifest.xml ファイルです (これらのレポートの詳細な説明については、このトピックの「[エクスポートレポートを無効にする方法についてよく寄せられる質問](#frequently-asked-questions-about-disabling-export-reports)」を参照してください)。 これらのファイルは非常に大きくなる可能性があるため、ダウンロード時間を短縮し、これらのファイルがエクスポートされないようにすることによって、ディスク領域を節約できます。 これを行うには、検索結果のエクスポートに使用するコンピューターで Windows レジストリを変更します。 後でレポートを含める必要がある場合は、レジストリ設定を編集できます。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>レジストリ設定を作成してエクスポートレポートを無効にする

コンテンツ検索の結果をエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 電子情報開示エクスポートツールが開いている場合は、それを閉じます。
    
2. 無効にするエクスポートレポートに応じて、次の手順のいずれかまたは両方を実行します。
    
    - **Results.csv**
    
      ファイル名サフィックス .reg を使用して、次のテキストを Windows レジストリファイルに保存します。たとえば、DisableResultsCsv のようにします。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      ファイル名サフィックス .reg を使用して、次のテキストを Windows レジストリファイルに保存します。たとえば、DisableManifestXml のようにします。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. エクスプローラーで、前の手順で作成した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。 
    
5. 続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>レジストリ設定を編集してエクスポートレポートを再度有効にする

前の手順で .reg ファイルを作成して Results.csv を無効に Manifest.xml した場合は、それらのファイルを編集して、検索結果と共にエクスポートされるようにレポートを再度有効にすることができます。 その後、結果をコンテンツ検索にエクスポートするために使用するコンピューターで、次の手順を実行します。
  
1. 電子情報開示エクスポートツールが開いている場合は、それを閉じます。
    
2. 前の手順で作成した .reg の編集ファイルのいずれかまたは両方を編集します。
    
    - **Results.csv**
    
        DisableResultsCsv ファイルをメモ帳で開き、の値をに変更して、 `False` `True` ファイルを保存します。 たとえば、ファイルを編集した後、次のように表示されます。
    
        ```text
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        DisableManifestXml ファイルをメモ帳で開き、の値をに変更して、 `False` `True` ファイルを保存します。 たとえば、ファイルを編集した後、次のように表示されます。
    
      ```text
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. エクスプローラーで、前の手順で編集した .reg ファイルをクリックまたはダブルクリックします。
    
4. [ユーザーアクセス制御] ウィンドウで、[**はい**] をクリックしてレジストリエディターに変更を許可します。 
    
5. 続行するように求めるメッセージが表示されたら、[**はい**] をクリックします。
    
    レジストリエディターに、設定が正常にレジストリに追加されたことを示すメッセージが表示されます。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>エクスポートレポートを無効にする方法についてよく寄せられる質問

 **Results.csv レポートと Manifest.xml レポートとは**
  
Results.csv ファイルと Manifest.xml ファイルには、エクスポートされたコンテンツに関する追加情報が含まれています。
  
- **Results.csv**検索結果としてダウンロードされる各アイテムに関する情報を含む Excel ドキュメント。 メールの場合、結果ログには、各メッセージに関する次の情報が含まれます。 
    
  - 移行元のメールボックス内のメッセージの場所 (メッセージがプライマリ メールボックスとアーカイブ メールボックスのどちらであるかを含みます)。
    
  - メッセージが送信または受信された日付。
    
  - メッセージの件名行。
    
  - メッセージの送信者と受信者。
    
  - 検索結果をエクスポートするときに重複除去を有効にした場合の、メッセージが重複しているかどうか。 重複するメッセージには、メッセージを重複として識別する**親 ItemId**の列に値が設定されます。 **親 ItemId**列の値は、エクスポートされたメッセージの [ **Item DocumentId** ] 列の値と同じです。 
    
    SharePoint と OneDrive for Business サイトのドキュメントの場合、結果ログには、各ドキュメントに関する以下の情報が含まれています。
    
  - ドキュメントの URL。
    
  - ドキュメントがあるサイト コレクションの URL。
    
  - ドキュメントが最後に変更された日付。
    
  - ドキュメントの名前 (これは、結果のログの [件名] 列にあります)。
    
- **Manifest.xml**検索結果に含まれる各アイテムに関する情報を含むマニフェストファイル (XML 形式)。 このレポートの情報は Results.csv レポートと同じですが、電子情報開示参照モデル (EDRM) によって指定された形式になっています。 EDRM の詳細については、「」を参照 [https://www.edrm.net](https://www.edrm.net) してください。
    
 **これらのレポートのエクスポートを無効にする必要がある場合**
  
特定のニーズに応じて異なります。 多くの組織では、検索結果に関する追加情報は必要ありません。これらのレポートは必要ありません。
  
 **この操作を実行する必要があるコンピューター**
  
 電子情報開示エクスポートツールを実行しているローカルコンピューターのレジストリ設定を変更する必要があります。 
  
 **この設定を変更した後、コンピューターを再起動する必要がありますか。**
  
いいえ、コンピューターを再起動する必要はありません。 しかし、電子情報開示エクスポートツールが実行されている場合は、レジストリ設定を変更した後、それを閉じてから再起動する必要があります。
  
 **既存のレジストリキーを編集するか、新しいキーを作成しますか?**
  
このトピックの手順で作成した .reg ファイルを初めて実行するときに、新しいレジストリキーが作成されます。 その後、.reg の編集ファイルを変更して再実行するたびに、この設定が編集されます。
