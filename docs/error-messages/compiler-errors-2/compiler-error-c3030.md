---
title: "コンパイラ エラー C3030 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3030
dev_langs:
- C++
helpviewer_keywords:
- C3030
ms.assetid: de92fd7e-29ba-46e8-b43b-f4b985cd74de
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 96e4e3c823bd5a9523ebc7bde74ae808bab9e860
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3030"></a>コンパイラ エラー C3030
'var': 'reduction' 句またはディレクティブ内の変数は参照型を含むことはできません  
  
 reduction 句などの特定の句には、値パラメーターのみを渡すことができます。  
  
 次の例では C3030 が生成されます。  
  
```  
// C3030.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
void test(int &r) {  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
}  
  
void test2(int r) {  
   #pragma omp parallel reduction(+ : r)   // OK  
      ;  
}  
  
int main(int argc, char** argv) {  
   int& r = *((int*)argv);  
   int s = *((int*)argv);  
  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
  
   #pragma omp parallel reduction(+ : s)   // OK  
      ;  
}  
```
