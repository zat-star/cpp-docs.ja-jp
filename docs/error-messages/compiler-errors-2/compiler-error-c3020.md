---
title: "コンパイラ エラー C3020 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3020
dev_langs: C++
helpviewer_keywords: C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51275874ff28c41704d8a8daa8c2e0f1f6058c49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3020"></a>コンパイラ エラー C3020
'var': OpenMP の 'for' ループのインデックス変数は、ループの本体では変更できません  
  
 OpenMP`for`ループ可能性があります (ループ カウンター) の本文内のインデックスを変更していない、`for`ループします。  
  
 次の例では、C3020 が生成されます。  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 宣言された変数[lastprivate](../../parallel/openmp/reference/lastprivate.md)並列化されたループ内のインデックスとして使用することはできません。  
  
 次の例は、C3020 の 2 つ目の lastprivate その lastprivate が for ループ内で最も外側の idx_a への書き込みをトリガーするためです。 その lastprivate for ループ (技術的には、最後に、前回のイテレーションの) 最も外側の外部 idx_a への書き込みをトリガーするため、最初の lastprivate はエラーを提供しません。 次の例では、C3020 を生成します。  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 次の例では、考えられる解決策を示しています。  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```