---
title: "コンパイラ エラー C3052 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3052
dev_langs:
- C++
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 59686a585f66092fbf059cc5e84f7da493134b7f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3052"></a>コンパイラ エラー C3052
'var': 変数が、default(none) 句の下のデータ共有句に使用されていません  
  
 [default(none)](../../parallel/openmp/reference/default-openmp.md) が使用されている場合は、構造化ブロックで使用される変数を明示的に [shared](../../parallel/openmp/reference/shared-openmp.md) または [private](../../parallel/openmp/reference/private-openmp.md)として指定する必要があります。  
  
 次の例では C3052 が生成されます。  
  
```  
// C3052.cpp  
// compile with: /openmp /c  
int main() {  
   int n1 = 1;  
  
   #pragma omp parallel default(none) // shared(n1) private(n1)  
   {  
      n1 = 0;   // C3052 use either a shared or private clause  
   }  
}  
```
