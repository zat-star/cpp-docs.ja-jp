---
title: "bss_seg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.bss_seg"
  - "bss_seg_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bss_seg プラグマ"
  - "プラグマ, bss_seg"
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# bss_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

初期化されていない変数が格納される .obj ファイル内のセグメントを指定します。  
  
## 構文  
  
```  
  
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 解説  
 Obj ファイルは [dumpbin](../build/reference/dumpbin-command-line.md) アプリケーションで表示できます。  初期化されていないデータの .obj ファイルの既定セグメントは、.bss です。  場合によっては **bss\_seg** を使用して、初期化されていないデータを 1 つのセクションにグループ化することで、読み込み時間を短縮できます。  
  
 パラメーターなしの **bss\_seg** は、セグメントを .bss にリセットします。  
  
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
// pragma_directive_bss_seg.cpp  
int i;                     // stored in .bss  
#pragma bss_seg(".my_data1")  
int j;                     // stored in "my_data1"  
  
#pragma bss_seg(push, stack1, ".my_data2")     
int l;                     // stored in "my_data2"  
  
#pragma bss_seg(pop, stack1)   // pop stack1 from stack  
int m;                     // stored in "stack_data1"  
  
int main() {  
}  
```  
  
 初期化されたデータのセクション \([data\_seg](../preprocessor/data-seg.md)\)、関数 \([code\_seg](../preprocessor/code-seg.md)\)、および const 変数のセクション \([const\_seg](../preprocessor/const-seg.md)\) を指定することもできます。  
  
 **bss\_seg** プラグマを使用して割り当てられたデータは、その位置に関する情報を保持しません。  
  
 セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
## 参照  
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)