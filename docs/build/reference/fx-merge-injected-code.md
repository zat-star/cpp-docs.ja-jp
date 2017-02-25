---
title: "/Fx (挿入されたコードのマージ) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx コンパイラ オプション [C++]"
  - "-Fx コンパイラ オプション [C++]"
  - "挿入されたコード"
  - "マージ (挿入されたコードを)"
  - "/Fx コンパイラ オプション [C++]"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Fx (挿入されたコードのマージ)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

挿入されたコードをソースにマージして、各ソース ファイルのコピーを生成します。  
  
## 構文  
  
```  
/Fx  
```  
  
## 解説  
 **\/Fx** では、元のソース ファイルとマージされたソース ファイルを区別するため、ファイル名とファイル拡張子の間に .mrg 拡張子を追加します。 たとえば、属性付きのコードを含んだ MyCode.cpp という名前のファイルを **\/Fx** でビルドすると、次のコードを含んだ MyCode.mrg.cpp という名前のファイルが作成されます。  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 .mrg ファイルでは、属性により挿入されたコードは次のように区切られます。  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 [no\_injected\_text](../../windows/no-injected-text.md) 属性が .mrg ファイルに埋め込まれることにより、テキストを再挿入せずに .mrg ファイルのコンパイルができます。  
  
 .mrg ソース ファイルは、コンパイラによって挿入されたソース コードの表示を目的としていることに留意する必要があります。 .mrg ファイルは元のソース ファイルと完全に同じようにはコンパイルまたは実行されない場合があります。  
  
 .mrg ファイルでは、マクロは展開されません。  
  
 挿入されたコードを使用するヘッダー ファイルがプログラムに含まれている場合、**\/Fx** はそのヘッダー用の .mrg.h ファイルを生成します。**\/Fx** は、挿入されたコードを使用しないインクルード ファイルをマージしません。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。 詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[出力ファイル\]** プロパティ ページをクリックします。  
  
4.  **\[属性ソースの展開\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>」を参照してください。  
  
## 参照  
 [出力ファイル \(\/F\) オプション](../../build/reference/output-file-f-options.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)