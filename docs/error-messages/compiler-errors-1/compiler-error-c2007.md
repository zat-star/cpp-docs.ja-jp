---
title: "コンパイラ エラー C2007 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2007
dev_langs:
- C++
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 0348c76e0a7a4e78eb4b2928443e7fecbc9853b1
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2007"></a>コンパイラ エラー C2007
\#構文を定義します。  
  
 後に識別子が表示されない、`#define`です。 エラーを解決するには、識別子を使用します。  
  
 次の例では、C2007 が生成されます。  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 考えられる解決策:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```
