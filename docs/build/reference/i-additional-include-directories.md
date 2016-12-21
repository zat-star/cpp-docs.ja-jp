---
title: "/I (追加インクルード ディレクトリ) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories"
  - "/I"
  - "VC.Project.VCNMakeTool.IncludeSearchPath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/I コンパイラ オプション [C++]"
  - "追加インクルード ディレクトリのコンパイラ オプション"
  - "I コンパイラ オプション [C++]"
  - "-I コンパイラ オプション [C++]"
  - "インクルード ディレクトリ, コンパイラ オプション [C++]"
  - "設定 (include ディレクトリを)"
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /I (追加インクルード ディレクトリ)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インクルード ファイルを検索するディレクトリ一覧にディレクトリを追加します。  
  
## 構文  
  
```  
/I[ ]directory  
```  
  
## Arguments  
 `directory`  
 インクルード ファイルの検索対象ディレクトリ一覧に追加するディレクトリ。  
  
## 解説  
 複数のディレクトリを追加するには、このオプションを複数回使用します。  指定したインクルード ファイルが見つかるまでディレクトリが検索されます。  
  
 このオプションは、[\/X \(標準インクルード パスの無視\)](../../build/reference/x-ignore-standard-include-paths.md) \(標準インクルード パスの無視\) オプションと併用できます。  
  
 ディレクトリは、次の順で検索されます。  
  
1.  ソース ファイルが置かれているディレクトリ  
  
2.  **\/I** オプションで指定されたディレクトリ \(CL で出現する順序で検索\)  
  
3.  環境変数 **INCLUDE** で指定されているディレクトリ  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  \[全般\] プロパティ ページをクリックします。  
  
4.  **\[追加のインクルード ディレクトリ\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>」を参照してください。  
  
## 使用例  
 次のコマンドは、MAIN.c の要求するインクルード ファイルを検索します。検索順序は、MAIN.c が置かれているディレクトリ、\\INCLUDE ディレクトリ、\\MY\\INCLUDE ディレクトリ、環境変数 INCLUDE に代入されたディレクトリの順です。  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)