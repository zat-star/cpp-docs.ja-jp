---
title: "コンパイラ エラー C2019 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2019
dev_langs:
- C++
helpviewer_keywords:
- C2019
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 93c91bccf1b9bc709d006696b22e0e8c2febb713
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2019"></a>コンパイラ エラー C2019
プリプロセッサ ディレクティブが必要です。'character' が見つかりました  
  
 文字の後に、`#`記号はプリプロセッサ ディレクティブの最初の文字ではありません。  
  
 次の例では、C2019 が生成されます。  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 考えられる解決策:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```
