---
title: "コンパイラ エラー C3001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3001
dev_langs:
- C++
helpviewer_keywords:
- C3001
ms.assetid: d0e03478-1b44-47e5-8f5b-70415fa1f8bc
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
ms.openlocfilehash: 6bde06b4c0fab83acaa66ab742dd7e834a07f12f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3001"></a>コンパイラ エラー C3001
'error_text': OpenMP ディレクティブ名が必要です。  
  
 `omp` プラグマは、ディレクティブの前になければなりません。  
  
 次の例では C3001 が生成されます。  
  
```  
// C3001.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp   // C3001 missing token  
}  
```
