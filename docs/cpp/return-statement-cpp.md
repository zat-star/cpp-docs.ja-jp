---
title: "return ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- return
- return_cpp
dev_langs:
- C++
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 7474bc55a5c9d2406465a6ee763c19c2e56e1159
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="return-statement-c"></a>return ステートメント (C++)
関数の実行を終了し、呼び出し元の関数 (`main` 関数から制御を転送する場合はオペレーティング システム) に制御を返します。 呼び出し直後の位置から、呼び出し元の関数で実行が再開します。  
  
## <a name="syntax"></a>構文  
  
```  
return [expression];  
```  
  
## <a name="remarks"></a>コメント  
 `expression` 句は、存在する場合、初期化が実行されたときと同様に、関数宣言で指定された型に変換されます。 式の型から関数の `return` 型に変換すると、一時的なオブジェクトが作成される場合があります。 一時要素を作成する方法とタイミングの詳細については、次を参照してください。[一時オブジェクト](../cpp/temporary-objects.md)です。  
  
 `expression` 句の値が呼び出し元の関数に返されます。 expression が省略されている場合、関数の戻り値は未定義です。 コンス トラクターとデストラクター、および関数型の`void`、内の式を指定することはできません、`return`ステートメントです。 他のすべての型の関数は、`return` ステートメントで式を指定する必要があります。  
  
 制御フローが関数定義を含むブロックを終了するときの結果は、式のない `return` ステートメントが実行された場合と同じです。 これは、値を返すように宣言された関数では無効です。  
  
 関数には、`return` ステートメントを必要に応じていくつでも追加できます。  
  
 次の例は、2 つの整数値の大きい方を取得するために、`return` ステートメントを含む式を使用します。  
  
## <a name="example"></a>例  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
