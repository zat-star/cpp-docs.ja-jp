---
title: "コンパイラ エラー C3012 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: 9
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: e7cf30b5aa214c5042e430377cf839e463140149
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3012"></a>コンパイラ エラー C3012
'intrinsic': 組み込み関数を、並行領域内で使用することはできません  
  
 A[コンパイラ組み込み関数](../../intrinsics/compiler-intrinsics.md)で関数が許可されていません、`omp``parallel`領域。  
  
 次の例では C3012 が生成されます。  
  
```  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C"  
{  
#endif  
  
void* _ReturnAddress();  
  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   _ReturnAddress();   // OK  
  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
}  
```
