---
title: return ステートメントで、プログラムの終了 (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61d09c1b3aaea799c227686436486efa48fc7857
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="return-statement-in-program-termination-c"></a>プログラム終了時の return ステートメント (C++)
発行、`return`ステートメントから**メイン**機能的には、呼び出し元は、**終了**関数。 次に例を示します。  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **終了**と`return`前の例でのステートメントは機能的には同じです。 ただし、C++ では、`void` 以外の戻り値の型を持つ関数は、値を返す必要があります。 `return`ステートメントを使用するから値を返す**メイン**です。  
  
## <a name="see-also"></a>関連項目  
 [プログラムの終了](../cpp/program-termination.md)