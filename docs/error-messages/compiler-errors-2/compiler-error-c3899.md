---
title: "コンパイラ エラー C3899 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c7d9d32b3063dbecde375159ad90eec5bf128d56
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3899"></a>コンパイラ エラー C3899
'var': クラス 'class' の並行領域内で直接 initonly データ メンバーの左辺値の使用が許可されていません  
  
 [Initonly (C + + CLI)](../../dotnet/initonly-cpp-cli.md)内にあるコンス トラクターの部分の内部データ メンバーを初期化することはできません、[並列](../../parallel/openmp/reference/parallel.md)領域。  これは、コンパイラがそのコードの内部に従った再配置、コンス トラクターの一部では実質的に不要になったことなどです。  
  
 を解決するのには、initonly データ メンバーが、そのコンス トラクターが、並列領域の外を初期化します。  
  
## <a name="example"></a>例  
 次の例では、C3899 を生成します。  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```
