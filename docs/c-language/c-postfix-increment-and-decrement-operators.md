---
title: "C 後置インクリメント演算子と後置デクリメント演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a67e01fe0555a628c8b2178cc580bcaa8f84cd83
ms.lasthandoff: 04/01/2017

---
# <a name="c-postfix-increment-and-decrement-operators"></a>C 後置インクリメント演算子と後置デクリメント演算子
後置インクリメントと後置デクリメントのオペランドは、スカラー型の変更可能な左辺値です。  
  
## <a name="syntax"></a>構文  
 *postfix-expression*:  
 *postfix-expression*  **++**  
  
 *postfix-expression*  **--**  
  
 後置インクリメントまたは後置デクリメントの演算結果は、オペランドの値になります。 結果が得られた後で、オペランドの値がインクリメント (またはデクリメント) されます。 次のコードは、後置インクリメント演算子を示しています。  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 この例では、変数 `var` は 0 と比較されてからインクリメントされます。 `var` がインクリメントされる前に正である場合は、次のステートメントが実行されます。 まず、`q` でポイントされるオブジェクトの値が `p` でポイントされるオブジェクトに代入されます。 次に、`q` と `p` がインクリメントされます。  
  
## <a name="see-also"></a>関連項目  
 [後置インクリメント演算子と後置デクリメント演算子: ++ および --](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)
