---
title: Microsoft 365 のディレクトリ同期を無効にする
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: この記事では、PowerShell を使用して Microsoft 365 のディレクトリ同期を無効にする方法についての情報を確認します。
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691592"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Microsoft 365 のディレクトリ同期を無効にする
PowerShell を使用して、ディレクトリ同期を無効にすることができます。 ただし、トラブルシューティング手順としてディレクトリ同期を無効にすることはお勧めしません。 ディレクトリ同期のトラブルシューティングに関してサポートが必要な場合は、「 [Microsoft 365 のディレクトリ同期の問題を解決](fix-problems-with-directory-synchronization.md) する」を参照してください。 
  
必要に応じて、ビジネス製品の[サポートに問い合わせて](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)ください。
  
## <a name="turn-off-directory-synchronization"></a>ディレクトリ同期を無効にする  
ディレクトリ同期を無効にするには、次のようにします。
  
1. 最初に、必要なソフトウェアをインストールし、Microsoft 365 サブスクリプションに接続します。 手順については、「 [Windows PowerShell 用 Microsoft Azure Active Directory モジュールとの接続](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)」を参照してください。
    
2. ディレクトリ同期を無効にするには [、MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) を使用します。 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>このコマンドを使用する場合、ディレクトリ同期を再び有効にするには、72時間待機する必要があります。
>
 
