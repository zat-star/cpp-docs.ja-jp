---
title: "/FR、/Fr (.sbr ファイルの作成) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.BrowseInformation"
  - "VC.Project.VCCLCompilerTool.BrowseInformation"
  - "/fr"
  - "VC.Project.VCCLCompilerTool.BrowseInformationFile"
  - "VC.Project.VCCLWCECompilerTool.BrowseInformationFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FR コンパイラ オプション [C++]"
  - "FR コンパイラ オプション [C++]"
  - "-FR コンパイラ オプション [C++]"
  - "シンボリック ブラウザー情報"
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FR、/Fr (.sbr ファイルの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.sbr ファイルを作成します。  
  
## 構文  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## 解説  
 ビルド処理中、Microsoft Browse Information File Maintenance Utility \(BSCMAKE\) はこれらのファイルを使って BSC ファイルを作成します。このファイルは、ブラウザー情報を表示するために使います。  
  
 **\/FR** は、完全なシンボリック情報を含む .sbr ファイルを作成します。  
  
 **\/Fr** は、ローカル変数に関する情報を含まない .sbr ファイルを作成します。  
  
 `filename` を指定しない場合、.sbr ファイルはソース ファイルと同じベース名を取得します。  
  
 **\/Fr** は使用されなくなりました。代わりに **\/FR** を使用してください。 詳しくは、[カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md) の「使用されなくなった削除済みのコンパイラ オプション」をご覧ください。  
  
> [!NOTE]
>  .sbr 拡張子を変更しないでください。 BSCMAKE では、中間ファイルにその拡張子を含める必要があります。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  ナビゲーション ウィンドウで、**\[C\/C\+\+\]**、**\[ブラウザー情報\]** プロパティ ページを選択してください。  
  
3.  **\[ブラウザー情報ファイル\]** か **\[ブラウザー情報の有効化\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>」を参照してください。  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)   
 [パス名の指定](../Topic/Specifying%20the%20Pathname.md)