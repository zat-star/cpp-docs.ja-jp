---
title: "コンパイラの警告 (レベル 1) C4258 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 436ef3dd9984750885390a3974572b9d86bd7243
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258
'variable': 定義から、ループが無視されます。外側のスコープから定義を使用すると"  
  
 [/Ze](../../build/reference/za-ze-disable-language-extensions.md)と[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で定義された変数、[の](../../cpp/for-statement-cpp.md)ループが後にスコープ外に出る、**の**ループが終了します。 この警告を含むスコープの外側のループ内で定義された、ループ変数と同じ名前を持つ変数が再度使用される場合に発生、**の**ループします。 例:  
  
```  
// C4258.cpp  
// compile with: /Zc:forScope /W1  
int main()  
{  
   int i;  
   {  
      for (int i =0; i < 1; i++)  
         ;  
      i = 20;   // C4258 i (in for loop) has gone out of scope  
   }  
}  
```