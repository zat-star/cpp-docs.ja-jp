---
title: "コンパイラの警告 (レベル 1) C4508 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a2d54a87565c3217168dc077f5aa79614fee080b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4508"></a>コンパイラの警告 (レベル 1) C4508
'function': 関数が値を返す必要があります'void' の戻り値型と見なされます  
  
 関数には、指定された戻り値の型がありません。 この場合、C4430 も発生し、コンパイラが (既定値は int) C4430 によって報告された修正プログラムを実装します。  
  
 この警告を解決するには、関数の戻り値の型を明示的に宣言します。  
  
 次の例では、C4508 が生成されます。  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```
