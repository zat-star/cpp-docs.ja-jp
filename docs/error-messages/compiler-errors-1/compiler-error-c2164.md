---
title: "コンパイラ エラー C2164 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2164
dev_langs: C++
helpviewer_keywords: C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d793a558611cc8fcf08222200a99934edb6cdd34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2164"></a>コンパイラ エラー C2164
'function': 組み込み関数が宣言されていません  
  
 `intrinsic`プラグマは宣言されていない関数を使用して (でのみ発生**/Oi**)。 または、そのヘッダー ファイルを含めずにコンパイラ組み込み関数のいずれかが使用されました。  
  
 次の例では、C2164 が生成されます。  
  
```  
// C2164.c  
// compile with: /c  
// processor: x86  
// Uncomment the following line to resolve.  
// #include "xmmintrin.h"  
void b(float *p) {  
   _mm_load_ss(p);   // C2164  
}  
```