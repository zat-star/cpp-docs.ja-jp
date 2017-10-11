---
title: "コンパイラ エラー C2007 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
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
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7b4cb49426125df28793e7d2b7800198a129db3d
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

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
