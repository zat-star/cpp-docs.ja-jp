---
title: "チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Visual C++ の配置"
ms.assetid: 66735cda-8fe3-4211-a19a-2cf717a12a3f
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: セットアップ プロジェクトを使用した Visual C++ アプリケーションの配置
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

セットアップ プロジェクトを使用して Visual C\+\+ アプリケーションを配置する方法について説明します。  
  
## 必須コンポーネント  
 このチュートリアルを実行するには、次のコンポーネントが必要です。  
  
-   [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] がインストールされているコンピューター  
  
-   Visual C\+\+ ライブラリがない別のコンピューター  
  
### セットアップ プロジェクトを使用してアプリケーションを配置するには  
  
1.  新しい Visual Studio ソリューションを作成するため、**MFC アプリケーション ウィザード**を使用します。  このウィザードを実行するには、**\[新しいプロジェクト\]** ダイアログ ボックスの **\[Visual C\+\+\]** ノードを展開し、**\[MFC\]** を選択します。**\[MFC アプリケーション\]** をクリックし、プロジェクトの名前を入力して、**\[OK\]** をクリックします。  
  
2.  アクティブなソリューション構成を **\[解放\]** に変更します。  **\[ビルド\]** メニューの **\[構成マネージャー\]** をクリックします。  **\[構成マネージャー\]** ダイアログ ボックスで、**\[アクティブ ソリューション構成\]** ボックスの **\[解放\]** をクリックします。  
  
3.  F7 キーを押してアプリケーションをビルドします。  または、**\[ビルド\]** メニューの **\[ソリューションのビルド\]** をクリックします。  これは、この MFC アプリケーション プロジェクトの出力を使用するセットアップ プロジェクトを有効にします。  
  
4.  いない場合は、Visual Studio 開発者向けに、可用性、セットアップと配置の Visual Studio プロジェクト テンプレートの機能を置き換えるダウンロードの InstallShield Limited Edition \(ISLE\)。  インターネットに接続すると、**\[ファイル\]**、**\[新規作成\]**、メニュー バーの **\[プロジェクト\]**、または **\[ソリューション エクスプローラー\]** でソリューションを右クリックし、**\[追加\]** を選択すると、**\[新しいプロジェクト\]** のダイアログ ボックスをオンにすると、**\[新しいプロジェクト…\]** 開きます。  **\[その他のプロジェクトの種類\]** のノードを展開し、**\[セットアップと配置\]** のノードの **\[InstallShield Limited Edition の有効化\]** を選択し、表示される指示に従います。  InstallShield Limited Edition ダウンロードし、インストール、およびアクティブ化された、Visual Studio を終了し、再起動します。  
  
5.  **\[新しいプロジェクト\]** のダイアログ ボックスを再度開き、**\[その他のプロジェクトの種類\]** のノードを展開し、を **\[InstallShield Limited Edition\]** のノードの **\[InstallShield Limited Edition Project\]** を選択します。  
  
6.  は、Visual Studio の MFC プロジェクトへ出力参照を追加するには、InstallShield Limited Edition テンプレートで作成されたセットアップ プロジェクトの **\[作業の開始\]** のノードの指示に従います。  
  
7.  インストーラー ファイル \(setup.exe\) を作成するセットアップ プロジェクトをビルドします。  にそのためには、**\[ソリューション エクスプローラー\]** のセットアップ プロジェクト ノードを右クリックし、**\[ビルド\]** を選択します。  
  
     InstallShield Limited Edition は、セットアップ プロジェクト ツリーのセットアップ ファイルを作成します \(既定では、セットアップ プロジェクトの Express\\SingleImage\\DiskImages\\DISK1 サブフォルダーにあります\)。  
  
8.  Visual C\+\+ ライブラリがないもう 2 台のコンピューターでセットアップ プログラムを実行します。  
  
## 参照  
 [配置例](../ide/deployment-examples.md)