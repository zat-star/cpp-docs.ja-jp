---
title: "自動 (C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
caps.latest.revision: 18
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 自動 (C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

宣言された変数の型を、その初期化式から推測します。  
  
## 構文  
  
```  
auto declarator initializer;  
```  
  
```  
[](auto param1, auto param2) {};  
```  
  
## 解説  
 `auto` キーワードは、宣言された変数の初期化式、またはラムダ式のパラメーターを使用してその型を推測するようにコンパイラに指示します。  
  
 次のような利点があるので、実際に変換が必要な場合を除き、ほとんどの状況で `auto` キーワードを使用することをお勧めします。  
  
-   **保全性:** 式の型が変更されても、関数の戻り値の型が変更された場合も含めて、機能が保たれます。  
  
-   **パフォーマンス:** 変換が行われないことが保証されます。  
  
-   **利便性:** 型名のスペルの難しさや入力ミスを気にする必要がありません。  
  
-   **効率性:** コーディングをより効率的にすることができます。  
  
 `auto` を使用するのではなく、変換を行うのは、次のような場合です。  
  
-   特定の型が必要であり、他の型を使用できない場合。  
  
-   式テンプレート ヘルパー型 \(たとえば `(valarray+valarray)` と初期化子リスト\) の場合 \(実際に `auto x = { 1 };` を取得しようとしていて、`int` のように記述することはほとんどありませんが\)。  
  
 `auto` キーワードを使用するには、変数を宣言する型の代わりに使用し、初期化式を指定します。  また、`auto`、`const`、ポインター \(`volatile`\)、参照 \(`*`\)、および右辺値参照 `&`\) などの指定子と宣言子を使用して、`(&&` キーワードを修飾できます。  コンパイラは初期化式を評価し、その情報を使用して変数の型を推測します。  
  
 初期化式は、代入 \(等号構文\)、直接の初期化 \(関数形式の構文\)、[new 演算子](../Topic/operator%20new%20\(%3Cnew%3E\).md)式にすることができます。また、[範囲ベースの for ステートメント \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md) ステートメントの  *for\-range\-declaration* パラメーターにすることもできます。  詳細については、「[初期化子](../cpp/initializers.md)」と、このドキュメントの後の方のコード例を参照してください。  
  
 `auto` キーワードは、型のプレースホルダーであり、それ自体が型ではありません。  そのため、`auto` キーワードは、[sizeof](../cpp/sizeof-operator.md) や [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) などの演算子やキャストでは使用できません。  
  
## 実用性  
 `auto` キーワードは、複雑な型を持つ変数を宣言する簡単な方法です。  たとえば、`auto` キーワードを使用して、初期化式にテンプレート、関数へのポインター、またはメンバーへのポインターが含まれる変数を宣言できます。  
  
 `auto` を使用して、ラムダ式の変数を宣言して初期化することもできます。  ラムダ式の型を認識できるのはコンパイラのみであるため、プログラマが変数の型を宣言することはできません。  詳細については、「[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)」を参照してください。  
  
## 後続の戻り値の型  
 テンプレート ライブラリの記述を支援するには、`auto` 型指定子と共に、`decltype` を使用します。  `auto` と `decltype` を使用して、テンプレートの引数の型に応じた戻り値の型を持つテンプレート関数を宣言します。  または、別の関数の呼び出しをラップするテンプレート関数を `auto` と `decltype` を使用して宣言し、その別の関数の戻り値の型を返します。  詳細については、「[decltype](../cpp/decltype-cpp.md)」を参照してください。  
  
## 参照と cv 修飾子  
 `auto` を使用すると、参照、const 修飾子、および volatile 修飾子がなくなることに注意してください。  次に例を示します。  
  
```cpp  
// cl.exe /analyze /EHsc /W4  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
    int count = 10;  
    int& countRef = count;  
    auto myAuto = countRef;  
  
    countRef = 11;  
    cout << count << " ";  
  
    myAuto = 12;  
    cout << count << endl;  
}  
  
```  
  
 myAuto は int の参照であると思うかもしれませんが、そうではありません。  これは単なる int です。そのため、出力は `11 11` です。`11 12` によって参照が解除されていなかったら、`auto` でしたが、そうなっていません。  
  
## 制限事項とエラー メッセージ  
 次の表は、`auto` キーワードの使用に関する制限事項と、それに対応してコンパイラによって生成される診断エラー メッセージの一覧です。  
  
|エラー番号|説明|  
|-----------|--------|  
|[C3530](../Topic/Compiler%20Error%20C3530.md)|`auto` キーワードを他の型指定子と組み合わせることはできません。|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|`auto` キーワードで宣言されたシンボルには初期化子が必要です。|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|`auto` キーワードを不適切に使用して型を宣言しました。  たとえば、メソッドの戻り値の型または配列を宣言しました。|  
|[C3533](../Topic/Compiler%20Error%20C3533.md)、[C3539](../Topic/Compiler%20Error%20C3539.md)|パラメーターまたはテンプレート引数は `auto` キーワードで宣言することはできません。|  
|[C3534](../Topic/Compiler%20Error%20C3534.md)|`auto` 式内の `new` キーワードで宣言されたシンボルには初期化子が必要です。  詳細については、「[new 演算子](../Topic/operator%20new%20\(%3Cnew%3E\).md)」を参照してください。|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|メソッドまたはテンプレート パラメーターは `auto` キーワードで宣言することはできません。|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|シンボルは初期化前に使用することはできません。  実際には、変数はその変数自体を初期化するために使用できないことを意味します。|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|`auto` キーワードで宣言された型にはキャストできません。|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|`auto` キーワードで宣言されている宣言子リスト内のすべてのシンボルは、同じ型に解決する必要があります。  詳細については、「[宣言](../misc/declarations.md)」を参照してください。|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md)、[C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|[sizeof](../cpp/sizeof-operator.md) と [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) 演算子は `auto` キーワードで宣言されたシンボルに適用できません。|  
  
## 使用例  
 以下のコード片は、`auto` キーワードを使用するためのいくつかの方法を示しています。  
  
 次の宣言は同等です。  最初のステートメントでは、変数 `j` は `int` 型として宣言されます。  2 番目のステートメントでは、初期化式 \(0\) が整数であるため、変数 `k` は型 `int` であると推測されます。  
  
```cpp  
  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 次の宣言は同じ意味を持ちますが、2 番目の宣言の方が最初の宣言より単純です。  `auto` キーワードを使用する最も説得力のある理由の 1 つは簡潔さです。  
  
```cpp  
  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 次のコード片は、`iter` と範囲の `elem` ループが開始されるときに、変数 `for` と `for` の型を宣言します。  
  
```cpp  
  
// cl /EHsc /nologo /W4  
#include <deque>  
using namespace std;  
  
int main()  
{  
    deque<double> dqDoubleData(10, 0.1);  
  
    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)  
    { /* ... */ }  
  
    // prefer range-for loops with the following information in mind  
    // (this applies to any range-for with auto, not just deque)  
  
    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples  
    { /* ... */ }  
  
    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE  
    { /* ... */ }  
  
    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE  
    { /* ... */ }  
}  
  
```  
  
 次のコード片は、ポインターを宣言するために、`new` 演算子とポインター宣言を使用します。  
  
```cpp  
  
double x = 12.34;  
auto *y = new auto(x), **z = new auto(&x);  
```  
  
 次のコード片は各宣言ステートメントで複数のシンボルを宣言します。  各ステートメントのすべてのシンボルが同じ型に解決されることに注意してください。  
  
```cpp  
  
auto x = 1, *y = &x, **z = &y; // Resolves to int.  
auto a(2.01), *b (&a);         // Resolves to double.  
auto c = 'a', *d(&c);          // Resolves to char.  
auto m = 1, &n = m;            // Resolves to int.  
```  
  
 次のコード片は、値が 200 の整数として変数 `?:` を宣言するために、条件演算子 \(`x`\) を使用します。  
  
```cpp  
  
int v1 = 100, v2 = 200;  
auto x = v1 > v2 ? v1 : v2;  
```  
  
 次のコード フラグメントは、変数 `x` を型 `int` に、変数 `y` を型 `const` `int` への参照に、変数 `fp` を型 `int` を返す関数へのポインターに初期化します。  
  
```cpp  
  
int f(int x) { return x; }  
int main()  
{  
    auto x = f(0);  
    const auto & y = f(1);  
    int (*p)(int x);  
    p = f;  
    auto fp = p;  
    //...  
}  
  
```  
  
## 参照  
 [auto キーワード](../cpp/auto-keyword.md)   
 [\(NOTINBUILD\)Storage\-Class Specifiers](http://msdn.microsoft.com/ja-jp/10b3d22d-cb40-450b-994b-08cf9a211b6c)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\/Zc:auto \(変数の型の推測\)](../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof 演算子](../cpp/sizeof-operator.md)   
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)   
 [new 演算子](../Topic/operator%20new%20\(%3Cnew%3E\).md)   
 [宣言](../misc/declarations.md)   
 [ラムダ式の例](../cpp/examples-of-lambda-expressions.md)   
 [初期化子](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)