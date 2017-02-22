---
title: "const_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.const_seg"
  - "const_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_seg プラグマ"
  - "プラグマ, const_seg"
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# const_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[const](../cpp/const-cpp.md) 変数が格納されている .obj ファイル内のセグメントを指定します。  
  
## 構文  
  
```  
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 解説  
 このトピックでは、*セグメント*と*セクション*は同義の用語です。  
  
 OBJ ファイルは [dumpbin](../build/reference/dumpbin-command-line.md) アプリケーションで表示できます。  `const` 変数の .obj ファイルの既定セグメントは、.rdata です。  スカラーのような一部の `const` 変数は、コード ストリームに自動的にインライン展開されます。  インライン コードは、.rdata には現れません。  
  
 `const_seg` 内に動的な初期化を必要とするオブジェクトを定義すると、未定義の動作が発生します。  
  
 パラメーターなしの `#pragma const_seg` は、セグメントを .rdata にリセットします。  
  
 `push` \(省略可能\)  
 レコードを内部コンパイラ スタックに格納します。  `push` には `identifier` と `segment-name` を指定できます。  
  
 `pop` \(省略可能\)  
 内部コンパイラ スタックの最上部からレコードを削除します。  
  
 `identifier` \(省略可能\)  
 `push` と共に使用した場合、内部コンパイラ スタックのレコードに名前を割り当てます。  `pop` と共に使用した場合、`identifier` が削除されるまでレコードを内部スタックからポップします。`identifier` が内部スタックにない場合は何もポップされません。  
  
 `identifier` を使用して、複数のレコードを 1 つの `pop` コマンドでポップできます。  
  
 "`segment-name`" \(省略可能\)  
 引数の名前。  `pop` と共に使用した場合、スタックがポップされ、`segment-name` がアクティブなセグメント名になります。  
  
 "`segment-class`" \(省略可能\)  
 Version 2.0 未満の C\+\+ との互換性のために残されています。  これは無視されます。  
  
## 使用例  
  
```  
// pragma_directive_const_seg.cpp  
// compile with: /EHsc  
#include <iostream>  
  
const int i = 7;               // inlined, not stored in .rdata  
const char sz1[]= "test1";     // stored in .rdata  
  
#pragma const_seg(".my_data1")  
const char sz2[]= "test2";     // stored in .my_data1  
  
#pragma const_seg(push, stack1, ".my_data2")  
const char sz3[]= "test3";     // stored in .my_data2  
  
#pragma const_seg(pop, stack1) // pop stack1 from stack  
const char sz4[]= "test4";     // stored in .my_data1  
  
int main() {  
    using namespace std;  
   // const data must be referenced to be put in .obj  
   cout << sz1 << endl;  
   cout << sz2 << endl;  
   cout << sz3 << endl;  
   cout << sz4 << endl;  
}  
```  
  
  **test1**  
**test2**  
**test3**  
**test4**   
## コメント  
 セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
 初期化されたデータのセクション \([data\_seg](../preprocessor/data-seg.md)\)、初期化されていないデータのセクション \([bss\_seg](../preprocessor/bss-seg.md)\)、および関数のセクション \([code\_seg](../preprocessor/code-seg.md)\) を指定することもできます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)