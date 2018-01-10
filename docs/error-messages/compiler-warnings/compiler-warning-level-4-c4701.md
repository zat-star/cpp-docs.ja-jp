---
title: "コンパイラの警告 (レベル 4) C4701 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4701
dev_langs: C++
helpviewer_keywords: C4701
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d001827c1d3e73ee4724aa52543231a43d41af5c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4701"></a>コンパイラの警告 (レベル 4) C4701
初期化されていない可能性があるローカル変数 'name' の使用  
  
 ローカル変数*名前*値を割り当てられることがなく使用される可能性があります。 これは、予期しない結果に可能性があります。  
  
## <a name="example"></a>例  
 次のコードには、C4701 と C4703 が生成されます。  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
```Output  
c:\src\test.cpp(10) : warning C4701: potentially uninitialized local variable 'p' used  
c:\src\test.cpp(10) : warning C4703: potentially uninitialized local pointer variable 'p' used  
  
```  
  
 この警告を解決するには、この例で示すように、変数を初期化します。  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## <a name="see-also"></a>参照  
 [コンパイラの警告 (レベル 4) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [警告、/sdl、および初期化されていない変数の検出の向上](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)