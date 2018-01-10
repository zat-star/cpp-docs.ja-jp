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
ms.workload: cplusplus
ms.openlocfilehash: 52139327831be17d6800f30b00f667da7d3b0376
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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