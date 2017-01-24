---
title: "/Yc (プリコンパイル済みヘッダー ファイルの作成) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.UsePrecompiledHeader"
  - "/yc"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough"
  - "VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader"
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch ファイル, 作成"
  - "/Yc コンパイラ オプション [C++]"
  - "PCH ファイル, 作成"
  - "プリコンパイル済みヘッダー ファイル, 作成"
  - "Yc コンパイラ オプション [C++]"
  - "-Yc コンパイラ オプション [C++]"
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yc (プリコンパイル済みヘッダー ファイルの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ある時点でのコンパイルの状態を表すプリコンパイル済みヘッダー \(.pch\) ファイルを作成します。  
  
## 構文  
  
```  
/Yc[filename]  
```  
  
## Arguments  
 `filename`  
 ヘッダー \(.h\) ファイルを指定します。  この引数を使用すると、コンパイラは .h ファイルまでのすべてのコードをコンパイルします。  
  
## 解説  
 引数を使わずに **\/Yc** を指定すると、コンパイラはベース ソース ファイルの最後まで、またはベース ファイルで [hdrstop](../../preprocessor/hdrstop.md) が現れる位置までのすべてのコードをコンパイルします。  生成される .pch ファイルでは、**hdrstop** プラグマまたは **\/Fp** オプションを使って別のファイル名を指定しない限り、ベース ソース ファイルと同じ基本名が使用されます。  
  
 プリコンパイル済みコードは、**\/Yc** オプションで指定されたファイルの基本名に拡張子 .pch が付いた名前のファイルに保存されます。  [\/Fp \(.pch ファイルの名前の指定\)](../Topic/-Fp%20\(Name%20.Pch%20File\).md) オプションを使用して、プリコンパイル済みヘッダー ファイルの名前を指定することもできます。  
  
 \/**\/Yc**`filename` を指定すると、後で **\/Yu** オプションで使用できるように、指定されたファイルまでのすべてのコードがコンパイルされます。  
  
 **\/Yc** `filename` オプションと [\/Yu \(プリコンパイル済みヘッダー ファイルの使用\)](../../build/reference/yu-use-precompiled-header-file.md)`filename` オプションが 1 つのコマンド ラインに指定され、その両方が同じファイル名を参照または暗黙に指定する場合は、**\/Yc**`filename` が優先されます。  したがって、メイクファイルの作成が簡単になります。  
  
 プリコンパイル済みヘッダーの詳細については、以下のトピックを参照してください。  
  
-   [\/Y \(プリコンパイル済みヘッダー\)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  .cpp ファイルを選択します。  .cpp ファイルは、プリコンパイル済みヘッダー情報を含む .h ファイルを \#include する必要があります。  プロジェクトの **\/Yc** 設定はファイル レベルでオーバーライドできます。  
  
2.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
3.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
4.  **\[プリコンパイル済みヘッダー\]** プロパティ ページをクリックします。  
  
5.  **\[ファイルを使用して PCH を作成\/使用\]** プロパティまたは **\[プリコンパイル済みヘッダーの作成\/使用\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>」を参照してください。  
  
## 使用例  
 次のコードがあるとします。  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 コマンド `CL /YcMYAPP.H PROG.CPP` を使用してこのコードをコンパイルすると、AFXWIN.h、RESOURCE.h、および MYAPP.h までのコンパイル結果がプリコンパイル済みヘッダー ファイル MYAPP.pch に保存されます。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)