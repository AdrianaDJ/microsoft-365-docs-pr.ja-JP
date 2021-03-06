---
title: S/MIME 設定の構成-web 上の Outlook の Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な Exchange Online 管理者の簡単な説明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fe561c3a66cf2e7bdb76aabe10ffc875d85f2d77
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203337"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、Outlook on the web (旧称 Outlook Web App) をセットアップできます。 Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig** コマンドレットおよび **Set-smimeconfig** コマンドレットを使用します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

構文およびパラメーターの詳細については、「 [Get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) 」および「 [Set-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)」を参照してください。

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新しい Microsoft Edge (Chromium ベース) に関する考慮事項

新しい [microsoft](https://www.microsoft.com/windows/microsoft-edge) edge web ブラウザーで Outlook on the Web で S/mime を使用するには、新しい microsoft Edge に microsoft S/mime 拡張機能をインストールするために、ユーザー (または別の管理者) が、 **Extensioninstallforcelist** という microsoft edge browser ポリシーを設定して構成しなければなりません。 ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` です。 このポリシーを適用するには、ドメインに参加しているか Azure AD に参加しているデバイスが必要であるため、新しい Microsoft Edge ブラウザーで S/MIME を使用すると、ドメインに参加しているまたは Azure AD に参加しているデバイスが効果的に必要になります。

**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)」を参照してください。

この手順は、新しい Microsoft Edge を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。 S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。 または、ユーザーが Outlook on the web 設定で **S/MIME** を事前に参照して、コントロールのダウンロードリンクを取得することができます。

## <a name="considerations-for-chrome"></a>Chrome の考慮事項

Google Chrome web ブラウザーで Outlook on the web で S/MIME を使用するには、ユーザー (または別の管理者) が **Extensioninstallforcelist** という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。 ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` です。 このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、Chrome で S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。

**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)」を参照してください。

この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。 S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。 または、ユーザーが Outlook on the web 設定で **S/MIME** を事前に参照して、コントロールのダウンロードリンクを取得することができます。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
