---
title: "/FU (強制 #using ファイルの名前の指定) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.ForcedUsingFiles"
  - "/FU"
  - "VC.Project.VCNMakeTool.ForcedUsingAssemblies"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FU コンパイラ オプション [C++]"
  - "FU コンパイラ オプション [C++]"
  - "-FU コンパイラ オプション [C++]"
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FU (強制 #using ファイルの名前の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ソース・コードで [\#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md) にファイル名を渡すことの代わりとして使用できるコンパイラ オプション。  
  
## 構文  
  
```  
/FU file  
```  
  
## Arguments  
 `file`  
 このコンパイルで参照するメタデータ ファイルを指定します。  
  
## 解説  
 \/FU スイッチ取得、1 個のファイル名。  複数のファイルを指定するには、各オプションの \/FU を使用します。  
  
 [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] を使用して、[フレンド アセンブリ](../../dotnet/friend-assemblies-cpp.md) 機能を使用するメタデータを参照する **\/FU**を使用できません。  コードで `[as friend]` 属性と `#using`を使用してメタデータを—一緒に参照する必要があります。  フレンド アセンブリは [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) ではサポートされていません。  
  
 Common Language Runtime \(CLR\) のアセンブリまたはモジュールを作成する方法の詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]でビルドする方法の詳細については、「[アプリケーションとライブラリのビルド](../Topic/Building%20apps%20and%20libraries%20\(C++-CX\).md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  **\[\#using の強制\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>」を参照してください。  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)