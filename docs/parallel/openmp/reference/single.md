---
title: "単一 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: 11
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
ms.openlocfilehash: 7a353009983e0b5a96065fc094dabc0a4afb89e6
ms.lasthandoff: 02/24/2017

---
# <a name="single"></a>single
コードのセクションを単一スレッドで実行すべきことを指定できます。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>パラメーター  
 `clause` (省略可能)  
 0 個以上の句。 サポートされている句の一覧については、「解説」セクションを参照してください**単一**します。  
  
## <a name="remarks"></a>コメント  
 **単一**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [マスター](../../../parallel/openmp/reference/master.md)ディレクティブを使用して、コードのセクションをマスター スレッド上でのみ実行すべきことを指定できます。  
  
 詳細については、次を参照してください。 [2.4.3 単一構築](../../../parallel/openmp/2-4-3-single-construct.md)します。  
  
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
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)
