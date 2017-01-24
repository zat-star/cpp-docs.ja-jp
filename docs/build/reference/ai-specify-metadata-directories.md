---
title: "/AI (メタデータ ディレクトリの指定) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.AdditionalUsingDirectories"
  - "VC.Project.VCNMakeTool.AssemblySearchPath"
  - "/AI"
  - "VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/AI コンパイラ オプション [C++]"
  - "AI コンパイラ オプション [C++]"
  - "-AI コンパイラ オプション [C++]"
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /AI (メタデータ ディレクトリの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`#using` ディレクティブに渡されたファイル参照を解決するために、コンパイラによって検索されるディレクトリを指定します。  
  
## 構文  
  
```  
/AIdirectory  
```  
  
## 引数  
 `directory`  
 コンパイラが検索するディレクトリまたはパス。  
  
## 解説  
 **\/AI** 呼び出しに渡すことができるディレクトリは 1 つだけです。  コンパイラで検索するパスごとに **\/AI** オプションを 1 つずつ指定します。  たとえば、`#using` ディレクティブのコンパイラ検索パスに C:\\Project\\Meta と C:\\Common\\Meta の両方を追加するには、`/AI"C:\Project\Meta" /AI"C:\Common\Meta"` をコンパイラ コマンド ラインに追加するか、Visual Studio の **\[追加の \#using ディレクトリ\]** プロパティに各ディレクトリを追加します。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  ナビゲーション ペインで、**\[構成プロパティ\]**、**\[C\/C\+\+\]**、**\[全般\]** の順に選択します。  
  
3.  **\[追加の \#using ディレクトリ\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [\#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)