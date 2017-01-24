---
title: "コンパイラ エラー C3899 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3899"
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : initonly データ メンバーの左辺値は、クラス 'クラス' の並行領域内で使用することはできません  
  
 [initonly](../../dotnet/initonly-cpp-cli.md) データ メンバーは、[parallel](../../parallel/openmp/reference/parallel.md) 領域内にあるコンストラクターの内部で初期化できません。これは、コンパイラはコードを内部で再配置するため、コードが実質的にはコンストラクターの一部ではなくなるためです。  
  
 これを解決するには、並行領域外のコンストラクター内で initonly データ メンバーを初期化します。  
  
## 使用例  
 次の例では C3899 エラーが生成されます。  
  
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