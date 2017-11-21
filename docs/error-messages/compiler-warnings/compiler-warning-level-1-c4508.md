---
title: "コンパイラの警告 (レベル 1) C4508 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4508
dev_langs: C++
helpviewer_keywords: C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d29e821fe29720b065bd9f003e1349c80bbb5c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4508"></a>コンパイラの警告 (レベル 1) C4508
'function': 関数が値を返す必要があります'void' 戻り値の型と見なされます  
  
 関数には、指定された戻り値の型がありません。 この場合、C4430 も発生し、コンパイラが (既定値は int) C4430 によって報告された修正を実装します。  
  
 この警告を解決するには、関数の戻り値の型を明示的に宣言します。  
  
 次の例では、C4508 が生成されます。  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```