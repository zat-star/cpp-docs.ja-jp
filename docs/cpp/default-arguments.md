---
title: "既定の引数 |Microsoft ドキュメント"
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
- arguments [C++], function
- function declarators
- functions [C++], default arguments
- declaring functions [C++], declarators
- default arguments
- arguments [C++], default
- defaults [C++], arguments
ms.assetid: d32cf516-05cb-4d4d-b169-92f5649fdfa2
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: b14cd3b6ff1386ab2484b8a424c6ef2ceee1cd85
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="default-arguments"></a>既定の引数
多くの場合、関数には引数がありますが、ほとんど使用されることはありません。既定値で十分です。 これに対処するために、既定の引数機能では、特定の呼び出しで有効な引数だけを関数に指定できます。 この概念を示すために示されている例を検討してください。[関数のオーバー ロード](../cpp/function-overloading.md)です。  
  
```  
// Prototype three print functions.  
int print( char *s );                  // Print a string.  
int print( double dvalue );            // Print a double.  
int print( double dvalue, int prec );  // Print a double with a  
//  given precision.  
```  
  
 多くのアプリケーションでは、適切な既定値は `prec` で指定できるので、次の 2 つの関数は不要です。  
  
```  
// Prototype two print functions.  
int print( char *s );                    // Print a string.  
int print( double dvalue, int prec=2 );  // Print a double with a  
//  given precision.  
```  
  
 実装、`print`関数は型の 1 つだけこのような関数が存在するという事実を反映するように少し変更**二重**:  
  
```  
// default_arguments.cpp  
// compile with: /EHsc /c  
  
// Print a double in specified precision.  
//  Positive numbers for precision indicate how many digits  
//  precision after the decimal point to show. Negative  
//  numbers for precision indicate where to round the number  
//  to the left of the decimal point.  
  
#include <iostream>  
#include <math.h>  
using namespace std;  
  
int print( double dvalue, int prec ) {  
   // Use table-lookup for rounding/truncation.  
   static const double rgPow10[] = {   
      10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1, 10E0,  
         10E1,  10E2,  10E3,  10E4, 10E5,  10E6  
   };  
   const int iPowZero = 6;  
   // If precision out of range, just print the number.  
   if( prec >= -6 && prec <= 7 )  
      // Scale, truncate, then rescale.  
      dvalue = floor( dvalue / rgPow10[iPowZero - prec] ) *  
      rgPow10[iPowZero - prec];  
   cout << dvalue << endl;  
   return cout.good();  
}  
```  
  
 新しい `print` 関数を呼び出すには、次のようなコードを使用します:  
  
```  
print( d );    // Precision of 2 supplied by default argument.  
print( d, 0 ); // Override default argument to achieve other  
//  results.  
```  
  
 既定の引数を使用する場合は、これらのポイントに注意します。  
  
-   既定の引数は、後続の引数を省略した関数呼び出しでのみ使用されます。既定の引数は、最後の引数である必要があります。 したがって、次のコードは正しくありません。  
  
    ```  
    int print( double dvalue = 0.0, int prec );  
    ```  
  
-   既定の引数は、以降の宣言で再定義が元と同じでも再定義できません。 したがって、次のコードはエラーになります。  
  
    ```  
    // Prototype for print function.  
    int print( double dvalue, int prec = 2 );  
  
    ...  
  
    // Definition for print function.  
    int print( double dvalue, int prec = 2 )  
    {  
    ...  
    }  
    ```  
  
     このコードの問題は、定義での関数宣言が `prec` の既定の引数を定義し直すことです。  
  
-   追加の既定の引数は、後の宣言によって追加できます。  
  
-   既定の引数は、関数へのポインターに対して指定できます。 例:  
  
    ```  
    int (*pShowIntVal)( int i = 0 );  
    ```  
  
## <a name="see-also"></a>関連項目  
 
