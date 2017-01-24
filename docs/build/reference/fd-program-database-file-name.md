---
title: "/Fd (プログラム データベース ファイル名) | Microsoft Docs"
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
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName"
  - "VC.Project.VCCLCompilerTool.ProgramDataBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb ファイル, 作成"
  - "/FD コンパイラ オプション [C++]"
  - "FD コンパイラ オプション [C++]"
  - "-FD コンパイラ オプション [C++]"
  - "PDB ファイル, 作成"
  - "プログラム データベース コンパイラ オプション [C++]"
  - "プログラム データベース ファイル名 [C++]"
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fd (プログラム データベース ファイル名)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Z7、\/Zi、\/ZI \(デバッグ情報の形式\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) で生成されたプログラム データベース \(PDB\) ファイルの名前を指定します。  
  
## 構文  
  
```  
/Fdpathname  
```  
  
## 解説  
 **\/Fd** を指定しないと、既定の PDB ファイル名 VC`x`0.pdb が使用されます。`x` は現在使用している Visual C\+\+ のメジャー バージョンです。  
  
 円記号でファイル名 \(パスの末尾に含まれない\) でパスを指定した場合、コンパイラは、指定したディレクトリに含まれている`x`0.pdb VC .pdb ファイルを作成します。  
  
 ファイル名の拡張子を指定しない場合は、拡張子 .pdb が付加されます。  
  
 このオプションでは、簡易リビルドとインクリメンタル コンパイルに使用されるステート \(.idb\) ファイルの名前も指定します。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[出力ファイル\]** プロパティ ページをクリックします。  
  
4.  **\[プログラム データベース ファイルの名前\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、PROG.pdb という名前の .pdb ファイルと、PROG.idb という名前の .idb ファイルを作成します。  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)