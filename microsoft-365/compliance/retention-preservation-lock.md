---
title: 保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーと保持ラベル ポリシーとともに保管ロックを使用して、規制要件を満たし、不正な管理者から保護します。
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920719"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>保管ロックを使用して、アイテム保持ポリシーと保持ラベル ポリシーへの変更を制限する

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://aka.ms/ComplianceSD)。*

保管ロックは、アイテム保持ポリシーまたは保持ラベル ポリシーをロックして、グローバル管理者を含む誰もがポリシーをオフにしたり、ポリシーを削除したり、制限を緩和したりできないようにします。 この構成は、規制要件のために必要になる場合があります。また、不正な管理者からの保護に役立ちます。

保持に関するポリシーがロックされている場合:

- だれもオフにすることはできません。
- 場所は追加できますが、削除できません
- 保持期間を延長することはできますが、減らすことはできません

つまり、ロックされたアイテム保持ポリシーを増やしたり延長したりすることは可能ですが、減らしたり、オフにしたりすることはできません。
  
> [!IMPORTANT]
> アイテム保持ポリシーまたは保持ラベル ポリシーをロックする前に、その影響を理解し、それが組織に必要であるかどうかを確認することが非常に重要です。 たとえば、規制要件を満たす必要がある場合があります。 保管ロックを適用すると、管理者はこれらのポリシーを無効にすることも削除することもできなくなります。

[発行](create-apply-retention-labels.md)または[自動適用](apply-retention-labels-automatically.md)する[アイテム保持ポリシー](create-retention-policies.md)、または保持ラベル ポリシーを作成した後、保管ロックを構成します。 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>アイテム保持ポリシーまたは保持ラベル ポリシーをロックする方法

保管ロックを使用する必要がある場合は、PowerShell を使用する必要があります。 管理者は、保管ロックが適用された後に保持に関するポリシーを無効にしたり、削除したりすることができないため、この機能の有効化は、偶発的な構成を予防するものとして UI で使用することはできません。

すべての保持に関するポリシーおよびそのいかなる構成も、保管ロックをサポートします。

1. [セキュリティ/コンプライアンス センター PowerShell に接続します](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。

2. [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy) を実行してロックするポリシーの名前を検索します。 例:
    
   ![PowerShell のアイテム保持ポリシーの一覧](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. ポリシーに保管ロックを設定するには、ポリシーの名前を指定して [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) コマンドレットを実行し、 *RestrictiveRetention* パラメーターを true に設定します。
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    例:
    
    ![PowerShell の RestrictiveRetention パラメーター](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     メッセージが表示されたら、この構成に含まれる制限事項を読んで確認し、 **Y** を選びます。
    
   ![PowerShell でアイテム保持ポリシーをロックすることを確認するプロンプト](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

アイテム保持ポリシーに保管ロックが設定されました。 確認するには、`Get-RetentionCompliancePolicy` をもう一度実行しますが、ポリシーの名前を指定してポリシー パラメーターを表示します。

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

**RestrictiveRetention** が **True** に設定されていることを確認する必要があります。 例:

![PowerShell に表示されるすべてのパラメーターを含むロックされたポリシー](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>関連項目

[情報ガバナンスおよびレコード管理の規制要件を満たすために役立つリソース](retention-regulatory-requirements.md)
