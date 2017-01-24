---
title: "Visual Studio での C++ プロジェクトのビルド | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "ビルド [C++], 概要 (Visual Studio でのビルド)"
  - "プロジェクト [C++], ビルド"
  - "Visual C++ プロジェクト, ビルド"
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual Studio での C++ プロジェクトのビルド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 統合開発環境 \(IDE\) では、ソリューション全体または 1 つのプロジェクトのみをビルドする複数の方法があります。  また、ビルド設定を変更し、カスタム ビルド ステップを指定して、開発プロセスを効率的にすることもできます。  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] で開いており、**ソリューション エクスプローラー**で選択したソリューションをビルドするために、次の操作を行うことができます。  
  
-   メニュー バーの **\[ビルド\]**、**\[ソリューションのビルド\]** の順にクリックします。  
  
-   または、**ソリューション エクスプローラー**でソリューションのショートカット メニューを開き、**\[ソリューションのビルド\]** を選択します。  
  
-   または、F7 キーを押します。  \(これは、C\/C\+\+ 開発設定の既定のキーボード ショートカットです\)。  
  
-   または、[コマンド ウィンドウ](../Topic/Command%20Window.md) \(メニュー バーで **\[表示\]**、**\[その他のウィンドウ\]**、**\[コマンド ウィンドウ\]** の順に選択\) で、「`Build.BuildSolution`」と入力します。  
  
-   または、[&#91;クイック起動&#93;](../Topic/Quick%20Launch,%20Environment,%20Options%20Dialog%20Box.md) ボックスに、「`ビルド ソリューションのビルド`」と入力します。  
  
 **ソリューション エクスプローラー**で選択したプロジェクトをビルドするために、次の操作を行うことができます。  
  
-   メニュー バーの **\[ビルド\]**、**\[\<プロジェクト名\> のビルド\]** の順にクリックします。  
  
-   または、**ソリューション エクスプローラー**でプロジェクトのショートカット メニューを開き、**\[ビルド\]** を選択します。  
  
-   または、コマンド ウィンドウ \(メニュー バーで **\[表示\]**、**\[その他のウィンドウ\]**、**\[コマンド ウィンドウ\]** の順に選択\) で、「`Build.BuildOnlyProject`」と入力します。  
  
-   または、\[クイック起動\] ボックスに、「`ビルド プロジェクトのみビルド <プロジェクト名> のみ`」と入力します。  
  
 Visual Studio で Visual C\+\+ アプリケーションをビルドする場合、プロジェクトの \[プロパティ ページ\] ダイアログ ボックスでビルドの設定の多くを変更できます。  プロジェクトのプロパティの設定方法の詳細については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。  
  
 IDE を使用して C\+\+ プロジェクトを作成、ビルド、およびデバッグする方法の例については、「[チュートリアル: C\+\+ での Visual Studio IDE の調査](../Topic/Getting%20Started%20with%20C++%20in%20Visual%20Studio.md)」を参照してください。  IDE を使用して C\+\+\/CLR プロジェクトをビルドする方法の例については、「[チュートリアル: Visual Studio で CLR をターゲットにした C\+\+ プログラムのコンパイル](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)」を参照してください。  IDE を使用して Windows ランタイム アプリを作成する方法の例については、「[C\+\+ を使った初めての Windows ランタイム アプリの作成](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx)」を参照してください。  
  
 ビルド、ビルド設定の変更、およびカスタム ビルド ステップの指定を行う方法の詳細については、次の記事を参照してください。  
  
## このセクションの内容  
 [カスタム ビルド ステップとビルド イベントについて](../ide/understanding-custom-build-steps-and-build-events.md)  
 統合開発環境でビルド プロセスをカスタマイズする方法について説明します。  
  
 [ビルドのコマンドとプロパティのマクロ](../ide/common-macros-for-build-commands-and-properties.md)  
 文字列を入力できる場所で使用できるマクロを一覧表示します。  
  
 [外部プロジェクトのビルド](../ide/building-external-projects.md)  
 統合開発環境外の機能を使用するプロジェクトのビルドについて説明します。  
  
 [プロジェクト ファイル](../ide/project-files.md)  
 .vcxproj ファイルの XML データ構造を示します。  
  
## 関連項目  
 [VC\+\+ Directories, Projects, Options Dialog Box](http://msdn.microsoft.com/ja-jp/e027448b-c811-4c3d-8531-4325ad3f6e02)  
 ビルド時の実行可能ファイル、インクルード ファイル、ライブラリ ファイル、およびソース コード ファイルの検索パスの変更方法について説明します。  
  
 [Visual Studio でのアプリケーションのビルド](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Visual Studio でのビルドについて説明します。  
  
 [C\/C\+\+ プログラムのビルド](../build/building-c-cpp-programs.md)  
 コマンド ラインまたは Visual Studio の統合開発環境からプログラムをビルドする方法について説明するトピックへのリンクがあります。  
  
 [C\/C\+\+ ビルドのリファレンス](../Topic/C-C++%20Building%20Reference.md)  
 C\+\+ でのプログラムのビルド、コンパイラ オプションとリンカー オプション、およびその他のビルド ツールの概要へのリンクがあります。  
  
 [旧バージョンの Visual C\+\+ からのプロジェクトのアップグレード](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Visual C\+\+ 6.0 以降のプロジェクトから Visual C\+\+ .NET へのアップグレードに関する問題について説明するトピックへのリンクがあります。  
  
 [Porting and Upgrading Programs](http://msdn.microsoft.com/ja-jp/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)  
 アプリケーションの移植の詳細とメイクファイルについて説明します。  
  
## 参照  
 [Roadmap for Windows Store apps using C\+\+](http://msdn.microsoft.com/ja-jp/0b71e4a4-5d8a-4a20-b2ec-e40062675ec1)