---
title: OMP_NUM_THREADS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OMP_NUM_THREADS
dev_langs:
- C++
helpviewer_keywords:
- OMP_NUM_THREADS OpenMP environment variable
ms.assetid: 4b558124-1387-4c30-a6a5-ff5345a9ced6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 077a709d70e19e62133e5b48e42f2e53ac7c835f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ompnumthreads"></a>OMP_NUM_THREADS
オーバーライドされない限り、並行領域内のスレッドの最大数を設定[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[num_threads](../../../parallel/openmp/reference/num-threads.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_NUM_THREADS[=num]  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `num`  
 Visual C の実装では 64 まで、並列領域で目的のスレッドの最大数。  
  
## <a name="remarks"></a>コメント  
 **OMP_NUM_THREADS**で環境変数をオーバーライドすることができます、 [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)関数または[num_threads](../../../parallel/openmp/reference/num-threads.md)です。  
  
 既定値の`num`Visual C の OpenMP 標準の実装は、ハイパー スレッドの Cpu を含む、仮想プロセッサの数。  
  
 詳細については、次を参照してください。 [4.2 OMP_NUM_THREADS](../../../parallel/openmp/4-2-omp-num-threads.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、 **OMP_NUM_THREADS** 16 に環境変数。  
  
```  
set OMP_NUM_THREADS=16  
```  
  
 次のコマンドの現在の設定を表示する、 **OMP_NUM_THREADS**環境変数。  
  
```  
set OMP_NUM_THREADS  
```  
  
## <a name="see-also"></a>参照  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)