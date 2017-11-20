---
title: "C 後置インクリメント演算子と後置デクリメント演算子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- increment operators, syntax
- scalar operators
- types [C], scalar
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6279ede332ffbcc12db4f8c72e17fe9050cc96e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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