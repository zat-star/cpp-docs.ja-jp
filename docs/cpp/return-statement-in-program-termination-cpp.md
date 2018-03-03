---
title: "return ステートメントで、プログラムの終了 (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a9e97c0ee52094cd3f0ccbb36c0da8b3b04c630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [プログラムの終了](../cpp/program-termination.md)