---
title: "1 つ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b93480f01ea35129812b3d4f3c42ce2130046243
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="single"></a>single
コードのセクションをシングル スレッドで実行するように指定することができます。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clause` (省略可能)  
 0 個以上の句。 サポートされている句の一覧については、「解説」セクションを参照してください**単一**です。  
  
## <a name="remarks"></a>コメント  
 **単一**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [マスター](../../../parallel/openmp/reference/master.md)ディレクティブを使用して、コードのセクションをマスター スレッドでのみ実行するように指定できます。  
  
 詳細については、次を参照してください。 [2.4.3 1 つ構築](../../../parallel/openmp/2-4-3-single-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>参照  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)