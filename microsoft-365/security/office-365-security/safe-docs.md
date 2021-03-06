---
title: Microsoft Defender for Office 365 の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 または Microsoft 365 E5 セキュリティの安全なドキュメントについて説明します。
ms.openlocfilehash: 7fbee440298aea3609665b62a946ae3ce2857e37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845482"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[安全なドキュメント] は、 [エンドポイントに Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) を使用して、 [保護さ](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)れたビューで開かれたドキュメントやファイルをスキャンする、microsoft 365 e5 または microsoft 365 E5 セキュリティの機能です。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- セーフドキュメントは、 *microsoft 365 E5* または *Microsoft 365 E5 セキュリティ* ライセンスを持つユーザーのみが利用できます。 これらのライセンスは、Microsoft Defender for Office 365 プランには含まれていません。

- 「安全なドキュメント」は、Microsoft 365 for enterprise (旧称 Office 365 ProPlus) version 2004 以降でサポートされています。

- <https://protection.office.com> でセキュリティ/コンプライアンス センターを開きます。 [ATP の安全な **添付ファイル** ] ページに直接移動するには、を開き <https://protection.office.com/safeattachmentv2> ます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。 安全なドキュメントを有効にして構成するには、組織の **管理** 役割グループまたは **セキュリティ管理者** 役割グループのメンバーである必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft はどのようにデータを処理していますか?

保護された状態を維持するために、安全なドキュメントは、分析のために [エンドポイントクラウドのファイルを Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) に送信します。 エンドポイントの Microsoft Defender がデータを処理する方法の詳細については、「 [エンドポイントのデータの保存とプライバシーに関する Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)」を参照してください。

Safe ドキュメントによって送信されたファイルは、分析に必要な時間 (通常は24時間未満) を超えて、Defender に保持されません。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する

1. [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル** ] に移動し、[ **グローバル設定** ] をクリックします。

2. [ **グローバル設定** ] が表示されたら、次の設定を構成します。

   - **Office クライアントに対して安全なドキュメントを有効** にします。トグルを右に移動して、機能をオンにします。オン ![ に ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) します。

   - **安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可** します。このオプションはオフのままにしておくことをお勧めします (トグルオフのままにし ![ ](../../media/scc-toggle-off.png) ます)。

   完了したら、 **[保存]** をクリックします。

   ![[安全な添付ファイル] ページでグローバル設定を選択した後の、安全なドキュメントの設定。](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _Enablesafedocs_ パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。
- _Allowsafedocsopen_ パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。

この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)」を参照してください。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[ **脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル** ] に移動し、[ **グローバル設定** ] をクリックし、[ **Office クライアントの安全なドキュメントを有効** にする] をオンにして、 **安全なドキュメントでファイルが悪意のある設定として識別される場合でも、[保護されたビューを使用してクリックできる**

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 次のファイルを使用して、安全なドキュメント保護をテストできます。 これらのドキュメントは、マルウェア対策およびウイルス対策ソリューションをテストするための EICAR.TXT ファイルに似ています。 これらのファイルは有害ではありませんが、安全なドキュメント保護をトリガーします。

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
