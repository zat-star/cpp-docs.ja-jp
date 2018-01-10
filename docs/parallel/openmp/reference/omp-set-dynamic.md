---
title: "omp_set_dynamic |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_dynamic
dev_langs: C++
helpviewer_keywords: omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13cb098170e46b8459821156aeb8be369bbc1ffa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
実行時以降の並列領域で使用できるスレッドの数を調整できることを示します。  
  
## <a name="syntax"></a>構文  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `val`  
 ランタイムによって、以降の並列領域で使用できるスレッドの数を調整することができるかどうかを示す値。  ゼロ以外の場合、0 の場合、ランタイムは、スレッドの数を調整できます、ランタイムのスレッドの数は動的に調整されません。  
  
## <a name="remarks"></a>コメント  
 スレッドの数はによって設定された値を超えることはありません[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)です。  
  
 使用して[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)の現在の設定を表示する`omp_set_dynamic`です。  
  
 設定`omp_set_dynamic`の設定を上書き、 [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)環境変数。  
  
 詳細については、次を参照してください。 [3.1.7 omp_set_dynamic 関数](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)