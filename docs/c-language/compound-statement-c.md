---
title: "複合ステートメント (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "compound ステートメント"
  - "ステートメント, 複合"
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 複合ステートメント (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

複合ステートメント \("ブロック" ともいう\) は通常、**if** ステートメントなどの別のステートメントの本体として現れます。  「[宣言および型](../c-language/declarations-and-types.md)」では、複合ステートメントの先頭に記述できる宣言の形式とその意味について説明しています。  
  
## 構文  
 *compound\-statement*:  
 **{**  *declaration\-list*  opt *statement\-list* opt **}**  
  
 *declaration\-list*:  
 *declaration*  
  
 *declaration\-list declaration*  
  
 *statement\-list*:  
 s*tatement*  
  
 *statement\-list statement*  
  
 宣言がある場合は、すべてのステートメントの前に記述する必要があります。  複合ステートメントの先頭で宣言された識別子のスコープは、その宣言ポイントからブロックの最後までです。  同じ識別子の宣言が内側のブロック内にない限り、ブロック全体から参照可能です。  
  
 複合ステートメントの識別子は、**register**、**static**、または `extern` で明示的に宣言されていない限り、**auto** と想定されます。ただし関数は `extern` にしかできません。  関数宣言で `extern` 指定子の指定を省略できます。それでも、関数は `extern` です。  
  
 `extern` ストレージ クラスを指定して複合ステートメント内で変数または関数が宣言されている場合、ストレージは割り当てられず、初期化は許可されません。  宣言は、他の場所で定義された外部変数または関数を参照します。  
  
 **auto** または **register** キーワードを使用してブロック内で宣言されている変数は、複合ステートメントに入るたびに再割り当てされ、必要に応じて初期化されます。  これらの変数は、複合ステートメントが終了した後は定義されていません。  ブロック内で宣言された変数が **static** 属性を持つ場合、プログラムの実行が開始されるとその変数が初期化されて、その値がプログラム全体で保持されます。  **static** については、「[ストレージ クラス](../c-language/c-storage-classes.md)」を参照してください。  
  
 この例は、複合ステートメントを示しています。  
  
```  
if ( i > 0 )   
{  
    line[i] = x;  
    x++;  
    i--;  
}  
```  
  
 この例では、`i` が 0 を超える場合、複合ステートメント内のすべてのステートメントが順次実行されます。  
  
## 参照  
 [ステートメント](../c-language/statements-c.md)