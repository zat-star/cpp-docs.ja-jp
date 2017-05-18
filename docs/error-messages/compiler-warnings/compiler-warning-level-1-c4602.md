---
title: "コンパイラの警告 (レベル 1) C4602 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4602
dev_langs:
- C++
helpviewer_keywords:
- C4602
ms.assetid: c1f0300f-e2a2-4c9e-a7c3-4c7318d10509
caps.latest.revision: 8
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
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b47b7c0cb0271aa6ab463fb5505af348bc5e75af
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4602"></a>コンパイラの警告 (レベル 1) C4602
\#プラグマ pop_macro: 'macro name' この識別子の前の #pragma push_macro がありません  
  
 使用する場合[pop_macro](../../preprocessor/pop-macro.md)特定のマクロの必要があります最初に合格するには、そのマクロ名[push_macro](../../preprocessor/push-macro.md)です。 たとえば、次の例では C4602 が生成されます。  
  
```  
// C4602.cpp  
// compile with: /W1  
int main()  
{  
   #pragma pop_macro("x")   // C4602 x is not on the stack  
}  
```
