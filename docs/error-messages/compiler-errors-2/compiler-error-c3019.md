---
title: "コンパイラ エラー C3019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3019
dev_langs:
- C++
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a2ef8264326ec47cead99d2c492cb7ec725d3929
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3019"></a>コンパイラ エラー C3019
OpenMP 'for' ステートメントのインクリメントには、正しくない形式が含まれています  
  
 OpenMP のインクリメント部分`for`ループ インデックス変数、演算子の右辺と左辺の両方を使用する必要があります。  
  
 次の例では、c3019 エラーが生成されます。  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```
