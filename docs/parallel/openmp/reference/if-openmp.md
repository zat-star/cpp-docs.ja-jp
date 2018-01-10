---
title: "場合 (OpenMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: if OpenMP clause
ms.assetid: db5940b6-2414-4bf8-934d-3edd8393c0f8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 81952612a80ac74cd4bfca62a1b2d62c910cb8f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="if-openmp"></a>if (OpenMP)
並列または直列に、ループを実行するかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
if(expression)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `expression`  
 True (ゼロ以外) と評価された場合は、並列実行する並列領域で、コードを原因となる整数式です。 式の評価が false (0)、並列領域が (1 つのスレッド) を直列に実行されます。  
  
## <a name="remarks"></a>コメント  
 `if`次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [セクション](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_if.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
void test(int val)  
{  
    #pragma omp parallel if (val)  
    if (omp_in_parallel())  
    {  
        #pragma omp single  
        printf_s("val = %d, parallelized with %d threads\n",  
                 val, omp_get_num_threads());  
    }  
    else  
    {  
        printf_s("val = %d, serialized\n", val);  
    }  
}  
  
int main( )  
{  
    omp_set_num_threads(2);  
    test(0);  
    test(2);  
}  
```  
  
```Output  
val = 0, serialized  
val = 2, parallelized with 2 threads  
```  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)