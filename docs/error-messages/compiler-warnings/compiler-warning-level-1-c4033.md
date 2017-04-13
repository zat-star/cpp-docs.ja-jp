---
title: "コンパイラの警告 (レベル 1) C4033 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4033
dev_langs:
- C++
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
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
ms.openlocfilehash: ee0a3e19ca51bb5cfbfa447aed553fd5985966bc
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4033"></a>コンパイラの警告 (レベル 1) C4033
'function': 値を返さなければいけません  
  
 この関数は値を返しません。 定義されていない値が返されます。  
  
 戻り値のない `return` を使用する関数は、型 `void`として宣言する必要があります。  
  
 このエラーは、C 言語コード用です。  
  
 次の例では C4033 が生成されます。  
  
```  
// C4033.c  
// compile with: /W1 /LD  
int test_1(int x)   // C4033 expected  
{  
   if (x)  
   {  
      return;   // C4033  
   }  
}  
```
