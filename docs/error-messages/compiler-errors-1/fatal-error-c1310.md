---
title: "致命的なエラー C1310 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1310
dev_langs:
- C++
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 05955990b1df5d2e64215a96a5da205d45539bc0
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1310"></a>致命的なエラー C1310
ガイド付き最適化のプロファイルは OpenMP と共に使用できません  
  
 [/GL](../../build/reference/ltcg-link-time-code-generation.md) を使用してコンパイルしたモジュールを [/LTCG:PGI](../../build/reference/gl-whole-program-optimization.md)でリンクさせることはできません。  
  
 次の例では C1310 が生成されます。  
  
```  
// C1310.cpp  
// compile with: /openmp /GL /link /LTCG:PGI  
// C1310 expected  
int main()  
{  
   int i = 0, j = 10;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 0; i++)   
         --j;  
   }  
}  
```
