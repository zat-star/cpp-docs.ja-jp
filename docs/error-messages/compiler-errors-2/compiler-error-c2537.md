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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7095511e401dfb1aa703e1d0be4f998e40416c58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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