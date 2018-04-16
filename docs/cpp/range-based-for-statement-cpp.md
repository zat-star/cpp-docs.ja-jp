---
title: "範囲ベースの for ステートメント (C++) |Microsoft ドキュメント"
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
ms.assetid: 5750ba1d-ba48-4236-a923-e32de8345c2d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43ded324227878b44f997e6539e060145ad0fb66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="range-based-for-statement-c"></a>範囲ベースの for ステートメント (C++)
`statement` 内の各要素に対して `expression` を繰り返し順番に実行します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      for ( for-range-declaration : expression )  
   statement   
```  
  
## <a name="remarks"></a>コメント  
 範囲ベースを使用して`for`必要があります、「範囲」を通じて実行、すべての反復処理できるものとして定義されているループを構築するためにステートメント — たとえば、 `std::vector`、または他の C++ 標準ライブラリ シーケンスの範囲は、によって定義されます`begin()`と`end()`です。 `for-range-declaration` の部分で宣言された名前は `for` ステートメントに対してローカルであり、`expression` または `statement` で再宣言することはできません。 なお、[自動](../cpp/auto-cpp.md)キーワードをお勧め、`for-range-declaration`ステートメントの部分です。 

 **Visual Studio 2017 の新機能:**範囲ベースのループが begin() および end() が同じ型のオブジェクトを返すことが必要なくなりました。 これにより、end() が、Ranges-V3 範囲で定義されている範囲で使用されるような sentinel オブジェクトを返すことができます。 詳細については、「[Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)」 (範囲ベースの for loop の汎用化) と「[range-v3 library on GitHub](https://github.com/ericniebler/range-v3)」 (GitHub 上の range-v3 ライブラリ) を参照してください。
  
 このコードは範囲ベースを使用する方法を示します`for`ベクトルと配列を反復処理するループ。  
  
```cpp  
// range-based-for.cpp  
// compile by using: cl /EHsc /nologo /W4  
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main()   
{  
    // Basic 10-element integer array.  
    int x[10] = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };  
  
    // Range-based for loop to iterate through the array.  
    for( int y : x ) { // Access by value using a copy declared as a specific type.   
                       // Not preferred.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    // The auto keyword causes type inference to be used. Preferred.  
  
    for( auto y : x ) { // Copy of 'x', almost always undesirable  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( auto &y : x ) { // Type inference by reference.  
        // Observes and/or modifies in-place. Preferred when modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
  
    for( const auto &y : x ) { // Type inference by const reference.  
        // Observes in-place. Preferred when no modify is needed.  
        cout << y << " ";  
    }  
    cout << endl;  
    cout << "end of integer array test" << endl;  
    cout << endl;  
  
    // Create a vector object that contains 10 elements.  
    vector<double> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(i + 0.14159);  
    }  
  
    // Range-based for loop to iterate through the vector, observing in-place.  
    for( const auto &j : v ) {  
        cout << j << " ";  
    }  
    cout << endl;  
    cout << "end of vector test" << endl;  
}  
  
```  
  
 出力を次に示します。  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `1 2 3 4 5 6 7 8 9 10`  
  
 `end of integer array test`  
  
 `0.14159 1.14159 2.14159 3.14159 4.14159 5.14159 6.14159 7.14159 8.14159 9.14159`  
  
 `end of vector test`  
  
 範囲に基づく`for`ループ終了でこれらのいずれかの`statement`が実行される: [break](../cpp/break-statement-cpp.md)、[返す](../cpp/return-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md)ラベル付きステートメントの外側に、範囲ベースの**の**ループします。 A[続行](../cpp/continue-statement-cpp.md)範囲ベースのステートメント`for`ループは、現在のイテレーションのみを終了します。  
  
 範囲ベースの `for` について、以下の点に注意してください。  
  
-   自動的に配列を認識します。  
  
-   `.begin()` と `.end()` を持つコンテナーを認識します。  
  
-   それ以外については `begin()` および `end()` の引数依存の参照を使用します。  
  
## <a name="see-also"></a>参照  
 [自動](../cpp/auto-cpp.md)   
 [繰り返しステートメント](../cpp/iteration-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [while ステートメント (C++)](../cpp/while-statement-cpp.md)   
 [do-while ステートメント (C++)](../cpp/do-while-statement-cpp.md)   
 [for ステートメント (C++)](../cpp/for-statement-cpp.md)