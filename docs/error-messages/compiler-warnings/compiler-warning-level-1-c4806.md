---
title: "コンパイラの警告 (レベル 1) C4806 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4806
dev_langs:
- C++
helpviewer_keywords:
- C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 021b0a5fd91df53e8fd1cb297c5d697f7135ff89
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4806"></a>コンパイラの警告 (レベル 1) C4806
'operation': 安全でない演算: 'type' 型から 'type' 型への上位変換を行うと与えられた定数に等しくなりません  
  
 このメッセージは、 `b == 3`に `b` 型がある `bool`などのコードに対して警告を行います。 上位変換の規則に従って、 `bool` が `int`に上位変換されます。 これは有効ですが、 **true**にすることはできません。 次の例では C4806 が生成されます。  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```
