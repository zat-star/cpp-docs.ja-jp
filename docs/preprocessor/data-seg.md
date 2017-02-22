---
title: "data_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "data_seg_CPP"
  - "vc-pragma.data_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "data_seg プラグマ"
  - "プラグマ, data_seg"
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# data_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

初期化された変数が格納される、.obj ファイルのデータ セグメントを指定します。  
  
## 構文  
  
```  
  
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 解説  
 このトピックでは、*セグメント*と*セクション*は同義の用語です。  
  
 OBJ ファイルは [dumpbin](../build/reference/dumpbin-command-line.md) アプリケーションで表示できます。  初期化される変数の .obj ファイルの既定セグメントは、.data です。  初期化されていない変数は、ゼロに初期化されたものと見なされ、bss に格納されます。  
  
 パラメーターなしの **data\_seg** により、セグメントは .data にリセットされます。  
  
 **push** \(省略可能\)  
 レコードを内部コンパイラ スタックに格納します。  **push** は *identifier* と *segment\-name* を持つことができます。  
  
 **pop** \(省略可能\)  
 内部コンパイラ スタックの最上部からレコードを削除します。  
  
 *identifier* \(省略可能\)  
 **push** と共に使用した場合、内部コンパイラ スタックのレコードに名前を割り当てます。  **pop** と共に使用した場合、*identifier* が削除されるまでレコードを内部スタックからポップします。*identifier* が内部スタックにない場合は何もポップされません。  
  
 *identifier* を使用すると、1 つの **pop** コマンドで複数のレコードをポップできます。  
  
 *"segment\-name"* \(省略可能\)  
 セグメントの名前。 **pop** と共に使用した場合、スタックがポップされ、*segment\-name* がアクティブなセグメント名になります。  
  
 *"segment\-class"* \(省略可能\)  
 Version 2.0 未満の C\+\+ との互換性のために残されています。  これは無視されます。  
  
## 使用例  
  
```  
// pragma_directive_data_seg.cpp  
int h = 1;                     // stored in .data  
int i = 0;                     // stored in .bss  
#pragma data_seg(".my_data1")  
int j = 1;                     // stored in "my_data1"  
  
#pragma data_seg(push, stack1, ".my_data2")     
int l = 2;                     // stored in "my_data2"  
  
#pragma data_seg(pop, stack1)   // pop stack1 off the stack  
int m = 3;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 **data\_seg** を使用して割り当てられたデータは、その位置に関する情報を保持しません。  
  
 セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
 const 変数のセクション \([const\_seg](../preprocessor/const-seg.md)\)、初期化されていないデータのセクション \([bss\_seg](../preprocessor/bss-seg.md)\)、および関数のセクション \([code\_seg](../preprocessor/code-seg.md)\) を指定することもできます。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)