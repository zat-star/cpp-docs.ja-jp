---
title: "/Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.CompileAs"
  - "VC.Project.VCCLCompilerTool.CompileAs"
  - "/Tp"
  - "/tc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Tc コンパイラ オプション [C++]"
  - "/Tp コンパイラ オプション [C++]"
  - "ソース ファイル, 指定 (コンパイラに)"
  - "Tc コンパイラ オプション [C++]"
  - "-Tc コンパイラ オプション [C++]"
  - "Tp コンパイラ オプション [C++]"
  - "-Tp コンパイラ オプション [C++]"
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Tc** オプションは、ファイルの拡張子が .c ではなくても、`filename` を C のソース ファイルとして指定します。  これに対し、**\/Tp** オプションは、ファイルの拡張子が .cpp または .cxx ではなくても、`filename` を C\+\+ のソース ファイルとして指定します。  両オプションとも、引数 `filename` との間にスペースを挿入してもかまいません。  この 2 つのオプションでは、一度に指定できるファイルは 1 つだけです。複数のファイルを指定する場合は、ファイルごとにオプションを繰り返します。  
  
 **\/TC** と **\/TP** は、それぞれ **\/Tc** と **\/Tp** のグローバル変数です。  \/TC オプションと \/TP オプションでは、コマンド ラインで指定されたすべてのファイルをそれぞれ C のソース ファイル \(**\/TC**\) または C\+\+ のソース ファイル \(**\/TP**\) として処理するようにコンパイラに指定します。これは、コマンド ラインでのファイル名とオプションの位置には関係ありません。  これらのグローバル オプションは、それぞれ **\/Tc** または **\/Tp** を使用して、単一ファイル上でオーバーライドできます。  
  
## 構文  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## Arguments  
 `filename`  
 C または C\+\+ のソース ファイル。  
  
## 解説  
 既定では、拡張子 .c のファイルは C のソース ファイルと見なされ、拡張子 .cpp または .cxx のファイルは C\+\+ のソース ファイルと見なされます。  
  
 **TC** または **Tc** オプションを指定すると、[\/Zc:wchar\_t \(wchar\_t をネイティブ型として認識\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) オプションの指定は無視されます。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  **\[コンパイル言語の選択\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>」を参照してください。  
  
## 例  
 次の CL コマンド ラインは、MAIN.c、TEST.prg、および COLLATE.prg を C のソース ファイルとして指定しています。  PRINT.prg は認識されません。  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 次の CL コマンド ラインは、TEST1.c、TEST2.cxx、TEST3.huh、および TEST4.o を C\+\+ ファイルとしてコンパイルし、TEST5.z を C ファイルとしてコンパイルすることを指定しています。  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)