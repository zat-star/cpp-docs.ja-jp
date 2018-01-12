---
title: "if-else ステートメント (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- else_cpp
- if_cpp
dev_langs: C++
helpviewer_keywords:
- if keyword [C++]
- else keyword [C++]
- if keyword [C++], if-else
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96233323e5a95f88a43fb56162393238f8c2e091
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="if-else-statement-c"></a>if-else ステートメント (C++)
条件分岐を制御します。 内のステートメント、 *if ブロック*が実行された場合にのみ、 *if 式*0 以外の値に評価される (または`true`)。 場合の値*式*がゼロ以外、 *statement1*ブロック内の他のステートメントが実行され、存在する場合、その他のブロックはスキップされます。 場合の値*式*0 の場合は、し、if ブロックはスキップされ、他のブロックが存在する場合を実行します。 0 以外に評価される式は、します。
- `true`
- null 以外のポインター
- 0 以外の算術値、または 
- 算術演算子、ブール値またはポインターへの明確な変換を定義するクラス型を入力します。 (変換については、次を参照してください[標準変換](../cpp/standard-conversions.md)。)。   
  
## <a name="syntax"></a>構文  
  
```  
  
if ( expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
} 

// Visual Studio 2017 version 15.3 and later:
if ( initialization; expression )  
{
   statement1;
   ...  
}
else  // optional
{
   statement2;
   ...
}  

// Visual Studio 2017 version 15.3 and later:
if constexpr (expression)
{
    statement1;
    ...
}
else  // optional
{
   statement2;
   ...
} 
```  
## <a name="example"></a>例  
```  
// if_else_statement.cpp  
#include <iostream>

using namespace std;

class C
{
    public:
    void do_somthing(){}
};
void init(C){}
bool is_true() { return true; }
int x = 10;

int main()
{
    if (is_true())
    {
        cout << "b is true!\n";  // executed
    }
    else
    {
        cout << "b is false!\n";
    }

  // no else statement
    if (x == 10)
    {
        x = 0; 
    }
    
  
    C* c;
  init(c);
    if (c)
    {
        c->do_something();
    }
    else
    {
        cout << "c is null!\n";
    }
}
```  
## <a name="if-statement-with-an-initializer"></a>場合、初期化子と共にステートメント
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)):**場合**ステートメントは、式を宣言し、名前付き変数が初期化される場合もあります。 変数が、if ブロックのスコープ内だけに必要なときは、この形式の if ステートメントを使用します。 

```cpp
## Example  
#include <iostream>
#include <mutex>
#include <map>
#include <string>
#include <algorithm>


using namespace std;

map<int, string> m;
mutex mx;
bool shared_flag; // guarded by mx
void unsafe_operation() {}

int main()
{

    if (auto it = m.find(10); it != m.end())
    {
        cout << it->second;
        return 0;
    }

    if (char buf[10]; fgets(buf, 10, stdin))
    {
        m[0] += buf;
    }

    if (lock_guard<mutex> lock(mx); shared_flag)
    {
        unsafe_operation();
        shared_flag = false;
    }


    string s{ "if" };
    if (auto keywords = { "if", "for", "while" }; any_of(keywords.begin(), keywords.end(), [&s](const char* kw) { return s == kw; }))
    {
        cout << "Error! Token must not be a keyword\n";
    }

}
```

 すべてのフォーム、**場合**ステートメントでは、*式*構造体以外の値であることができますが評価され、すべての副作用を含めています。 制御が渡される、**場合**プログラムに次のステートメントにステートメントしない限りのいずれか、*ステートメント*が含まれて、 [break](../cpp/break-statement-cpp.md)、 [を続行](../cpp/continue-statement-cpp.md)、または[goto](../cpp/goto-statement-cpp.md)です。  
  
 **Else**の句、`if...else`ステートメントは、最も近いに関連付けられた以前**場合**が、対応するものと同じスコープ内のステートメント**else**ステートメント。   

## <a name="constexpr-if-statements"></a>constexpr 場合ステートメント
**Visual Studio 2017 15.3 およびそれ以降のバージョン**(で利用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 関数テンプレートで使用することができます、 **constexpr 場合**コンパイル時の分岐の意思決定を行うステートメント複数の関数オーバー ロードに頼ることがなくです。 たとえば、1 つの関数を記述する、そのハンドル パラメーターの開梱 (0 パラメーター オーバー ロードは必要ありません)。 

```cpp
template <class T, class... Rest>
void f(T&& t, Rest&&... r)
{
// handle t
   do_something(t);

   // handle r conditionally
   constexpr if (sizeof...(r)) 
   {
      
      f(r...); 
   }
   else
   {
       g(r...);
   }
}
```

  
 
## <a name="see-also"></a>参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [switch ステートメント (C++)](../cpp/switch-statement-cpp.md)