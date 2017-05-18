---
title: "コンパイラ エラー C2233 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2233
dev_langs:
- C++
helpviewer_keywords:
- C2233
ms.assetid: 236bdf0b-9607-4f26-a249-d8def0b1333c
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4f34eb4ad95aa8059a0d8590c3b76d4d9a3d4128
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2233"></a>コンパイラ エラー C2233
'identifier': サイズが&0; の配列を含むオブジェクトの配列は有効  
  
 配列内の各オブジェクトは、少なくとも&1; つの要素を含める必要があります。  
  
 次の例では、C2233 が生成されます。  
  
```  
// C2233.cpp  
// compile with: /c  
class A {  
   char somearray[1];  
};  
  
class B {  
   char zeroarray[];  
};  
  
A array[100];   // OK  
B array2[100];   // C2233  
```
