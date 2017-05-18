---
title: "コンパイラ エラー C3041 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3041
dev_langs:
- C++
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
caps.latest.revision: 8
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
ms.openlocfilehash: a3db28762b8c20c7157b0ae04ee943e654f06cfa
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3041"></a>コンパイラ エラー C3041
'var': 'copyprivate' 句の変数は、それを囲むコンテキスト内でプライベートである必要があります  
  
 渡される変数[copyprivate](../../parallel/openmp/reference/copyprivate.md)外側のコンテキストで共有することはできません。  
  
 次の例では C3041 が生成されます。  
  
```  
// C3041.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
int main() {  
   #pragma omp parallel shared(d)  
   // try the following line instead  
   // #pragma omp parallel private(d)  
   {  
      // or don't make d copyprivate  
      #pragma omp single copyprivate(d)   // C3041  
      {  
      }  
   }  
}  
```
