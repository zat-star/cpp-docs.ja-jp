---
title: "コンパイラ エラー C3042 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3042
dev_langs: C++
helpviewer_keywords: C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15099fd212c58df0369749a497a277ecb7f6987e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3042"></a>コンパイラ エラー C3042
'copyprivate' 句および 'nowait' 句は、OpenMP 'directive' ディレクティブで同時に使用することはできません  
  
 [copyprivate](../../parallel/openmp/reference/copyprivate.md) 句と [nowait](../../parallel/openmp/reference/nowait.md) 句は、指定されたディレクティブでは同時に使用できません。 このエラーを解決するには、 `copyprivate` 句か `nowait` 句の一方または両方を削除します。  
  
 次の例では C3042 が生成されます。  
  
```  
// C3042.cpp  
// compile with: /openmp /c  
#include <stdio.h>  
#include "omp.h"  
  
double d;  
  
int main() {  
    #pragma omp parallel private(d)  
   {  
      #pragma omp single copyprivate(d) nowait   // C3042  
      {  
      }  
   }  
}  
```