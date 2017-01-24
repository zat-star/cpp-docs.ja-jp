---
title: "hdrstop | Microsoft Docs"
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
  - "hdrstop_CPP"
  - "vc-pragma.hdrstop"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "hdrstop プラグマ"
  - "プラグマ, hdrstop"
ms.assetid: 5ea8370a-10d1-4538-ade6-4c841185da0e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hdrstop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プリコンパイル ファイル名およびコンパイル状態が保存される場所に対する追加の制御を指定します。  
  
## 構文  
  
```  
  
#pragma hdrstop [( "filename" )]    
```  
  
## 解説  
 *filename* は、使用または作成する \([\/Yu](../build/reference/yu-use-precompiled-header-file.md) と [\/Yc](../build/reference/yc-create-precompiled-header-file.md) のどちらが指定されているかに基づく\) プリコンパイル済みヘッダー ファイルの名前です。  *filename* にパスの指定が含まれていない場合、プリコンパイル済みヘッダー ファイルはソース ファイルと同じディレクトリにあると想定されます。  
  
 \/Yc でコンパイルするときに C ファイルまたは C\+\+ ファイルに **hdrstop** プラグマが含まれている場合、コンパイラはプラグマの位置までのコンパイル状態を保存します。  プラグマの後ろにあるコードのコンパイル状態は保存されません。  
  
 コンパイル状態が保存されるプリコンパイル済みヘッダー ファイルに名前を付けるには、*filename* を使用します。  **hdrstop** と *filename* の間にスペースを挿入してもかまいません。  **hdrstop** プラグマで指定されるファイル名は文字列であるため、C または C\+\+ の文字列の制約を受けます。  具体的には、文字列を引用符で囲み、エスケープ文字 \(円記号\) を使用してディレクトリ名を指定する必要があります。  次に例を示します。  
  
```  
#pragma hdrstop( "c:\\projects\\include\\myinc.pch" )  
```  
  
 プリコンパイルされたヘッダー ファイルの名前は、次の規則 \(優先度順に表示\) に従って決定されます。  
  
1.  \/Fp コンパイラ オプションの引数  
  
2.  \#**pragma hdrstop** への *filename* 引数  
  
3.  拡張子 .PCH を持つソース ファイルのベース名  
  
 \/Yc オプションおよび \/Yu オプションの場合、この 2 つのコンパイル オプションまたは **hdrstop** プラグマでファイル名を指定しないと、ソース ファイルのベース名がプリコンパイル済みヘッダー ファイルのベース名として使用されます。  
  
 また、次のように、プリプロセス コマンドを使用してマクロ置換を実行することもできます。  
  
```  
#define INCLUDE_PATH "c:\\progra~`1\\devstsu~1\\vc\\include\\"  
#define PCH_FNAME "PROG.PCH"  
.  
.  
.  
#pragma hdrstop( INCLUDE_PATH PCH_FNAME )  
```  
  
 **hdrstop** プラグマを配置できる場所は、次の規則に従います。  
  
-   すべてのデータ宣言、関数宣言、および定義の外にある必要があります。  
  
-   ヘッダー ファイルにではなく、ソース ファイルに指定する必要があります。  
  
## 使用例  
  
```  
#include <windows.h>                 // Include several files  
#include "myhdr.h"  
  
__inline Disp( char *szToDisplay )   // Define an inline function  
{  
    ...                              // Some code to display string  
}  
#pragma hdrstop  
```  
  
 この例では、2 つのファイルがインクルードされ、インライン関数が定義された後に、**hdrstop** プラグマが記述されています。  初めは、プラグマの位置が不自然に見えるかもしれません。  ただし、手動プリコンパイル オプション \/Yc および \/Yu で **hdrstop** プラグマを使用すると、インライン コードであっても、ソース ファイル全体をプリコンパイルできることを考慮してください。  Microsoft コンパイラでは、データ宣言以外のプリコンパイルも実行できます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)