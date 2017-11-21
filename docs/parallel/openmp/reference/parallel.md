---
title: "並列 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: parallel
dev_langs: C++
helpviewer_keywords: parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289a4928c9c46f6d758ddc2f30ed864488ab725e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="parallel"></a>parallel
同時に複数のスレッドで実行されるコードである並列領域を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `clause` (省略可能)  
 0 個以上の句。  サポートされている句の一覧については、「解説」セクションを参照してください**並列**です。  
  
## <a name="remarks"></a>コメント  
 **並列**ディレクティブは、次の OpenMP 句をサポートしています。  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [共有](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **並列**でも使用できます、[セクション](../../../parallel/openmp/reference/sections-openmp.md)と[の](../../../parallel/openmp/reference/for-openmp.md)ディレクティブです。  
  
 詳細については、次を参照してください。 [2.3 parallel コンストラクト](../../../parallel/openmp/2-3-parallel-construct.md)です。  
  
## <a name="example"></a>例  
 次の例では、スレッドの数を設定し、並行領域を定義する方法を示します。 既定では、スレッドの数は、コンピューター上の論理プロセッサの数と同じです。 たとえば、ハイパースレッディングが有効になっている 1 つの物理プロセッサを搭載したマシンがある場合は、2 つの論理プロセッサと 2 つのスレッドがあります。  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>コメント  
 出力の順序は、別のコンピューターで異なることに注意してください。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)