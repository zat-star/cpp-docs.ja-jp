---
title: "コンパイラの警告 (レベル 4) C4938 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4938
dev_langs:
- C++
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f4e3184d1833da65c73149eb89ab1be8b2249b4e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4938"></a>コンパイラの警告 (レベル 4) C4938
'var' : 浮動小数点の減少変数は、/fp:strict または #pragma fenv_access で矛盾する結果を生じさせる可能性があります  
  
 使用しないでください[/fp。 厳密な](../../build/reference/fp-specify-floating-point-behavior.md)または[fenv_access](../../preprocessor/fenv-access.md) OpenMP の浮動小数点の減少とは異なる順序で合計が計算されるためです。 したがって、結果は、/openmp を使用しない場合の結果と異なる可能性があります。  
  
 次の例では C4938 が生成されます。  
  
```  
// C4938.cpp  
// compile with: /openmp /W4 /fp:strict /c  
// #pragma fenv_access(on)  
extern double *a;   
  
double test(int first, int last) {   
   double sum = 0.0;   
   #pragma omp parallel for reduction(+: sum)   // C4938  
   for (int i = first ; i <= last ; ++i)   
      sum += a[i];   
   return sum;   
}  
```  
  
 明示的な並列化を使用しない場合、合計は次のように計算されます。  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 明示的な並列化 (および 2 つのスレッド) を使用する場合、合計は次のように計算されます。  
  
```  
sum1 = a[first] + ... a[first + last / 2];   
sum2 = a[(first + last / 2) + 1] + ... a[last];   
sum = sum1 + sum2;  
```
