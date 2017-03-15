---
title: "コンパイラの警告 (レベル 1) C4258 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
caps.latest.revision: 7
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
ms.openlocfilehash: 0f3da4315033fe33282526c6a67de6b6666c8604
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4258"></a>コンパイラの警告 (レベル 1) C4258
'variable': 定義から、ループは無視します。外側のスコープの定義を使用すると"  
  
 [/Ze](../../build/reference/za-ze-disable-language-extensions.md)と[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で定義された変数、[の](../../cpp/for-statement-cpp.md)ループの後のスコープから外れ、**の**ループが終了します。 外側のループ内で定義された、ループ変数と同じ名前の変数がスコープを含むでもう一度使用されている場合、この警告が発生した、**の**ループします。 例:  
  
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
