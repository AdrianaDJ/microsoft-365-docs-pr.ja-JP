---
title: Sail オーバーする可能性があるセキュリティ上の課題-1 つのアーキテクトの視点
description: 説明
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: eb8019efb13a13b27a67d541ae69ca6f30b35ed0
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "44160053"
---
# <a name="security-hurdles-you-can-sail-over--one-architects-viewpoint"></a>Sail オーバーする可能性があるセキュリティ上の課題-1 つのアーキテクトの視点

この記事では、Microsoft の Cybersecurity アーキテクト[Garrett](https://www.linkedin.com/in/kozeta-garrett-53013a6/)について説明し、企業組織で発生する主なセキュリティ上の課題とこれらの問題を sailing するためのアプローチを推奨します。 

## <a name="about-the-author"></a>筆者について

![Garrett の写真](../media/solutions-architecture-center/kozeta-garrett-security.jpg) 

クラウドセキュリティアーキテクトとしての私の役割では、複数の組織と協力して、Microsoft 365 と Azure に移行しているお客様にセキュリティアーキテクチャを設計および実装するための戦略的および技術的なガイダンスを提供し、エンタープライズセキュリティソリューションを開発し、ビジネスの復元のためにセキュリティアーキテクチャと文化を促進しています。 筆者の専門知識には、インシデントの検出と応答、マルウェアの分析、ペネトレーションテスト、および IT のセキュリティと防御に対する改善の推奨が含まれています。 高度な変換によって、企業のためのイネーブラーとしてセキュリティが実現されています。

最近の数年間にわたってセキュリティによる近代化のマインドセットを採用した組織が優位な立場にあることを理解しています。これは、最新の COVID-19 状況にかかわらず、安全な方法でリモートでの運用を継続できるようにするためです。 残念ながら、このような状況は、この当面のニーズに対応していないお客様のために、一部のお客様に対して、ウェイクアップ呼び出しとしても提供されています。 多くの組織では、急速に改革する必要があることを実感しています。そのため、蓄積された IT セキュリティの借入金を廃止し、セキュリティに関する姿勢を大幅に向上させることができます。

Microsoft では、組織がセキュリティ上の姿勢をすぐに向上させるための優れたリソースを合わせしています。 これらのリソースに加えて、このような問題に対処するためのお客様が日常的に遭遇した sail の重要な課題を共有したいと考えています。

現在、北バージニア州に居住しており、自国の国の首都である、ワシントン DC に接近しています。 「実行中」、「自転車」、「ハイキング」、「お元気」など、すべてのアウトドア活動と練習の形式については、ほぼ好きです。 このことを対抗するために、料理、gourmet 食品、トラベルとしてお楽しみください。 


## <a name="partner-with-the-security-team-from-the-start-of-cloud-adoption"></a>クラウド導入の開始からセキュリティチームを持つパートナー

最初に、組織内のチームが開始から調整できる重要な点について、十分に説明できません。 セキュリティチームは、クラウド導入と設計の初期段階で、重要なパートナーとして採用する必要があります。 そのため、セキュリティチームは、ビジネスに追加された機能 (セキュリティで保護されたモバイルデバイスからの充実したユーザー環境、完全な機能を備えたアプリケーション、または制限付き機能の電子メールと生産性アプリケーションからの企業データに関する価値の作成など) だけでなく、新しいセキュリティの問題を解決するのに役立つストレージ、AI、コンピューティング セキュリティチームは、ユーザー (カルチャ)、プロセス (トレーニング)、テクノロジを成功させるために、この移行のすべての側面の管理に含める必要があります。 また、セキュリティ運用センター (SOC) の近代化と継続的な改善に投資することも意味します。 連携して、ビジネス戦略と環境の傾向に沿ったセキュリティ戦略を調整し、デジタル変換が安全に実行されるようにします。 これが正常に実行されると、組織は、ビジネス、IT、セキュリティに対する変更を含め、変更にすばやく適応する機能を開発します。 

障害が発生したお客様が最も多いのは、運用チームと SOC チームの間に実際のパートナーシップがない場合です。 運用チームは pressured され、クラウドを採用する厳しい期限が義務付けられていますが、セキュリティチームは常に、包括的なセキュリティ戦略を改訂および計画するためのプロセスの初期段階に含まれているわけではありません。 これには、さまざまなクラウドコンポーネントとオンプレミスのコンポーネントの統合が含まれます。 このようなパートナーシップの欠如は、さまざまなチームに対して、特定のコンポーネントの制御を実装するためにサイロで作業するようになっていると考えられます。これにより、実装、トラブルシューティング、および統合がさらに複雑になります。

これらの問題を sail しているお客様は、運用とガバナンス、およびセキュリティおよびリスク管理チームとの間で、ハイブリッドクラウドワークロードを保護するためのセキュリティ戦略と要件を revamp しています。 Cybersecurity ガバナンス、リスク、およびコンプライアンスの要件に基づいて、最終的なセキュリティの目標と結果に焦点を当てることができます。データの保護、システム、およびサービスの可用性。 これらの組織は、運用およびガバナンスチームと SOC の間に、セキュリティ設計手法に不可欠であり、投資の価値を最大化するために必要な初期段階のパートナーシップを開発しています。 

## <a name="build-a-modern-identity-based-security-perimeter"></a>モダンな (id ベースの) セキュリティ境界を構築する

次に、ゼロ信頼アーキテクチャアプローチを採用します。 これは、id ベースのモダンセキュリティ境界を作成することから始まります。 オンプレミスまたはクラウドのすべてのアクセス試行が信頼されているかどうかを確認するセキュリティアーキテクチャを設計します。「信頼しない」、「常に確認」というようにします。 この設計方法によって、セキュリティと生産性が向上するだけでなく、ユーザーが任意のデバイスタイプを使用してどこからでも作業できるようになります。 Microsoft 365 に含まれる洗練されたクラウドコントロールは、ユーザーの id を保護し、ユーザーのリスクレベルに基づいて貴重なリソースへのアクセスを制御するのに役立ちます。

推奨される構成については、「 [id とデバイスのアクセス構成](../enterprise/microsoft-365-policies-configurations.md)」を参照してください。 

## <a name="transition-security-controls-to-the-cloud"></a>セキュリティ制御をクラウドに移行する

多くのセキュリティチームは、「ネットワーク境界のセキュリティ」を維持し、オンプレミスのセキュリティツールと制御をクラウドソリューションに "強制" しようとするなど、すべてのオンプレミスの世界に構築された従来のセキュリティのベストプラクティスを引き続き使用しています。 このようなコントロールは、クラウド向けに設計されておらず、効果もありません。また、モダンクラウド機能の導入が妨げられています。 ネットワーク境界のセキュリティ手法に対して動作するプロセスとツールは、非効率かつ obstructive にクラウド機能を提供することが実証されておらず、モダンかつ自動化されたセキュリティ機能を利用することはできません。

防衛戦略をクラウド管理による保護、自動化された調査と修復、自動ペンテスト、高度な脅威保護、インシデント分析に移行することによって、この hurdle を sail することができます。 モダンデバイス管理ソリューションを使用しているお客様は、すべてのデバイス (スマートフォン、パーソナルコンピューター、ラップトップ、タブレット) に対して、自動管理、標準化されたパッチ、ウイルス対策、ポリシーの適用、およびアプリケーション保護を実装しています。 これにより、VPN、Microsoft System Center Configuration Manager (SCCM)、および Active Directory グループポリシーを使用する必要がなくなります。 これは条件付きアクセスポリシーと組み合わせて使用することにより、強力なコントロールと可視性を提供し、ユーザーが操作している場所に関係なく、リソースへのアクセスを効率化します。

## <a name="strive-for-best-together-security-tools"></a>「ベストに一体な」セキュリティツールを追求する

「お客様の stumble がよく見られる hurdle」では、セキュリティツールに対して「最高の組み合わせ」アプローチを採用しています。 最新のセキュリティニーズに対応するために「最高の選り抜き」ポイントソリューションを継続的に階層化することにより、企業のセキュリティが細分化されます。 最善の目的であっても、ほとんどの環境のツールは高コストで複雑になるため、統合されません。 これにより、チームが処理できるよりも優先度の高いアラートがあるので、可視性にギャップが生じます。 新しいツールで SecOps チームの再トレーニングも、一定の課題になります。

「Simple is 良好な」アプローチはセキュリティにも適しています。 ' Best of best ' ツールの後ではなく、既定で共に動作するツールを使用して ' best hurdle ' 戦略を採用することにより、このに sail を加えます。 Microsoft のセキュリティ機能は、アプリケーション、ユーザー、およびクラウドにわたる統合された脅威保護を使用して、組織全体を保護します。 統合によって、組織の復元性が向上し、修復攻撃に対する攻撃者を含むリスクが軽減されます。

## <a name="balance-security-with-functionality"></a>機能を使用したセキュリティのバランス

Cybersecurity のバックグラウンドと経験が長いため、すぐに使用できる構成から始めて、運用およびセキュリティのニーズに基づいてセキュリティ構成を緩和することをお勧めします。 ただし、このことは、hefty の失われた機能と低品質のユーザー環境で発生する可能性があります。 多くの組織では、ユーザーにとってセキュリティが非常に困難な場合、管理されていないクラウドサービスを使用するなど、ユーザーを回避する方法を見つけることができます。 私が承諾するのと同じように、「デリケート」の機能を実現する必要があることを認識しています。

ユーザーが自分の仕事を遂行するために必要なことを実現する組織では、"シャドウ IT の戦い" が対処されているとは言えないことを認識します。 It スタッフは、it 担当者が、作業に関して、it および承認されていない SaaS アプリケーションの使用に関して最も大きな offenders であることを認識しています。 その戦略を移行して、(抑制するのではなく) 使用を促し、作成できるリスクの露呈を軽減することに重点を置いています。 これらの組織のセキュリティチームは、すべてがリバースプロキシまたは VPN を経由して、ブロック、ログ、送信されることを主張しません。 その代わりに、これらのセキュリティチームは、重要な機密データを誤った関係者や悪意のあるアプリに公開しないようにするための努力を二重にしています。 これらは、データの整合性を保護するために機能します。 また、暗号化、セキュリティで保護された多要素認証、自動のリスクとコンプライアンス、Cloud App Security Broker (CASB) の機能を最大限に活用し、複数のプラットフォーム間で保護された共有を促進することもできます。 IT 部門は、IT を inspiring の創造性、生産性、コラボレーションに統合することができます。これにより、企業は競争力を維持することができます。


## <a name="adopt-a-methodical-approach"></a>系統的な方法を採用する 

クラウドセキュリティをさまざまな組織で実装することについて経験した課題のほとんどは、業界に関係なく、非常に類似しています。 最初に、特定の機能についての多くのドキュメントがありますが、組織レベルで適用されるもの、セキュリティ機能の重複、および機能の統合方法について、混乱が生じます。 また、このボックスから事前に構成されており、組織による構成を必要とするセキュリティ機能についても不確実なレベルがあります。 さらに、SOC チームには、急速なクラウド導入およびデジタル変換の準備に必要な完全露出、トレーニング、または予算割り当てがありませんでした。

これらの問題を明確にするために、Microsoft では、セキュリティ戦略と実装に対して系統的なアプローチを実現するために設計されたいくつかのリソースを合わせしています。 


|Resource   |詳細情報  |
|---------|---------|
|[自宅での作業をサポートするためのセキュリティチームの主なタスク](../security/top-security-tasks-for-remote-work.md)      | 在宅勤務中の労働者を突然サポートしている場合は、この記事を参考にして、セキュリティを迅速に向上させることができます。 ライセンスプランに基づく上位の推奨タスクが含まれています。    |
|[Microsoft 365 のビジネス上の意思決定者向けのセキュリティ](../security/Microsoft-365-security-for-bdm.md)    | より包括的な計画のための時間がある場合、この記事には、Microsoft 365 にまたがる推奨事項と、攻撃の範囲による優先順位が設定されています。 また、ライセンスとエリア (id、脅威の保護、監視など) での並べ替えに使用できるスプレッドシートも付属しています。  |
|[Microsoft セキュリティアーキテクチャの推奨事項](https://docs.microsoft.com/security/compass/compass)    | セキュリティアーキテクトの場合は、id、ネットワーク、セキュリティの操作を含む、専門分野別に編成されたセキュリティ推奨事項を確認してください。   |
|[マイクロソフトのセキュリティ運用に関する推奨事項](https://docs.microsoft.com/security/compass/security-operations-videos-and-decks)|セキュリティ操作センター (SOC) をセットアップして実行するための Microsoft の推奨事項について説明します。 |
|[チーフ情報セキュリティ責任者 (CISO) ワークショップのトレーニング](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop)   | クラウドセキュリティを初めて使用する場合は、この一連のビデオをお見逃しないでください。        |
|[docs.security.com/security](https://docs.microsoft.com/security/)    | セキュリティ戦略およびアーキテクチャを対象とした Microsoft 全体からの技術ガイダンス。        |
| | |

これらのリソースはすべて、出発点として使用し、組織のニーズに適合するように設計されています。 
