---
title: "copyprivate |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- copyprivate
dev_langs:
- C++
helpviewer_keywords:
- copyprivate OpenMP clause
ms.assetid: 02c0209d-abe8-4797-8365-a82b53c3f15d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ed78f73edce6b84f53b8fe61199d4b75a40ee57
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="copyprivate"></a>copyprivate
すべてのスレッド間で 1 つまたは複数の変数を共有する必要がありますを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
copyprivate(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 共有する 1 つまたは複数の変数。 複数の変数が指定されている場合は、変数名をコンマで区切ります。  
  
## <a name="remarks"></a>コメント  
 `copyprivate` 適用されます、[単一](../../../parallel/openmp/reference/single.md)ディレクティブです。  
  
 詳細については、次を参照してください。 [2.7.2.8 copyprivate](../../../parallel/openmp/2-7-2-8-copyprivate.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_copyprivate.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
float x, y, fGlobal = 1.0;  
#pragma omp threadprivate(x, y)  
  
float get_float() {  
   fGlobal += 0.001;  
   return fGlobal;  
}  
  
void use_float(float f, int t) {  
   printf_s("Value = %f, thread = %d\n", f, t);  
}  
  
void CopyPrivate(float a, float b) {  
   #pragma omp single copyprivate(a, b, x, y)   
   {  
      a = get_float();  
      b = get_float();  
      x = get_float();  
      y = get_float();  
    }  
  
   use_float(a, omp_get_thread_num());     
   use_float(b, omp_get_thread_num());     
   use_float(x, omp_get_thread_num());  
   use_float(y, omp_get_thread_num());  
}  
  
int main() {  
   float a = 9.99, b = 123.456;  
  
   printf_s("call CopyPrivate from a single thread\n");  
   CopyPrivate(9.99, 123.456);  
  
   printf_s("call CopyPrivate from a parallel region\n");  
   #pragma omp parallel       
   {  
      CopyPrivate(a, b);  
   }  
}  
```  
  
```Output  
call CopyPrivate from a single thread  
Value = 1.001000, thread = 0  
Value = 1.002000, thread = 0  
Value = 1.003000, thread = 0  
Value = 1.004000, thread = 0  
call CopyPrivate from a parallel region  
Value = 1.005000, thread = 0  
Value = 1.005000, thread = 1  
Value = 1.006000, thread = 0  
Value = 1.006000, thread = 1  
Value = 1.007000, thread = 0  
Value = 1.007000, thread = 1  
Value = 1.008000, thread = 0  
Value = 1.008000, thread = 1  
```  
  
## <a name="see-also"></a>参照  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)