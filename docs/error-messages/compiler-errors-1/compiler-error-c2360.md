---
title: "コンパイラ エラー C2360 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2360
dev_langs: C++
helpviewer_keywords: C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 12b62d31c125dfc353623fa7cf10fce578698332
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2360"></a>コンパイラ エラー C2360
'identifier' の初期化が 'case' ラベルによって行われませんでした。  
  
 初期化`identifier`でスキップすることができます、`switch`ステートメントです。 宣言がブロックで囲まれている場合を除き、初期化子を含む宣言ジャンプすることはできません。 (ブロック内で宣言されている場合を除き、変数はスコープ内で最後までの`switch`ステートメントです)。  
  
 次の例では、C2360 が生成されます。  
  
```  
// C2360.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      int i = 1;  
      { int j = 1; }  
   case 1 :   // C2360  
      int k = 1;  
   }  
}  
```  
  
 考えられる解決策:  
  
```  
// C2360b.cpp  
int main() {  
   int x = 0;  
   switch ( x ) {  
   case 0 :  
      { int j = 1; int i = 1;}  
   case 1 :  
      int k = 1;  
   }  
}  
```