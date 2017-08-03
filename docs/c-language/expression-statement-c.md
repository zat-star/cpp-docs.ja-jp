---
title: "式ステートメント (C) |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- statements, expression
- expression statements
ms.assetid: 1085982b-dc16-4c1e-9ddd-0cd85c8fe2e3
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ed9c2524c015faaf2aff4467e68d32c01bc31d61
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="expression-statement-c"></a>式ステートメント (C)
式ステートメントが実行されると、式は「[式と代入](../c-language/expressions-and-assignments.md)」で説明されている規則に従って評価されます。  
  
## <a name="syntax"></a>構文  
 *expression-statement*:  
 *expression* opt**;**  
  
 式の評価に伴うすべての副作用は、次のステートメントが実行される前に完了します。 空の式ステートメントは null ステートメントと呼ばれます。 詳細については、「[Null ステートメント](../c-language/null-statement-c.md)」を参照してください。  
  
 次の例は、式ステートメントを示します。  
  
```  
x = ( y + 3 );            /* x is assigned the value of y + 3  */  
x++;                      /* x is incremented                  */  
x = y = 0;                /* Both x and y are initialized to 0 */  
proc( arg1, arg2 );       /* Function call returning void      */  
y = z = ( f( x ) + 3 );   /* A function-call expression        */  
```  
  
 最後のステートメントは関数呼び出し式で、関数によって返される任意の値を含む式の値が 3 増加し、変数 `y` と `z` の両方に割り当てられます。  
  
## <a name="see-also"></a>関連項目  
 [ステートメント](../c-language/statements-c.md)
