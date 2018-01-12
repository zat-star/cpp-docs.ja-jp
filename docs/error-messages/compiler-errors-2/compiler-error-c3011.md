---
title: "コンパイラ エラー C3011 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3011
dev_langs: C++
helpviewer_keywords: C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 81c6c1901b9392e80e31baaf61a8c7ec5739b5c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3011"></a>コンパイラ エラー C3011
インライン アセンブリを、並行領域内で使用することはできません  
  
 `omp` 並列領域は、インライン アセンブリの命令を含めることはできません。  
  
 次の例では C3011 が生成されます。  
  
```  
// C3011.cpp  
// compile with: /openmp  
// processor: /x86  
int main() {  
   int   n = 0;  
  
   #pragma omp parallel  
   {  
      _asm mov eax, n   // Delete this line to resolve this error.  
   }   // C3011  
}  
```