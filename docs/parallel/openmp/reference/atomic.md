---
title: "アトミック |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd00244d4668821942e7d6a9f6873652002bddb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="atomic"></a>アトミック
指定するアトミックに更新されるメモリの場所。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>パラメーター  
 `expression`  
 複数書き込みから保護するメモリ位置の値を含むステートメント。 有効な式のフォームの詳細については、OpenMP 仕様を参照してください。  
  
## <a name="remarks"></a>コメント  
 `atomic`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.4 atomic 構築](../../../parallel/openmp/2-6-4-atomic-construct.md)です。  
  
## <a name="example"></a>例  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>参照  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)