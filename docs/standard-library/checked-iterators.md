---
title: "チェックを行う反復子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SECURE_SCL"
  - "_SECURE_SCL_THROWS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "checked 反復子"
  - "反復子, checked"
  - "安全なライブラリ"
  - "安全なライブラリ, 標準 C++ ライブラリ"
  - "安全な標準 C++ ライブラリ"
ms.assetid: cfc87df8-e3d9-403b-ab78-e9483247d940
caps.latest.revision: 30
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チェックを行う反復子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

チェックを行う反復子は、コンテナーの境界が上書きされないようにします。  
  
 チェックを行う反復子は、リリース ビルドおよびデバッグ ビルドに適用されます。  デバッグ モードでのコンパイル時に反復子を使用する方法の詳細については、「[反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)」を参照してください。  
  
## 解説  
 チェックを行う反復子によって生成される警告を無効にする方法の詳細については、「[\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)」を参照してください。  
  
 チェックを行う反復子機能では、次のシンボルを使用できます。  
  
 `_SECURE_SCL`  
 `_SECURE_SCL` が 1 と定義されている場合、反復子の安全でない使用によってランタイム エラーが発生し、プログラムが終了します。  0 と定義されている場合、チェックを行う反復子は無効になります。  既定では、`_SECURE_SCL` の値は、リリース ビルドの場合は 0、デバッグ ビルドの場合は 1 です。  
  
> [!IMPORTANT]
>  [\_SECURE\_SCL](../standard-library/secure-scl.md) を制御するには、`_ITERATOR_DEBUG_LEVEL` を使用します。  詳細については、「[\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
 `_SECURE_SCL` が 1 と定義されている場合、次の SCL のチェックが実行されます。  
  
-   すべての標準反復子 \(たとえば、[vector::iterator](../Topic/vector::iterator.md)\) がチェックされます。  
  
-   出力反復子がチェックを行う反復子の場合、標準関数の呼び出し \(たとえば、[std::copy](../Topic/copy.md)\) の動作がチェックされます。  
  
-   出力反復子がチェックを行わない反復子である場合、標準関数の呼び出しによってコンパイラの警告が表示されます。  
  
-   次の関数は、コンテナーの境界の外側へのアクセスがある場合は、ランタイム エラーを生成します。  
  
|||||  
|-|-|-|-|  
|[basic\_string::operator](../Topic/basic_string::operator.md)|[bitset::operator](../Topic/bitset::operator.md)|[deque::back](../Topic/deque::back.md)|[deque::front](../Topic/deque::front.md)|  
|[deque::operator](../Topic/deque::operator.md)|[list::back](../Topic/list::back.md)|[list::front](../Topic/list::front.md)|[queue::back](../Topic/queue::back.md)|  
|[queue::front](../Topic/queue::front.md)|[vector::operator](../Topic/vector::operator.md)|[vector::back](../Topic/vector::back.md)|[vector::front](../Topic/vector::front.md)|  
  
 `_SECURE_SCL` 0 と定義されている場合、  
  
-   すべての標準反復子はチェックされません \(反復子はコンテナーの境界を越えて移動でき、未定義の動作につながります\)。  
  
-   出力反復子がチェックを行う反復子の場合、標準関数の呼び出し \(たとえば、`std::copy`\) の動作がチェックされます。  
  
-   出力反復子がチェックを行わない反復子の場合、標準関数の呼び出し \(たとえば、`std::copy`\) の動作はチェックされません。  
  
 コンテナーの境界を越えて移動しようとすると、チェックを行う反復子は、`invalid_parameter_handler` を呼び出す反復子を参照します。  `invalid_parameter_handler` の詳細については、「[パラメーターの検証](../c-runtime-library/parameter-validation.md)」を参照してください。  
  
 [checked\_array\_iterator クラス](../standard-library/checked-array-iterator-class.md)と [unchecked\_array\_iterator クラス](../standard-library/unchecked-array-iterator-class.md)は、チェックを行う反復子をサポートする反復子アダプターです。  
  
## 使用例  
 `_SECURE_SCL 1` を使用してコンパイルする場合、特定のクラスのインデックス演算子を使用して、コンテナーの境界の外側にある要素にアクセスしようとすると、ランタイム エラーが発生します。  
  
```cpp  
// checked_iterators_1.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
    v.push_back(67);  
  
    int i = v[0];  
    cout << i << endl;  
  
    i = v[1]; // triggers invalid parameter handler  
};  
  
```  
  
 このプログラムは "67" を出力し、次にエラーに関する追加情報を含むアサーション エラー ダイアログ ボックスを表示します。  
  
## 使用例  
 同様に、`_SECURE_SCL 1` を使用してコンパイルする場合、コンテナーが空であるときに、特定のクラスの前後を使用して要素にアクセスしようとすると、ランタイム エラーが発生します。  
  
```cpp  
// checked_iterators_2.cpp  
// cl.exe /Zi /MDd /EHsc /W4  
  
#define _ITERATOR_DEBUG_LEVEL 1  
// implies #define _SECURE_SCL 1  
  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
int main()   
{  
    vector<int> v;  
  
    int& i = v.front(); // triggers invalid parameter handler  
};  
  
```  
  
 このプログラムは、エラーに関する追加情報を含むアサーション エラー ダイアログ ボックスを表示します。  
  
 次のコードは、さまざまな反復子のユース ケースのシナリオを示しており、それぞれにコメントが付けられています。  
  
```cpp  
// cl.exe /MTd /EHsc /W4  
#include <algorithm>  
#include <array>  
#include <iostream>  
#include <iterator>  
#include <numeric>  
#include <string>  
#include <vector>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v(16);  
    iota(v.begin(), v.end(), 0);  
    print("v: ", v);  
  
    // OK: vector::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    vector<int> v2(16);  
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });  
    print("v2: ", v2);  
  
    // OK: back_insert_iterator is marked as checked in debug mode  
    // (i.e. an overrun is impossible)  
    vector<int> v3;  
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });  
    print("v3: ", v3);  
  
    // OK: array::iterator is checked in debug mode  
    // (i.e. an overrun will trigger a debug assertion)  
    array<int, 16> a4;  
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });  
    print("a4: ", a4);  
  
    // OK: Raw arrays are checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    // NOTE: This applies only when raw arrays are given to STL algorithms!  
    int a5[16];  
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });  
    print("a5: ", a5);  
  
    // WARNING C4996: Pointers cannot be checked in debug mode  
    // (an overrun will trigger undefined behavior)  
    int a6[16];  
    int * p6 = a6;  
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });  
    print("a6: ", a6);  
  
    // OK: stdext::checked_array_iterator is checked in debug mode  
    // (an overrun will trigger a debug assertion)  
    int a7[16];  
    int * p7 = a7;  
    transform(v.begin(), v.end(), stdext::make_checked_array_iterator(p7, 16), [](int n) { return n * 7; });  
    print("a7: ", a7);  
  
    // WARNING SILENCED: stdext::unchecked_array_iterator is marked as checked in debug mode  
    // (it performs no checking, so an overrun will trigger undefined behavior)  
    int a8[16];  
    int * p8 = a8;  
    transform(v.begin(), v.end(), stdext::make_unchecked_array_iterator(p8), [](int n) { return n * 8; });  
    print("a8: ", a8);  
}  
  
```  
  
## 出力  
 前のセクションで示した `cl.exe /EHsc /W4 /MTd` のコードをコンパイルすると、次のコンパイラの警告が生成されますが、エラーなしで実行可能ファイルにコンパイルされます。  
  
```  
algorithm(1026) : warning C4996: 'std::_Transform1': Function call with parameters that may be unsafe - this call rel  
ies on the caller to check that the passed values are correct. To disable this warning, use -D_SCL_SECURE_NO_WARNINGS. See documentation on how to use Visual C++ 'Checked Iterators'  
```  
  
 コンソール アプリの実行可能ファイルを実行すると、次のように出力されます。  
  
```  
v: 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15  
v2: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30  
v3: 0 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45  
a4: 0 4 8 12 16 20 24 28 32 36 40 44 48 52 56 60  
a5: 0 5 10 15 20 25 30 35 40 45 50 55 60 65 70 75  
a6: 0 6 12 18 24 30 36 42 48 54 60 66 72 78 84 90  
a7: 0 7 14 21 28 35 42 49 56 63 70 77 84 91 98 105  
a8: 0 8 16 24 32 40 48 56 64 72 80 88 96 104 112 120  
```  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)   
 [反復子のデバッグのサポート](../standard-library/debug-iterator-support.md)