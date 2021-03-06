---
title: Microsoft 365 用のエンタープライズテスト環境の特権アクセス管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境の特権アクセス管理を有効にします。
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487590"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 用のエンタープライズテスト環境の特権アクセス管理

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

この記事では、Microsoft 365 for enterprise テスト環境のセキュリティを強化するために、特権アクセス管理を構成する方法について説明します。

Priviledged アクセス管理を構成するには、3つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 特権アクセス管理を構成する](#phase-2-configure-privileged-access-management)
- [フェーズ 3: 昇格された権限のあるタスクに承認が必要であることを確認する](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最低限の要件を持つ軽量な方法で特権アクセス管理を構成する場合は、「軽量な [基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで特権アクセス管理を構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
>[!NOTE]
>特権アクセス管理をテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメインサービスフォレストのディレクトリ同期が含まれます。 この記事はオプションとして提供されており、一般的な組織を表す環境で、特権アクセス管理をテストし、それを試してみることができます。

## <a name="phase-2-configure-privileged-access-management"></a>フェーズ 2: 特権アクセス管理を構成する

このフェーズでは、承認者グループを構成し、Microsoft 365 for enterprise テスト環境の特権アクセス管理を有効にします。 その他の詳細と、特権アクセス管理の概要については、「 [特権アクセス管理](../compliance/privileged-access-management-overview.md)」を参照してください。

組織で特権アクセスを設定して使用するには、次の手順を実行します。

#### <a name="step-1-create-an-approvers-group"></a>[手順 1: 承認者のグループを作成する](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

特権アクセスの使用を開始する前に、昇格されたタスクと特権タスクへのアクセスのための受信要求に対して、誰がだれに承認権限を付与するかを決定します。 承認者グループの一部であるすべてのユーザーは、アクセス要求を承認できます。 特権アクセスを使用するには、Microsoft 365 でメールが有効なセキュリティグループを作成する必要があります。 テスト環境で、新しいセキュリティグループに「権限のあるアクセス承認者」という名前を指定し、以前のテストラボガイドの手順で作成した「User 3」を追加します。

#### <a name="step-2-enable-privileged-access"></a>[手順 2: 特権アクセスを有効にする](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

既定の承認者グループを使用して Microsoft 365 で特権アクセスを明示的に有効にする必要があります。また、特権アクセス管理アクセス制御から除外する必要のあるシステムアカウントのセットが含まれている必要があります。 このガイドのフェーズ3を開始する前に、必ず組織で特権アクセスを有効にしてください。

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>フェーズ 3: 昇格された権限のあるタスクに承認が必要であることを確認する

このフェーズでは、特権アクセスポリシーが機能していること、および定義された昇格した権限のあるタスクを実行するためにユーザーに承認が必要であることを確認します。

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>特権アクセスポリシーで定義されていないタスクを実行する機能をテストする

最初に、テスト環境で全体管理者として構成されているユーザーの資格情報を使用して Exchange 管理 PowerShell に接続し、新しいジャーナルルールを作成します。 [New-journalrule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule)タスクは、現在、組織の特権アクセスポリシーでは定義されていません。

1. ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールにサインインし、microsoft**exchange online**リモート powershell モジュールにサインインします。

1. Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>New-JournalRule タスクの新しい特権アクセスポリシーを作成する

>[!NOTE]
>このガイドのフェーズ2の手順1と2をまだ完了していない場合は、「権限アクセス承認者」という名前の承認者グループを作成する手順に従って、テスト環境での特権アクセスを有効にしてください。

1. 資格情報を使用して [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。テスト環境のグローバル管理者アカウントです。

2. 管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [ **アクセスポリシーと要求の管理**] を選択します。

4. [ **構成ポリシー**] を選択し、[ **ポリシーの追加**] を選択します。

5. ドロップダウンフィールドで、次の値を選択または入力します。

    **ポリシーの種類**: タスク

    **ポリシースコープ**: 交換

    **ポリシー名**: 新しいジャーナルルール

    **承認の種類**: 手動

    **承認グループ**: 特権アクセス承認者

6. [ **作成**] を選択し、[ **閉じる**] を選択します。 ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。 次の手順で承認の要件をテストする前に、ポリシーが完全に有効になるまでの時間を確保してください。

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>特権アクセスポリシーで定義された New-JournalRule タスクのテスト承認要件

1. ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールを開き、microsoft**exchange online リモート**powershell モジュールにサインインします。

2. Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exchange 管理 PowerShell で "権限が不足しています" というエラーを表示します。

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>New-JournalRule タスクを使用して新しいジャーナルルールを作成するためのアクセス権を要求する

1. テスト環境のグローバル管理者アカウントを使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。

2. 管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [ **アクセスポリシーと要求の管理**] を選択します。

4. [ **新しい要求**] を選択します。 ドロップダウンフィールドで、組織に適切な値を選択します。

    **要求の種類**: タスク

    **要求スコープ**: 交換

    **要求**: 新しいジャーナルルール

    **期間 (時間)**: 2

    **コメント**: 新しいジャーナルルールを作成するためのアクセス許可を要求する

5. [ **保存**] を選択し、[ **閉じる**] を選択します。 要求は、電子メールを介して承認者のグループに送信されます。

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>新しいジャーナルルールの作成に関する特権アクセス要求を承認する

1. テスト環境のユーザー3の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします (テスト環境の "特権アクセス承認者" セキュリティグループのメンバー)。

2. 管理センターで、[**設定**  >  **セキュリティ & プライバシー**  >  **特権アクセス**] に移動します。

3. [ **アクセスポリシーと要求の管理**] を選択します。

4. 保留中の要求を選択し、[ **承認** ] を選択して、新しいジャーナルルールを作成するためのグローバル管理者アカウントへのアクセス権を付与します。 グローバル管理者アカウント (要求元のユーザー) は、承認が付与されたことを確認する電子メールを受信します。

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>New-JournalRule タスクに対する特権アクセスが承認された新しいジャーナルルールを作成するテスト

1. ローカルコンピューターで、 **Microsoft Corporation**  >  テスト環境のグローバル管理者アカウントを使用して、microsoft Corporation の exchange online リモート powershell モジュールにサインインし、microsoft**exchange online**リモート powershell モジュールにサインインします。

1. Exchange 管理 PowerShell で、組織の新しいジャーナルルールを作成します。

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Exchange 管理 PowerShell で新しいジャーナルルールが正常に作成されたことを表示します。

## <a name="next-step"></a>次のステップ

テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
