---
title: "コンパイラの警告 (レベル 3) C4357 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4357
dev_langs: C++
helpviewer_keywords: C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eecf5286a2a216509e842eea9d231d4f7705c410
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4357"></a>コンパイラの警告 (レベル 3) C4357
に対する仮引数リストで param 配列引数のデリゲート 'del' が 'function' を生成するときは無視されます。  
  
 `ParamArray`属性が無視されました、および`function`変数引数で呼び出されることはできません。  
  
 次の例では、C4357 が生成されます。  
  
```  
// C4357.cpp  
// compile with: /clr /W3 /c  
using namespace System;  
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357  
  
public delegate void g(int i, array<Object^>^ varargs);   // OK  
```