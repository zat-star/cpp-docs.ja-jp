---
title: "フラッシュ (OpenMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Flush
dev_langs: C++
helpviewer_keywords: flush OpenMP directive
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72b69daf431ab9dfd2b5c2ed7cebdc8c5af75847
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="flush-openmp"></a>flush (OpenMP)
すべてのスレッドがすべての共有オブジェクトのメモリについて同じビューを持つことを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp flush [(var)]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var` (省略可能)  
 同期するオブジェクトを表す変数のコンマ区切り一覧。 場合`var`が指定されていない、すべてのメモリをフラッシュします。  
  
## <a name="remarks"></a>コメント  
 **フラッシュ**ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.5 flush ディレクティブ](../../../parallel/openmp/2-6-5-flush-directive.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
```Output  
Thread 0: read data  
Thread 1: process data  
data = 2  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)