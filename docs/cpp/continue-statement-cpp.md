---
title: continue ステートメント (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b153c9f5dfae93f1a5cb83dc2b9bcfc09e77af07
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="continue-statement-c"></a>continue ステートメント (C++)
制御の転送を強制的に外側にある最小の制御式[は](../cpp/do-while-statement-cpp.md)、[の](../cpp/for-statement-cpp.md)、または[中](../cpp/while-statement-cpp.md)ループします。  
  
## <a name="syntax"></a>構文  
  
```  
continue;  
```  
  
## <a name="remarks"></a>コメント  
 現在のイテレーションの残りのステートメントは実行されません。 ループの次のイテレーションは、次のように決定されます。  
  
-   `do` または `while` ループ内では、次のイテレーションは `do` または `while` ステートメントの制御式を再評価することによって開始されます。  
  
-   `for` ループ (構文 `for`(`init-expr`; `cond-expr`; `loop-expr`) を使用) では、`loop-expr` 句が実行されます。 次に、`cond-expr` 句が再評価され、その結果に応じて、ループが終了するか、別のイテレーションが発生します。  
  
 次の例は、`continue` ステートメントを使用してコードのセクションをバイパスし、ループの次のイテレーションを開始する方法を示しています。  
  
## <a name="example"></a>例  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
```Output  
before the continue  
before the continue  
before the continue  
after the do loop  
```  
  
## <a name="see-also"></a>関連項目  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)