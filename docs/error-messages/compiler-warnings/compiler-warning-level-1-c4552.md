---
title: "コンパイラの警告 (レベル 1) C4552 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4552
dev_langs:
- C++
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
caps.latest.revision: 6
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: fc791c0576f8961f0de72a2677b1b48d8d86afdd
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4552"></a>コンパイラの警告 (レベル 1) C4552
'operator': 演算子も何も起こりません。予期される演算子の副作用  
  
 式ステートメントしない副作用を伴う演算子式の一番上にある場合、誤りと思われます。  
  
 この警告を無効にするには、かっこで囲まれた式を配置します。  
  
 次の例では、C4552 が生成されます。  
  
```  
// C4552.cpp  
// compile with: /W1  
int main() {  
   int i, j;  
   i + j;   // C4552  
   // try the following line instead  
   // (i + j);  
}  
```
