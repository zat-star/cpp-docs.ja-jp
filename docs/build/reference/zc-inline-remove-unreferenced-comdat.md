---
title: "/Zc:inline (参照されない COMDAT の除去) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Zc:inline"
  - "VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc コンパイラ オプション (C++)"
  - "/Zc:inline"
  - "Zc コンパイラ オプション (C++)"
  - "-Zc コンパイラ オプション (C++)"
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /Zc:inline (参照されない COMDAT の除去)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COMDAT であるか内部リンケージのみを持つ、参照されていない関数またはデータを削除します。  **\/Zc:inline** を指定すると、インライン データまたはインライン関数を使用する翻訳単位には、そのデータまたは関数の定義も含まれている必要があるということがコンパイラによって要求されます。  
  
## 構文  
  
```  
/Zc:inline[-]  
```  
  
## 解説  
 **\/Zc:inline** を指定すると、参照されていない COMDAT 関数またはデータ、または内部リンケージのみを持つ関数またはデータのシンボル情報は、コンパイラによって出力されません。  既定では、このオプションはオフ \(**\/Zc:inline\-**\) です。  この最適化によって、リリース ビルドにおいて、またはリンカー オプション [\/OPT:REF](../../build/reference/opt-optimizations.md) を指定したときに、リンカーによって実行される作業の一部が簡素化されます。  コンパイラによってこの最適化が実行されると、.obj ファイルのサイズを大幅に縮小し、リンカーの速度を向上させることができます。  このコンパイラ オプションは、最適化が無効な場合 \([\/Od](../../build/reference/od-disable-debug.md)\) または [\/GL \(プログラム全体の最適化\)](../../build/reference/gl-whole-program-optimization.md) が指定されている場合は有効になりません。  
  
 **\/Zc:inline** を指定すると、`inline` として宣言されたすべての関数は、使用される場合に同じ翻訳単位内に使用可能な定義が必要があるという C\+\+11 の要件がコンパイラによって適用されます。  このオプションを指定しない場合、[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] では、定義を参照できなくても `inline` として宣言された関数を起動する非準拠コードが許可されます。  詳細については、C\+\+11 標準のセクション 3.2 およびセクション 7.1.2 を参照してください。  このコンパイラ オプションは、Visual Studio 2013 更新プログラム 2 で導入されました。  
  
 **\/Zc:inline** オプションを使用するには、非準拠コードを更新します。  この例では、既定の **\/Zc:inline\-** オプションを使用する場合、定義のないインライン関数宣言の非準拠の使用でもコンパイルおよびリンクされることを示します。  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 **\/Zc:inline** を有効にすると、同じコードで [LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md) エラーが発生します。コンパイラによって、example.obj 内の `Example::inline_call` のインライン展開されていないコード本体が出力されないためです。  これにより、`main` 内のインライン展開されていない呼び出しは、定義されていない外部シンボルを参照します。  
  
 このエラーを解決するには、`inline` キーワードを `Example::inline_call` の宣言から削除するか、`Example::inline_call` の定義をヘッダー ファイルに移動するか、`Example` の実装を main.cpp に移動します。  次の例では、定義をヘッダー ファイルに移動します。そこでは、ヘッダーを含む任意の呼び出し元から定義を参照できます。  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Visual C\+\+ の準拠に関する問題の詳細については、「[非標準動作](../Topic/Nonstandard%20Behavior.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  `/Zc:inline` が含まれるように **\[追加オプション\]** プロパティを変更し、**\[OK\]** をクリックします。  
  
## 参照  
 [\/Zc \(準拠\)](../../build/reference/zc-conformance.md)