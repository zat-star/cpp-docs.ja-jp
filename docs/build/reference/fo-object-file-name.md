---
title: "/Fo (オブジェクト ファイルの名前の指定) | Microsoft Docs"
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
  - "/Fo"
  - "VC.Project.VCCLCompilerTool.ObjectFile"
  - "VC.Project.VCCLWCECompilerTool.ObjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fo コンパイラ オプション [C++]"
  - "Fo コンパイラ オプション [C++]"
  - "-Fo コンパイラ オプション [C++]"
  - "オブジェクト ファイル, 名前付け"
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fo (オブジェクト ファイルの名前の指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

既定のファイル名の代わりに使用するオブジェクト \(.obj\) ファイル名またはディレクトリを指定します。  
  
## 構文  
  
```  
/Fopathname  
```  
  
## 解説  
 このオプションを使用しない場合は、ソース ファイルの基本名と拡張子 .obj がオブジェクト ファイル名として使用されます。  任意の名前と拡張子を使用できますが、通常は .obj を使用することをお勧めします。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[出力ファイル\]** プロパティ ページをクリックします。  
  
4.  **\[オブジェクト ファイル名\]** プロパティを変更します。開発環境では、オブジェクト ファイルの拡張子を .obj にする必要があります。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>」を参照してください。  
  
## 使用例  
 次のコマンド ラインは、ドライブ B にある既存の \\OBJECT ディレクトリに、THIS.obj という名前のオブジェクト ファイルを作成します。  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)