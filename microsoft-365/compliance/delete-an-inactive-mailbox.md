---
title: 非アクティブなメールボックスを削除する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 365 の非アクティブなメールボックスの内容を保持する必要がなくなった場合は、非アクティブなメールボックスを完全に削除することができます。
ms.openlocfilehash: 05357ce1b3e10394854844f15ec6a18c1c427d5b
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817896"
---
# <a name="delete-an-inactive-mailbox"></a>非アクティブなメールボックスを削除する

An inactive mailbox is used to preserve a former employee's email after he or she leaves your organization. When you no longer need to preserve the contents of an inactive mailbox, you can permanently delete the inactive mailbox by removing the hold. Also, it's possible that multiple holds might be placed on an inactive mailbox. For example, an inactive mailbox might be placed on Litigation Hold and on one or more In-Place Holds. さらに、(Office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成された) アイテム保持ポリシーは、非アクティブなメールボックスに適用されることがあります。 非アクティブなメールボックスを削除するには、保留リストとアイテム保持ポリシーをすべて削除する必要があります。 After you remove the holds and retention policies, the inactive mailbox is marked for deletion and is permanently deleted after it's processed.
  
> [!IMPORTANT]
> メールボックスのコンテンツを保持するためのさまざまな方法に投資し続けるので、Exchange 管理センターでのインプレースホールドの廃止を発表しています。 つまり、非アクティブなメールボックスを作成するには、訴訟ホールドとアイテム保持ポリシーを使用する必要があります。 2020年7月1日以降、Exchange Online に新しいインプレースホールドを作成することはできません。 ただし、非アクティブなメールボックスに設定されたインプレースホールドの保持期間を変更することはできます。 ただし、2020年10月1日以降、保持期間を変更することはできません。 インプレースホールドを削除しても、非アクティブなメールボックスを削除することはできません。 インプレース保持されている既存の非アクティブなメールボックスは、保留が解除されるまで保持されます。 インプレースホールドが廃止された場合の詳細については、「[従来の電子情報開示ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。
  
保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](#more-information)」セクションを参照してください。
  
## <a name="before-you-delete-an-inactive-mailbox"></a>非アクティブなメールボックスを削除する前に

- 非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。 Exchange 管理センター (EAC) を使用することはできません。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。 非アクティブなメールボックスからインプレース ホールドを削除する場合は、Exchange Online PowerShell または EAC を使用できます。 
    
- 非アクティブなメールボックスの内容は、ホールドを解除して、非アクティブなメールボックスを削除する前に別のメールボックスにコピーできます。 詳細については、「 [Office の非アクティブなメールボックスを復元する 365](restore-an-inactive-mailbox.md)」を参照してください。
    
- 非アクティブなメールボックスからホールドまたはアイテム保持ポリシーを削除すると、そのメールボックスの回復可能な削除によって削除されたメールボックスの保存期間が切れた場合、そのメールボックスは完全に削除されます。 削除後に回復することはできません。 ホールドを解除する前に、メールボックスの中身が不要かどうかを確認してください。 非アクティブなメールボックスを再アクティブ化することが必要な場合、メールボックスを回復することは可能です。 詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。
    
- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

前述したように、非アクティブなメールボックスに訴訟ホールド、インプレースホールド、またはアイテム保持ポリシーを設定することができます。 最初の手順として、非アクティブなメールボックスのホールドを識別します。
  
組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。たとえば、2 つの非アクティブなメールボックスの次の結果は、1 つの訴訟ホールドが Ann Beebe に設定され、2 つのインプレース ホールドが Pilar Pinilla に設定されていることを示しています。 
  
```text
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 多数のインプレース ホールドが非アクティブなメールボックスに設定されている場合、一部のインプレース ホールドの GUID が表示されません。 すべてのインプレースホールド Guid を表示するには、次のコマンドを実行します。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>手順 2:非アクティブなメールボックスから保留リストを削除する

非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。 
  
### <a name="remove-a-litigation-hold"></a>訴訟ホールドを削除する

前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。
  
```powershell
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。 
  
### <a name="remove-in-place-holds"></a>インプレース ホールドを削除する

 非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。 
  
- **インプレースホールドオブジェクトを削除する**完全に削除する非アクティブなメールボックスが、インプレースホールドの唯一のソースメールボックスである場合は、インプレース保持オブジェクトを削除するだけです。 
    
    > [!NOTE]
    > インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。 
  
- **インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>EAC を使用してインプレース ホールドを削除する

1. 削除するインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、完全に削除する非アクティブなメールボックスに設定されているインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース ホールドの GUID を使用します。
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. 削除するインプレースホールドを選択し、[編集] 編集アイコンを**クリックし** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**, uncheck the **Place content matching the search query in selected mailboxes on hold** box, and then click **Save**.
    
5. On the **In-Place eDiscovery &amp; Hold** page, select the In-Place Hold again, and then click **Delete**![Delete icon](../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png).
    
6. 警告が表示されたら、 **[はい]** をクリックして、インプレース保持を削除します。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Exchange Online PowerShell を使用してインプレース ホールドを削除する

1. 削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。
    
   ```powershell
   $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
   ```

2. インプレース ホールドの保留リストを無効にします。
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
   ```

3. インプレース ホールドを削除します。
    
   ```powershell
   Remove-MailboxSearch $InPlaceHold.Name
   ```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>EAC を使用してインプレース ホールドから非アクティブなメールボックスを削除する

1. 非アクティブなメールボックスに設定されたインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、メールボックスに設定されたインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース ホールドの GUID を使用します。
    
   ```powershell
   Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
   ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. 非アクティブなメールボックスに配置されたインプレースホールドを選択し、[編集アイコンの**編集**] をクリックし ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ます。
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **Sources**.
    
5. ソース メールボックスのリストで、削除する非アクティブなメールボックスの名前をクリックして、 **[削除]**![[削除] アイコン](../media/adf01106-cc79-475c-8673-065371c1897b.gif)をクリックします。
    
6. **[保存]** をクリックして変更を保存します。操作が正常に完了したことを示すメッセージが表示されます。 
    
7. 手順 1 から手順 6 を繰り返して、非アクティブなメールボックスに設定された他のインプレース保持を削除します。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Exchange Online PowerShell を使用してインプレース保持から非アクティブなメールボックスを削除する

インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。 
  
1. 非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](#step-1-identify-the-holds-on-an-inactive-mailbox) で取得したインプレース保持の GUID を使用します。
    
    ```powershell
    $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
    ```

2. 非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。 
    
   ```powershell
   $InPlaceHold.Sources
   ```

   **注:** インプレースホールドの*Sources*プロパティは、 *LegacyExchangeDN*プロパティによってソースメールボックスを識別します。 このプロパティは非アクティブなメールボックスを一意に特定するため、インプレース ホールドの *Sources* プロパティを削除すると、正しくないメールボックスの削除を回避できます。 これはまた、2 つのメールボックスが同じエイリアスまたは SMTP アドレスを持っているときの問題も回避できます。 
   
3. 変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。 
    
    ```powershell
    $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
    ```

    たとえば、次のコマンドは、Pilar Pinilla の非アクティブなメールボックスを削除します。
    
    ```powershell
    $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/ cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
    ```

4. 変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。
    
   ```powershell
   $InPlaceHold.Sources
   ```

5. 非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。
    
   ```powershell
   Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
   ```

6. インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。
    
   ```powershell
   Get-MailboxSearch $InPlaceHold.Name | FL Sources
   ```

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。Exchange Online で回復可能な削除によって削除されたメールボックスの保存期間は 30 日です。つまり、回復可能な削除によって削除されてから 30 日以内なら、メールボックスを復元できます。30 日が経過すると、回復可能な削除によって削除されたメールボックスは完全削除のマークが付けられ、回復できなくなります。 
    
- **非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。** 非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。 この保存期間は、メールボックスが最初に非アクティブになった日から始まります。 この日付は、対応するユーザーアカウントが削除された日付、または**メールボックスの削除**コマンドレットを使用して Exchange Online メールボックスが削除された日付である、回復可能な削除日と呼ばれます。 回復可能な削除によって削除された日は、保留リストを削除した日ではありません。 
    
- **ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が 30 日より前であっても、ホールドを解除するとすぐにメールボックスが完全に削除されるということはありません。メールボックスに完全に削除するようマークが付けられ、次に処理されるときに削除されます。 
    
- **回復可能な削除によって削除されたメールボックスの保持期間は非アクティブなメールボックスにどのように影響しますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が、ホールドが解除された日付からさかのぼって 30 日目よりも前である場合は、メールボックスに完全削除のマークが付けられます。 ただし、非アクティブなメールボックスの回復可能な削除によって削除された日から 30 日が経過しないうちにホールドを解除した場合は、回復可能な削除によって削除されたメールボックスの保持期間内であれば、メールボックスを回復することが可能です。 詳細については、「 [Exchange Online でユーザーメールボックスを削除または復元](https://go.microsoft.com/fwlink/?linkid=856835)する」を参照してください。 回復可能な削除によって削除されたメールボックスの保持期間が経過した後は、非アクティブなメールボックスを回復するための手順を実行する必要があります。 詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。
    
- **ホールドを解除した後、どうすれば非アクティブなメールボックスの情報を表示できますか。** 保持が削除され、非アクティブなメールボックスが回復可能な削除によって削除されたメールボックスに戻された後は、**メールボックスの取得**コマンドレットで*Inactivemailboxonly*パラメーターを使用して返されることはありません。 ただし、 **Get-Mailbox -SoftDeletedMailbox** コマンドを使用して、メールボックスの情報を表示できます。 たとえば、次のように入力します。 
    
  ```text
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
  ```

  上記の例では、 *Whensoftdeleted*プロパティは、回復可能な削除によって削除された日付 (この例では、2014年10月30日) を示しています。 この回復可能な削除によって削除されたメールボックスが以前は、保留が削除された非アクティブなメールボックスであった場合、 *Whensoftdeleted*プロパティの値の30日後に完全に削除されます。 この場合、メールボックスは 2014 年 11 月 30 日に完全に削除されます。

