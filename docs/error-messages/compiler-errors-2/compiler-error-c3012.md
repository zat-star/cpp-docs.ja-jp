---
title: "コンパイラ エラー C3012 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3012
dev_langs: C++
helpviewer_keywords: C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32c12397339f861b71fe41566f29fd1a8929b66e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3012"></a>コンパイラ エラー C3012
  
> '*組み込み*': 組み込み関数は、並行領域内で直接使用できません  
  
 A[コンパイラ組み込み関数](../../intrinsics/compiler-intrinsics.md)で関数が許可されていません、`omp parallel`領域。 この問題を解決するには、地域からの組み込みを移動または組み込みで非対応に置き換えます。   
  
## <a name="example"></a>例  
  
 次の例では、C3012 を生成し、その修正方法を示しています。  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```