---
title: "コンパイラ エラー C2197 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2197
dev_langs:
- C++
helpviewer_keywords:
- C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3b2f3482a8f66098d42389234924fee9238b7ed0
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2197"></a>コンパイラ エラー C2197
'function': 呼び出しに対する引数が多すぎます  
  
 コンパイラで検出された関数を呼び出すためのパラメーターが多すぎるか、または関数の宣言が正しくありません。  
  
 次の例では C2197 が生成されます。  
  
```  
// C2197.c  
// compile with: /Za /c  
void func( int );  
int main() {  
   func( 1, 2 );   // C2197 two actual parameters  
   func( 2 );   // OK  
}  
```
