---
title: "Visual C++ アプリケーションの依存関係の理解 | Microsoft Docs"
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
  - "アプリケーションの配置 [C++], 依存関係"
  - "依存関係 [C++], アプリケーションの配置"
  - "Dependency Walker"
  - "depends.exe"
  - "配置 (アプリケーションを) [C++], 依存関係"
  - "DLL [C++], 依存関係"
  - "DUMPBIN ユーティリティ"
  - "ライブラリ [C++], アプリケーションの配置の問題"
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ アプリケーションの依存関係の理解
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションがどの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリに依存しているかを確認するには、プロジェクトのプロパティを表示します   \(ソリューション エクスプローラーでプロジェクトを右クリックし、**\[プロパティ\]** を選択して、**\[プロパティ ページ\]** ダイアログ ボックスを開きます\)。 また、Dependency Walker \(depends.exe\) を使用して、全体的な依存関係をより包括的に把握することもできます。  
  
 **\[プロパティ ページ\]** ダイアログ ボックスで、**\[構成プロパティ\]** にあるさまざまなページを確認して、依存関係を把握できます。  たとえば、プロジェクトで MFC ライブラリが使用されている場合、**\[MFC の使用\]**、**\[構成プロパティ\]** の **\[共有 DLL で MFC を使う\]**、**\[全般\]** ページの順に選択すると、実行時のアプリケーションが mfc\<version\>.dll などの MFC DLL に依存していることがわかります。  アプリケーションで MFC を使用していない場合は、**\[構成プロパティ\]** の **\[マルチスレッド デバッグ DLL \(\/MDd\)\]** または **\[マルチスレッド DLL \(\/MD\)\]** の **\[ランタイム ライブラリ\]**、**\[C\/C\+\+\]**、**\[コード生成\]** ページの順に選択すると、そのアプリケーションは CRT ライブラリに依存している可能性があります。  
  
 アプリケーションが依存する DLL を確認する包括的な方法は、Dependency Walker \(depends.exe\) を使用してアプリケーションを開くことです。  [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) Web サイトからツールをダウンロードすることができます。  
  
 depends.exe を使用すると、読み込み時にアプリケーションにリンクされた DLL の一覧と、遅延読み込みされた DLL の一覧を確認できます。  実行時に動的に読み込まれた DLL の完全な一覧を取得する必要がある場合は、depends.exe のプロファイル機能を使用して、すべてのコード パスが確実に実行されるまでアプリケーションをテストします。  プロファイル セッションを終了すると、実行時に動的に読み込まれた DLL が表示されます。  
  
 depends.exe を使用する場合は、DLL が、他の DLL や特定の DLL バージョンに依存している場合があることに注意してください。  depends.exe は、開発用コンピューターとターゲット コンピューターのどちらでも使用できます。  開発用コンピューターでは、アプリケーションのサポートに必要な DLL を報告します。  ターゲット コンピューターでアプリケーションを実行できない場合は、必要な DLL が見つからないのか、不適切なのかを判断できるように、depends.exe をターゲット コンピューターにコピーして、ツールでアプリケーションを開きます。  
  
 アプリケーションが依存する DLL がわかったら、アプリケーションを別のコンピューターに配置するときに共に再頒布する必要がある DLL を判断できます。  ほとんどの場合、システム DLL を再頒布する必要はありませんが、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ライブラリの DLL の再頒布が必要である可能性があります。  詳細については、「[再配布する DLL の決定](../ide/determining-which-dlls-to-redistribute.md)」を参照してください。  
  
## 参照  
 [デスクトップ アプリケーションの配置](../Topic/Deploying%20Native%20Desktop%20Applications%20\(Visual%20C++\).md)