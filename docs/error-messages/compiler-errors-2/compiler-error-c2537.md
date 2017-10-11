---
title: "コンパイラ エラー C2537 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 610fe53b68ccfa9f0ec187356a737e67837656a4
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2537"></a>コンパイラ エラー C2537
'specifier': リンケージ仕様  
  
 以下の原因が考えられます。  
  
1.  リンケージ指定子はサポートされていません。 "C"リンケージ指定子のみがサポートされています。  
  
2.  "C"リンケージは、一連のオーバー ロードされた関数の 1 つ以上の関数を指定します。 これは認められていません。  
  
 次の例では、C2537 が生成されます。  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```
