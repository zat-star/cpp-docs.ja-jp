---
title: "反復子のデバッグのサポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "debug 反復子のサポート"
  - "互換性のない反復子"
  - "反復子, debug 反復子のサポート"
  - "反復子, 互換性のない"
  - "安全なライブラリ"
  - "安全なライブラリ, 標準 C++ ライブラリ"
  - "安全な標準 C++ ライブラリ"
  - "標準 C++ ライブラリ, debug 反復子のサポート"
ms.assetid: f3f5bd15-4be8-4d64-a4d0-8bc0761c68b6
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# 反復子のデバッグのサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ ランタイム ライブラリで実行時に不正な反復子の使用を検出し、ダイアログ ボックスをアサートされ、表示されます。  デバッグ反復子サポートを有効にするには、プログラムをコンパイルするために. C ランタイム ライブラリのデバッグ バージョンを使用する必要があります。  詳細については、「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  反復子を使用する方法の詳細については、「[チェックを行う反復子](../standard-library/checked-iterators.md)」を参照してください。  
  
 C\+\+ 標準では、メンバー関数によってどのようにコンテナーに反復子が無効になる可能性について説明します。  2 個の例:  
  
-   コンテナー オフにより反復子はから要素に無効になります。  
  
-   [vector](../standard-library/vector.md) のサイズを大きくすると、`vector` \(プッシュまたは挿入\) を反復子が無効になります。  
  
## 使用例  
 デバッグ モードで次のプログラムをコンパイルすると、実行時にアサートし、終了します。  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
  
```  
  
## 使用例  
 デバッグ ビルドの反復子のデバッグ機能を無効に [\_HAS\_ITERATOR\_DEBUGGING](../Topic/_HAS_ITERATOR_DEBUGGING.md) 記号を使用できます。  次のプログラムは、アサートされませんが、トリガーは動作が定義されていません。  
  
> [!IMPORTANT]
>  `_HAS_ITERATOR_DEBUGGING`を制御するために `_ITERATOR_DEBUG_LEVEL` を使用します。  詳細については、「[\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)」を参照してください。  
  
```cpp  
// iterator_debugging.cpp  
// compile with: /EHsc /MDd  
#define _HAS_ITERATOR_DEBUGGING 0  
#include <vector>  
#include <iostream>  
  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   std::vector<int>::iterator i = v.begin();  
   ++i;  
  
   std::vector<int>::iterator j = v.end();  
   --j;  
  
   std::cout<<*j<<'\n';  
  
   v.insert(i,25);   
  
   std::cout<<*j<<'\n'; // Using an old iterator after an insert  
}  
```  
  
  **20**  
**\-572662307**   
## 使用例  
 アサートは、初期化される前に次のように反復子を使用しようとした場合にも発生する:  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <string>  
using namespace std;  
int main() {  
   string::iterator i1, i2;  
   if (i1 == i2)  
      ;  
}  
```  
  
## 使用例  
 [for\_each](../Topic/for_each.md) アルゴリズムへの 2 反復子が対応していないため、次のコード例によりアサーションが発生します。  アルゴリズムは、指定された反復子が同じコンテナーを参照しているかどうかを確認します。  
  
```cpp  
/* compile with /EHsc /MDd */  
#include <algorithm>  
#include <vector>  
using namespace std;  
  
int main()  
{  
    vector<int> v1;  
    vector<int> v2;  
  
    v1.push_back(10);  
    v1.push_back(20);  
  
    v2.push_back(10);  
    v2.push_back(20);  
  
    // The next line will assert because v1 and v2 are  
    // incompatible.  
    for_each(v1.begin(), v2.end(), [] (int& elem) { elem *= 2; } );  
}  
```  
  
 この例ではファンクタの代わりにラムダ式 `[] (int& elem) { elem *= 2; }` を使用することに注意してください。  この選択は示しませんが、エラーのようなラムダ ファンクタと同じエラーが簡易関数オブジェクト タスクを実行するための非常に便利な手段なります。  ラムダ式の詳細については、「[ラムダ式](../cpp/lambda-expressions-in-cpp.md)」を参照してください。  
  
## 使用例  
 もチェックするデバッグ反復子により `for` ループ スコープが終了すると `for` ループのスコープ外であると宣言する反復子変数が発生します。  
  
```cpp  
// debug_iterator.cpp  
// compile with: /EHsc /MDd  
#include <vector>  
#include <iostream>  
int main() {  
   std::vector<int> v ;  
  
   v.push_back(10);  
   v.push_back(15);  
   v.push_back(20);  
  
   for (std::vector<int>::iterator i = v.begin() ; i != v.end(); ++i)  
   ;  
   --i;   // C2065  
}  
```  
  
## 使用例  
 デバッグ反復子に重要なデストラクターがあります。  デストラクターが、いかなる理由であれ動作する、アクセス違反やデータ破損が発生する場合があります。  次の例について考えます。  
  
```cpp  
/* compile with: /EHsc /MDd */  
#include <vector>  
struct base {  
   // FIX: uncomment the next line  
   // virtual ~base() {}  
};  
  
struct derived : base {  
   std::vector<int>::iterator m_iter;  
   derived( std::vector<int>::iterator iter ) : m_iter( iter ) {}  
   ~derived() {}  
};  
  
int main() {  
   std::vector<int> vect( 10 );  
   base * pb = new derived( vect.begin() );  
   delete pb;  // doesn't call ~derived()  
   // access violation  
}  
```  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)