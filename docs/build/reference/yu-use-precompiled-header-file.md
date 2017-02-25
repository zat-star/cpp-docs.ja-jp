---
title: "/Yu (プリコンパイル済みヘッダー ファイルの使用) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch ファイル, 使用 (既存の)"
  - "/Yu コンパイラ オプション [C++]"
  - "PCH ファイル, 使用 (既存の)"
  - "プリコンパイル済みヘッダー ファイル, 使用 (既存の)"
  - "Yu コンパイラ オプション [C++]"
  - "-Yu コンパイラ オプション [C++]"
ms.assetid: 24f1bd0e-b624-4296-a17e-d4b53e374e1f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Yu (プリコンパイル済みヘッダー ファイルの使用)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在のコンパイルに既存のプリコンパイル済みヘッダー \(.pch\) を使用します。  
  
## 構文  
  
```  
/Yu[filename]  
```  
  
## Arguments  
 *filename*  
 ヘッダー ファイルの名前。このヘッダー ファイルは、**\#include** プリプロセッサ ディレクティブによってソース ファイルに取り込まれます。  
  
## 解説  
 インクルード ファイルの名前は、プリコンパイル済みヘッダーを作成する **\/Yc** オプションと、そのプリコンパイル済みヘッダーの使用を指示する以降の **\/Yu** オプションで同じにする必要があります。  
  
 **\/Yc** では、引数 `filename` はプリコンパイルの停止位置を指定します。つまり、名前が `filename` のファイルまでのすべてのコードがプリコンパイルされます。生成されるプリコンパイル済みヘッダーの名前には、インクルード ファイルの基本名と拡張子 .pch が付きます。  
  
 .pch ファイルは **\/Yc** を使用して作成されている必要があります。  
  
 ここで指定した .h ファイルまでのコードは、すべてプリコンパイル済みと見なされます。  したがって、その .h ファイルの **\#include** ディレクティブまでのコードはコンパイルされず、.pch ファイルのコードが代わりに使用されます。`filename` 以降のすべてのコードをコンパイルします。  
  
 コマンド ラインで、**\/Yu** と `filename` の間には空白を挿入しないでください。  
  
 **\/Yu** オプションでファイル名を指定しない場合は、ソース プログラムにプリコンパイル済みヘッダー \(.pch\) ファイル名を指定する [\#pragma hdrstop](../../preprocessor/hdrstop.md) が必要です。  この場合、コンパイラは [\/Fp \(.pch ファイルの名前の指定\)](../Topic/-Fp%20\(Name%20.Pch%20File\).md) で指定されたプリコンパイル済みヘッダー \(.pch\) ファイルを使用します。  コンパイラは、このプラグマの位置までスキップし、このプラグマで指定するプリコンパイル済みヘッダー ファイルからコンパイル状態を復元します。その後、このプラグマの後ろにあるコードだけをコンパイルします。  **\#pragma hdrstop** でファイル名を指定しないと、コンパイラはソース ファイルと同じ基本名で拡張子が .pch のファイルを探します。  また、**\/Fp** オプションを使用して、別の .pch ファイルを指定することもできます。  
  
 **\/Yu** オプションにファイル名を指定せず、**hdrstop** プラグマも指定していないと、エラー メッセージが出力されてコンパイルが失敗します。  
  
 **\/Yc** `filename` オプションと  **\/Yu**`filename` オプションが 1 つのコマンド ラインに指定され、その両方が同じファイル名を参照する場合は、**\/Yc**`filename` が優先され、引数で指定した名前のファイルまでのすべてのコードがプリコンパイルされます。  したがって、メイクファイルの作成が簡単になります。  
  
 .pch ファイルには、プログラムのメモリ アドレス情報に加えマシン環境に関する情報も含まれているため、pch ファイルはその作成先のマシンでのみ使用してください。  
  
 プリコンパイル済みヘッダーの詳細については、以下のトピックを参照してください。  
  
-   [\/Y \(プリコンパイル済みヘッダー\)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの .cpp ファイルに [\/Yc \(プリコンパイル済みヘッダー ファイルの作成\)](../../build/reference/yc-create-precompiled-header-file.md) を指定します。  
  
2.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
3.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
4.  **\[プリコンパイル済みヘッダー\]** プロパティ ページをクリックします。  
  
5.  **\[ファイルを使用して PCH を作成\/使用\]** プロパティまたは **\[プリコンパイル済みヘッダーの作成\/使用\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>」を参照してください。  
  
## 例  
 次のコードをコンパイルしてみます。  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 これはコマンド ライン `CL /YuMYAPP.H PROG.CPP` でコンパイルされます。上の 3 つの \#include ステートメントは処理されず、MYAPP.pch 内のプリコンパイル済みコードが使用されます。したがって、これらの 3 ファイルおよびこれ以外のインクルード ファイルのプリプロセス時間を節約できます。  
  
 .pch ファイルの名前が **\/Yc** の引数 filename またはソース ファイルの基本名と異なる場合は、次のように **\/Yu** オプションと [\/Fp \(.pch ファイルの名前の指定\)](../Topic/-Fp%20\(Name%20.Pch%20File\).md) オプションを併用するとファイル名を指定できます。  
  
```  
CL /YuMYAPP.H /FpMYPCH.pch PROG.CPP  
```  
  
 このコマンドでは、プリコンパイル済みヘッダー ファイルの名前として MYPCH.pch を指定しています。  コンパイラは、このファイルの内容を使って、MYAPP.h までのすべてのヘッダー ファイルのプリコンパイル状態を復元します。  その後、MYAPP.h を指定する **include** ステートメントの後ろのコードをコンパイルします。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)