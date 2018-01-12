---
title: "_ _noop |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __noop_cpp
- __noop
dev_langs: C++
helpviewer_keywords: __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 348dc23e5ef3744ef1a3f152bf4d4fc5a22d2222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="noop"></a>__noop
**Microsoft 固有の仕様**  
  
 `__noop`組み込み関数を無視することを指定し、引数リストを解析できませんが、引数のコードを生成できません。 これは可変個の引数を受け取るグローバル デバッグ関数で使用するものです。  
  
 コンパイラに変換、`__noop`組み込みコンパイル時に 0 にします。  
  
## <a name="example"></a>例  
 次のコードが使用する方法を示します`__noop`です。  
  
```  
// compiler_intrinsics__noop.cpp  
// compile with or without /DDEBUG  
#include <stdio.h>  
  
#if DEBUG  
   #define PRINT   printf_s  
#else  
   #define PRINT   __noop  
#endif  
  
int main() {  
   PRINT("\nhello\n");  
}  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [キーワード](../cpp/keywords-cpp.md)