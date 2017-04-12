---
title: "コンパイラの警告 (レベル 1) C4750 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4750
dev_langs:
- C++
helpviewer_keywords:
- C4750
ms.assetid: b0b2c938-7d2a-4c36-8270-7daee15ffee3
caps.latest.revision: 5
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
ms.sourcegitcommit: 84f0628de933344eb23dc6325679abdcd3699c3a
ms.openlocfilehash: 6e22ef89b92a5b584979abbd370f82b482cf74e0
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4750"></a>コンパイラの警告 (レベル 1) C4750
'identifier': ループにインライン展開されている _alloca() を含む関数です  
  
 'Identifier' 関数のインライン展開の強制、 [_alloca](../../c-runtime-library/reference/alloca.md)ループが実行されたときにスタック オーバーフローの可能性をループ内の関数です。  
  
### <a name="to-correct-this-error"></a>このエラーを解決するには  
  
1.  'Identifier' 関数が変更されないように、 [_ _forceinline](../../cpp/inline-functions-cpp.md)指定子。  
  
2.  'Identifier' 関数が含まれないように、 [_alloca](../../c-runtime-library/reference/alloca.md)ループに含まれている関数です。  
  
3.  指定しない、 [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)、 [/Ox](../../build/reference/ox-full-optimization.md)、または[/Og](../../build/reference/og-global-optimizations.md)コンパイル スイッチです。  
  
4.  場所、 [_alloca](../../c-runtime-library/reference/alloca.md)で機能、[実行してください-ステートメントを除く](../../cpp/try-except-statement.md)スタック オーバーフローをキャッチします。  
  
## <a name="example"></a>例  
 次のコード例はループ内で `MyFunction` を呼び出し、 `MyFunction` は `_alloca` 関数を呼び出します。 `__forceinline` 修飾子により、 `_alloca` 関数のインライン展開が発生します。  
  
```  
// c4750.cpp  
// compile with: /O2 /W1 /c  
#include <intrin.h>  
  
char * volatile newstr;  
  
__forceinline void myFunction(void) // C4750 warning  
{  
// The _alloca function does not require a __try/__except   
// block because the example uses compiler option /c.  
    newstr = (char * volatile) _alloca(1000);  
}  
  
int main(void)  
{  
    for (int i=0; i<50000; i++)  
       myFunction();  
    return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [_alloca](../../c-runtime-library/reference/alloca.md)
