---
title: "OMP_NUM_THREADS |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9fc343fd41bf0661099aee2cb4f890a215a64fed
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
によってオーバーライドされない限り、並列領域でスレッドの最大数を設定[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[num_threads](../../../parallel/openmp/reference/num-threads.md)します。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num`  
 Visual C の実装では 64 まで、並列領域で目的のスレッドの最大数。  
  
## <a name="remarks"></a>コメント  
 **OMP_NUM_THREADS**で環境変数をオーバーライドできる、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数または[num_threads](../../../parallel/openmp/reference/num-threads.md)します。  
  
 既定値の`num`Visual C OpenMP 標準の実装は、ハイパー スレッド Cpu を含む、仮想プロセッサの数。  
  
 詳細については、次を参照してください。 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)します。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_NUM_THREADS** 16 に環境変数。  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 次のコマンドの現在の設定を表示する、 **OMP_NUM_THREADS**環境変数。  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)
