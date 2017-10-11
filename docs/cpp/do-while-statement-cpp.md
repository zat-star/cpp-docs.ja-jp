---
title: "ステートメント (c++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- do_cpp
dev_langs:
- C++
helpviewer_keywords:
- do keyword [C++], do-while
- do-while keyword [C++]
- do keyword [C++]
- while keyword [C++], do-while
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 8c81bbeea9f841a834d59186017b2932f83de862
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="do-while-statement-c"></a>do-while ステートメント (C++)
実行、*ステートメント*指定した終了条件まで繰り返し (、*式*) 0 に評価します。  
  
## <a name="syntax"></a>構文  
  
```  
do  
   statement  
while ( expression ) ;  
```  
  
## <a name="remarks"></a>コメント  
 終了条件のテストは、ループの各実行の後で行われます。したがって、`do-while` ループは終了式の値に応じて 1 回以上実行されます。 `do-while`ステートメントできるときにも終了、 [break](../cpp/break-statement-cpp.md)、 [goto](../cpp/goto-statement-cpp.md)、または[返す](../cpp/return-statement-cpp.md)ステートメント本体内でステートメントを実行します。  
  
 *expression* は演算型またはポインター型であることが必要です。 次のように実行されます。  
  
1.  ステートメントの本体が実行されます。  
  
2.  次に、*expression* が評価されます。 *expression* が false の場合、`do-while` ステートメントが終了し、制御はプログラムの次のステートメントに渡されます。 *式*が true (0 以外) の場合、プロセスは手順 1 から繰り返されます。  
  
## <a name="example"></a>例  
 次のコードは、`do-while` ステートメントの使用例です。  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [while ステートメント (C++)](../cpp/while-statement-cpp.md)   
 [for ステートメント (C++)](../cpp/for-statement-cpp.md)   
 [範囲ベースの for ステートメント (C++)](../cpp/range-based-for-statement-cpp.md)
