---
title: "コンパイラの警告 (レベル 1) C4561 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4561
dev_langs:
- C++
helpviewer_keywords:
- C4561
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03fd67baa07b297ded01e06da37cad2a7cc97c68
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4561"></a>コンパイラの警告 (レベル 1) C4561
'_ _fastcall' と互換性のない、'/clr' オプション: への変換 '\__stdcall'  
  
 [_ _Fastcall](../../cpp/fastcall.md)で関数呼び出し規約は使用できません、 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)コンパイラ オプション。 コンパイラへの呼び出しは無視`__fastcall`です。 この警告を解決するへの呼び出しを削除するか**_ _fastcall**なしでコンパイルまたは**/clr**です。  
  
 次の例では、C4561 が生成されます。  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```