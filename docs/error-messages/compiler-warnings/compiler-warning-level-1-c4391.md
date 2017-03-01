---
title: "コンパイラの警告 (レベル 1) C4391 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4391
dev_langs:
- C++
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 81b7e6ba142edb94dd77f4a63c42b245b61ccc45
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4391"></a>コンパイラの警告 (レベル 1) C4391
'signature': 'type' 組み込み関数の戻り値の型が正しくないが期待どおり  
  
 コンパイラ組み込み関数の関数宣言には、間違ったの戻り値の型が必要があります。 生成されるイメージが正しく動作しない可能性があります。  
  
 この警告を解決するか、宣言を修正または宣言を削除し、単に #include 適切なヘッダー ファイルです。  
  
 次の例では、C4391 が生成されます。  
  
```  
// C4391.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_load_ss(float *p);   // C4391  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```
