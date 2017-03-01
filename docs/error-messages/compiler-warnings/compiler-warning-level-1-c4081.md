---
title: "コンパイラの警告 (レベル 1) C4081 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4081
dev_langs:
- C++
helpviewer_keywords:
- C4081
ms.assetid: 6f656373-a080-4989-bbc9-e2f894b03293
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 321f2df21db6ff867ba2f0f09039cf4e23924e95
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4081"></a>コンパイラの警告 (レベル 1) C4081
'token1' が必要でしたが、'token2' が見つかりました  
  
 コンパイラでは、このコンテキストで別のトークンが必要でした。  
  
## <a name="example"></a>例  
  
```  
// C4081.cpp  
// compile with: /W1 /LD  
#pragma optimize) "l", on )   // C4081  
```
