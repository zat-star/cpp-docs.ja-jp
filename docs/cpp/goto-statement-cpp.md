---
title: "goto ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- goto_cpp
dev_langs:
- C++
helpviewer_keywords:
- goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
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
ms.openlocfilehash: 3bdad97f36902762f34816a04a4fc0c5c0c16856
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="goto-statement-c"></a>goto ステートメント (C++)
`goto` ステートメントは、指定した識別子によってラベル付けされたステートメントに制御を移します。  
  
## <a name="syntax"></a>構文  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>コメント  
 `identifier` で指定されたラベル付きステートメントは、現在の関数内にある必要があります。 すべての `identifier` 名は内部の名前空間のメンバーであるため、他の識別子と干渉することはありません。  
  
 ステートメント ラベルは `goto` ステートメントに対してのみ意味があります。その他の場合、ステートメント ラベルは無視されます。 ラベルは再宣言できません。  
  
 可能な限り、`break` ステートメントより `continue`、`return`、および `goto` ステートメントを使用することをお勧めします。 ただし、`break` ステートメントはループの 1 つのレベルのみを終了するため、深い入れ子のループを終了するには `goto` ステートメントを使用する必要がある場合もあります。  
  
 ラベルの詳細については、`goto`ステートメントを参照してください[ラベル付きステートメント](../cpp/labeled-statements.md)と[goto ステートメントを使用してラベル](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe)です。  
  
## <a name="example"></a>例  
 この例で `goto` ステートメントは、`stop` が 3 に等しい場合に、`i` というラベルの位置に制御を移します。  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>関連項目  
 [ジャンプ ステートメント](../cpp/jump-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)
