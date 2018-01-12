---
title: "コンパイラの警告 (レベル 1) C4549 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4549
dev_langs: C++
helpviewer_keywords: C4549
ms.assetid: 81a07676-625b-4f58-9b0c-3ee22830b04a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0609899d3e9e209cec8a63673ed89f883e227e1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4549"></a>コンパイラの警告 (レベル 1) C4549
'operator': コンマも何も起こりません前の演算子。'operator' を意図しましたか。  
  
 正しい形式でコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
 次の例では、C4549 が生成されます。  
  
```  
// C4549.cpp  
// compile with: /W1  
#pragma warning (default : 4549)  
  
int main() {  
   int i = 0, k = 0;  
  
   if ( i == 0, k )   // C4549  
   // try the following line instead  
   // if ( i == 0 )  
      i++;  
}  
```