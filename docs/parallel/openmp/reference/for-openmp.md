---
title: "(OpenMP) の |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- for
dev_langs:
- C++
helpviewer_keywords:
- for OpenMP directive
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 59b424cc0efb429ed6d01fb46a469594b2737dbe
ms.lasthandoff: 02/24/2017

---
# <a name="for-openmp"></a>for (OpenMP)
行われる動作、スレッド間で除算する並列領域内の for ループします。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp [parallel] for [clauses]  
   for_statement  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `clause` (省略可能)  
 0 個以上の句。 サポートされている句の一覧については、「解説」セクションを参照してください**の**です。  
  
 `for_statement`  
 For ループ A があります。 ユーザー コードで未定義の動作が発生、ループ インデックス変数を変更します。  
  
## <a name="remarks"></a>コメント  
 **の**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [順序付けになります。](../../../parallel/openmp/reference/ordered-openmp-directives.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [削減](../../../parallel/openmp/reference/reduction.md)  
  
-   [スケジュール](../../../parallel/openmp/reference/schedule.md)  
  
 場合**並列**も指定されている`clause`句可能で、**並列**または**の**ディレクティブを除く**nowait**します。  
  
 詳細については、次を参照してください。 [2.4.1 for のコンストラクト](../../../parallel/openmp/2-4-1-for-construct.md)します。  
  
## <a name="example"></a>例  
  
```  
// omp_for.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <math.h>  
#include <omp.h>  
  
#define NUM_THREADS 4  
#define NUM_START 1  
#define NUM_END 10  
  
int main() {  
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;  
   int nThreads = 0, nTmp = nStart + nEnd;  
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *   
                               unsigned(abs(nTmp))) / 2;  
   int nSumCalc = uTmp;  
  
   if (nTmp < 0)  
      nSumCalc = -nSumCalc;  
  
   omp_set_num_threads(NUM_THREADS);  
  
   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)  
   {  
      #pragma omp master  
      nThreads = omp_get_num_threads();  
  
      #pragma omp for  
      for (i=nStart; i<=nEnd; ++i) {  
            #pragma omp atomic  
            nSum += i;  
      }  
   }  
  
   if  (nThreads == NUM_THREADS) {  
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);  
      nRet = 0;  
   }  
   else {  
      printf_s("Expected %d OpenMP threads, but %d were used.\n",  
               NUM_THREADS, nThreads);  
      nRet = 1;  
   }  
  
   if (nSum != nSumCalc) {  
      printf_s("The sum of %d through %d should be %d, "  
               "but %d was reported!\n",  
               NUM_START, NUM_END, nSumCalc, nSum);  
      nRet = 1;  
   }  
   else  
      printf_s("The sum of %d through %d is %d\n",  
               NUM_START, NUM_END, nSum);  
}  
```  
  
```Output  
4 OpenMP threads were used.  
The sum of 1 through 10 is 55  
```  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)
