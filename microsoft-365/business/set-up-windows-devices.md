---
title: Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップする
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Microsoft 365 Business Premium ユーザー用に Windows 10 Pro を実行している Windows デバイスをセットアップする方法について説明します。これにより、集中管理およびセキュリティ制御が可能になります。
ms.openlocfilehash: c95b9e51c7ec3c440509fe34084d2a030c7f2eec
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841261"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップする

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップするための前提条件

Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップする前に、すべての Windows デバイスで Windows 10 Pro、バージョン 1703 (作成者の更新プログラム) が実行されていることを確認してください。 Windows 10 Pro は windows 10 Business を展開するための前提条件です。これは、Windows 10 Pro を補完する一連のクラウドサービスとデバイス管理機能であり、Microsoft 365 Business Premium の集中管理およびセキュリティ制御を有効にします。
  
Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro を実行している Windows デバイスを使用している場合は、Microsoft 365 Business Premium サブスクリプションで Windows 10 のアップグレードができます。
  
Windows デバイスを Windows 10 Pro Creators Update にアップグレードする方法については、「[Windows デバイスを Windows Pro Creators Update にアップグレードする](upgrade-to-windows-pro-creators-update.md)」の手順に従います。
  
アップグレードが完了していることを確認するには、[ [デバイスが AZURE AD に接続されていること](#verify-the-device-is-connected-to-azure-ad) を確認する] を参照してください。

Microsoft 365 への Windows の接続に関する短いビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Windows 10 デバイスを組織の Azure AD に参加させる

組織内のすべての Windows デバイスを Windows 10 Pro クリエーターの更新プログラムにアップグレードするか、または Windows 10 Pro クリエーターの更新プログラムを既に実行している場合は、これらのデバイスを組織の Azure Active Directory に参加させることができます。 参加したデバイスは、Microsoft 365 Business Premium サブスクリプションの一部である Windows 10 Business に自動的にアップグレードされます。
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>新しい、または新たにアップグレードした Windows 10 Pro デバイスについて

Windows 10 Pro Creators Update が実行されている新しいデバイス、または Windows 10 Pro Creators Update にアップグレードしたが、Windows 10 デバイスのセットアップが完了していないデバイスについては、次の手順に従います。
  
1. [ **設定方法** ] ページが表示されるまで Windows 10 デバイスのセットアップを行います。 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. ここで、[ **組織用に設定** ] を選択し、Microsoft 365 Business Premium のユーザー名とパスワードを入力します。 
    
3. Windows 10 デバイスのセットアップを完了します。
    
   完了すると、組織の Azure AD に接続されます。「[デバイスが Azure AD に接続されていることを確認する](#verify-the-device-is-connected-to-azure-ad)」を参照して確認します。 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>既にセットアップして、Windows 10 Pro を実行しているデバイスの場合

 **ユーザーを Azure AD に接続する**
  
1. Windows 10 Pro バージョン 1703 (Creators Update) を実行しているユーザーの Windows PC で ([前提条件](pre-requisites-for-data-protection.md)を参照)、Windows ロゴ、[設定] アイコンの順にクリックします。
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. [ **設定** ] で [ **アカウント** ] に移動します。
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. On **Your info** page, click **Access work or school** \> **Connect** .
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. [ **職場または学校アカウントの設定** ] ダイアログの [ **別の操作** ] の下で、[ **このデバイスを Azure Active Directory に参加させる** ] を選びます。
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next** .
  
   On the **Enter password** page, enter your password \> **Sign in** .
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. [ **組織が組織** であることを確認してください] ページで、情報が正しいことを確認し、[ **参加** ] を選択します。
  
   [ **すべて完了しました。** ページ、[チョーク sse **完了** ]。
  
   ![[自分の組織になっていることを確認してください] 画面で、[参加] を選択します。](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
ファイルを OneDrive for Business にアップロードした場合、それらの同期を取り消します。 サードパーティ製のツールを使用してプロファイルとファイルを移行した場合は、それらを新しいプロファイルにも同期します。
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>デバイスが Azure AD に接続されていることを確認する

同期の状態を確認するには、[ **設定** ] の [ **職場または学校** へのアクセス] ページで、[ **接続先** ] _ \<organization name\> _ _ _ _ _ _ _ _ _ _」を選択し、ボタンの **情報** と **切断** を表示します。 [ **情報** ] を選択して同期の状態を取得します。 
  
[ **同期の状態** ] ページで、[ **同期** ] を選択して、PC に最新のモバイルデバイス管理ポリシーを取得します。
  
Microsoft 365 Business Premium アカウントの使用を開始するには、Windows の [ **スタート** ] ボタンに移動し、現在のアカウントの画像を右クリックして、 **アカウントを切り替え** ます。 自分の組織のメール アドレスとパスワードを使用してサインインします。
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>PC が Windows 10 Business にアップグレードされていることを確認する

Microsoft 365 Business Premium サブスクリプションの一部として、Azure AD に参加している Windows 10 デバイスが Windows 10 Business にアップグレードされていることを確認します。
  
1. Go to **Settings** \> **System** \> **About** .
    
2. [ **エディション** ] が **Windows 10 Business** であることを確認します。
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>次の手順

モバイルデバイスをセットアップするには、「 [microsoft 365 Business Premium ユーザーのモバイルデバイス](set-up-mobile-devices.md)をセットアップする」を参照してください。デバイス保護またはアプリ保護ポリシーを設定するには、「 [Manage microsoft 365 for business](manage.md)」を参照してください。
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の設定と使用の詳細については、「」を参照してください。

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
