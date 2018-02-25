---
title: "omp_get_wtime |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- omp_get_wtime
dev_langs:
- C++
helpviewer_keywords:
- omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57307df6a2e13c6bd3dbd90892669119f8526d70
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompgetwtime"></a>omp_get_wtime
ある時点から経過した時間の秒の値を返します。  
  
## <a name="syntax"></a>構文  
  
```  
double omp_get_wtime( );  
```  
  
## <a name="return-value"></a>戻り値  
 一貫したもの、任意のポイントからの経過時間の秒数値を返します。  
  
## <a name="remarks"></a>コメント  
 そのポイントは、後続の比較ができるように、プログラム実行中に一貫性のあるは残ります。  
  
 詳細については、次を参照してください。 [3.3.1 omp_get_wtime 関数](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_get_wtime.cpp  
// compile with: /openmp  
#include "omp.h"  
#include <stdio.h>  
#include <windows.h>  
  
int main() {  
    double start = omp_get_wtime( );  
    Sleep(1000);  
    double end = omp_get_wtime( );  
    double wtick = omp_get_wtick( );  
  
    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",  
             start, end, end - start);  
  
    printf_s("wtick = %.16g\n1/wtick = %.16g\n",  
             wtick, 1.0 / wtick);  
}  
```  
  
```Output  
start = 594255.3671159324  
end = 594256.3664474116  
diff = 0.9993314791936427  
wtick = 2.793651148400146e-007  
1/wtick = 3579545  
```  
  
## <a name="see-also"></a>参照  
 [関数](../../../parallel/openmp/reference/openmp-functions.md)