---
title: "コンパイラの警告 (レベル 1) C4600 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4600
dev_langs: C++
helpviewer_keywords: C4600
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b031f423d2230ffea03c33d35c3d959cafc9bf37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4600"></a>コンパイラの警告 (レベル 1) C4600
\#プラグマ 'macro name': 有効な空でない文字列が必要です  
  
 Push またはいずれかで、マクロ名を表示するときに、空の文字列を指定することはできません、 [pop_macro](../../preprocessor/pop-macro.md)または[push_macro](../../preprocessor/push-macro.md)です。  
  
 次の例では、C4600 が生成されます。  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```