---
title: "C++ でのラムダ式 | Microsoft Docs"
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
helpviewer_keywords: 
  - "ラムダ式 [C++]"
  - "ラムダ式 [C++], 概要"
  - "ラムダ式 [C++], vs. function オブジェクト"
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: 36
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ でのラムダ式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 11 では、ラムダ式 \(*ラムダ* と呼ばれることがよくあります\) は、匿名の関数オブジェクトが呼び出されたり、引数として関数に渡されたりする場所でこのオブジェクトを定義する便利な方法です。  一般に、ラムダは、アルゴリズムまたは非同期のメソッドに渡される数行のコードをカプセル化するために使用されます。  ここでは、ラムダとはどのようなものかを定義して他のプログラミング手法と比較した上で、その利点を説明し、基本的な例を示します。  
  
## ラムダ式のパーツ  
 ISO C\+\+ 標準では、`std::sort()` 関数の 3 番目の引数として渡される単純なラムダを示しています。  
  
```cpp  
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
  
```  
  
 次の図は、ラムダのパーツを示しています。  
  
 ![ラムダ式の構造要素](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *capture 句* \(C\+\+ の仕様では *lambda\-introducer* としても知られています。\)  
  
2.  *パラメーター リスト* \(省略可能\)  \(*lambda declarator* としても知られています。\)  
  
3.  *変更可能な指定* \(省略可能\)  
  
4.  *例外仕様* \(省略可能\)  
  
5.  *後続の戻り値の型* \(省略可能\)  
  
6.  *ラムダ式の本体*  
  
### capture 句  
 ラムダは、本体に新しい変数を導入できます \(**C\+\+ 14**\)。また、周辺のスコープから変数にアクセス \(または変数を*キャプチャ*\) することができます。  ラムダは capture 句 \(標準構文では *lambda\-introducer*\) から開始します。ここで、どの変数をキャプチャするか、およびキャプチャを値によって、または参照によって行うかどうかについて指定します。  アンパサンド \(`&`\) プレフィックス付きの変数は参照でアクセスされ、アンパサンド プレフィックスなしの変数は値でアクセスされます。  
  
 空のキャプチャ句 `[ ]` は、ラムダ式の本体が外側のスコープ内の変数にアクセスしないことを示します。  
  
 ラムダで参照される任意の外部の変数をキャプチャする方法を示すには、既定のキャプチャ モード \(標準構文では `capture-default`\) を使用します。\[&\] は参照するすべての変数が参照によってキャプチャされることを意味し、\[\=\] は値によってキャプチャされることを意味します。  既定のキャプチャ モードを使用してから、特定の変数には明示的に反対のモードを指定することができます。  たとえば、ラムダ式の本体が参照によって外部変数 `total` にアクセスし、値によって外部変数 `factor` にアクセスする場合、次の capture 句は同じ結果になります。  
  
```cpp  
  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 `capture-default` を使用する場合、ラムダで記述されている変数のみがキャプチャされます。  
  
 capture 句に `capture-default` `&` が含まれている場合、その capture 句の `identifier` に含まれるいずれの `capture` も `& identifier` 形式にすることはできません。  同様に、capture 句に `capture-default` `=` が含まれている場合、その capture 句のいずれの `capture` も `= identifier` 形式にすることはできません。  識別子または `this` を capture 句で複数回使用することはできません。  次のコードでは、そのいくつかの例を示しています。  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};    // OK  
    [&, &i]{};   // ERROR: i preceded by & when & is the default  
    [=, this]{}; // ERROR: this when = is the default  
    [i, i]{};    // ERROR: i repeated  
}  
```  
  
 次の`capture`可変個引数テンプレートの例に示しているように、[の後ろに省略記号を付けると、パックの展開を意味します。](../cpp/ellipses-and-variadic-templates.md)  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 クラスのメソッドの本体でラムダ式を使用するには、`this` ポインターを capture 句に渡して、メソッドと外側のクラスのデータ メンバーにアクセスできるようにします。  クラス メソッドでラムダ式を使用する方法の例については、「[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)」にある「例: メソッドでのラムダ式の使用」を参照してください。  
  
 capture 句を使用するとき、特にマルチスレッドでラムダを使用するときは、次の重要点に注意することをお勧めします。  
  
-   参照キャプチャは外部の変数を変更するために使用できますが、値キャプチャはその目的には使用できません   \(`mutable` ではそのコピーを変更できても元の変数は変更できません\)。  
  
-   参照キャプチャでは更新が外部の変数に反映されますが、値キャプチャでは反映されません。  
  
-   参照キャプチャは有効期間に依存しますが、値キャプチャは依存しません。  これは、ラムダを非同期的に実行する場合は特に重要です。  非同期のラムダで参照によってローカルをキャプチャする場合は、そのローカルは非常に高い可能性でラムダが実行するまでになくなり、結果として実行時にアクセス違反となります。  
  
 **汎用化されたキャプチャ \(C\+\+ 14\)**  
  
 C\+\+ 14 では、capture 句にある新しい変数がラムダ関数の外側のスコープに存在する必要なしに、この変数を導入し、初期化することができます。  初期化は、任意の式として表現できます。新しい変数の型は、式によって生成される型から推測されます。  この機能の利点の 1 つは、C\+\+ 14 では移動のみの変数 \(std::unique\_ptr\) を周辺のスコープからキャプチャして、ラムダで使用できることです。  
  
```  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### パラメーター リスト  
 変数をキャプチャするだけでなく、ラムダは入力パラメーターを受け入れることができます。  パラメーター リスト \(標準構文では *lambda declarator*\) は省略可能で、ほとんどの面で関数のパラメーター リストと似ています。  
  
```  
int y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 **C\+\+ 14** では、パラメーターの型がジェネリックの場合、型指定子として auto キーワードを使用できます。  これにより、コンパイラにテンプレートとして関数呼び出し演算子を作成するように指示します。  パラメーター リストの auto の各インスタンスは、別個の型パラメーターと同等です。  
  
```  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 ラムダ式は、引数として別のラムダ式を受け取ることができます。  詳細については、トピック「[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)」の「上位ラムダ式」を参照してください。  
  
 パラメーター リストはオプションなので、ラムダ式に引数を渡さず、`lambda-declarator:` に *exception\-specification*、*trailing\-return\-type*、または `mutable` を含めない場合、空のかっこを省略できます。  
  
### 変更可能な指定  
 通常、ラムダの関数呼び出し演算子は const 値ですが、`mutable` キーワードを使用することで無効になります。  これによりデータ メンバーが変更可能になることはありません。  mutable の指定により、ラムダ式の本体で値キャプチャされる変数を変更できるようになります。  この記事の後半にあるいくつかの例で `mutable` の使用方法を示しています。  
  
### 例外の指定  
 `throw()` 例外の指定を使用して、ラムダ式が例外をスローしないことを示すことができます。  通常の関数の場合と同様、次の例に示すように、ラムダ式で [C4297](../Topic/Compiler%20Warning%20\(level%201\)%20C4297.md) 例外の指定を宣言し、ラムダの本体で例外をスローする場合、Visual C\+\+ コンパイラは警告 `throw()` を生成します。  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() throw() { throw 5; }();  
}  
```  
  
 詳細については、「[例外の仕様 \(スロー\)](../cpp/exception-specifications-throw-cpp.md)」を参照してください。  
  
### 戻り値の型  
 ラムダ式の戻り値の型は自動的に推測されます。  [trailing\-return\-type](../cpp/auto-cpp.md) を指定しなければ、*auto* キーワードを使う必要はありません。  *trailing\-return\-type* は、通常のメソッドまたは関数の戻り値の型の部分に似ています。  ただし、戻り値の型はパラメーター リストに従い、戻り値の型の前に trailing\-return\-type キーワード `->` を含める必要があります。  
  
 ラムダ式の本体に return ステートメントが 1 つだけ含まれるか、ラムダ式が値を返さない場合は、ラムダ式の return\-type 部分を省略できます。  ラムダの本体が単一の return ステートメントで構成される場合、コンパイラは return 式の型から戻り値の型を推測します。  それ以外の場合、コンパイラは戻り値の型が `void` であると推測します。  この原理を説明する次のコード例について考えてみましょう。  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
  
```  
  
 ラムダ式は、戻り値として別のラムダ式を作成できます。  詳細については、「[ラムダ式の例](../cpp/examples-of-lambda-expressions.md)」の「上位ラムダ式」を参照してください。  
  
### ラムダ式の本体  
 ラムダ式の本体 \(標準構文内の *compound\-statement*\) には、通常のメソッドや関数の本体と同じものを含めることができます。  通常の関数の本体もラムダ式の本体も次の種類の変数にアクセスできます。  
  
-   前に説明したように、外側のスコープから変数がキャプチャされました。  
  
-   パラメーター  
  
-   ローカル宣言変数  
  
-   クラスのデータ メンバー。クラス内で宣言され、`this` がキャプチャされる場合  
  
-   静的ストレージ存続期間の任意の変数 \(たとえば、グローバル変数\)  
  
 次の例には、変数 `n` を明示的に値でキャプチャし、変数 `m` を暗黙的に参照でキャプチャするラムダ式が含まれています。  
  
```cpp  
// captures_lambda_expression.cpp  
// compile with: /W4 /EHsc   
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int m = 0;  
   int n = 0;  
   [&, n] (int a) mutable { m = ++n + a; }(4);  
   cout << m << endl << n << endl;  
}  
```  
  
 **Output:**  
  
  **5**  
**0** 変数 `n` は値でキャプチャされるため、ラムダ式への呼び出しの後も値は `0` のまま残ります。  `mutable` の指定により、`n` をラムダ内で変更できるようになります。  
  
 ラムダ式は自動ストレージ存続期間がある変数のみキャプチャできますが、ラムダ式の本体では静的ストレージ存続期間がある変数を使用できます。  次の例では、`generate` 関数とラムダ式を使用して、`vector` オブジェクトの各要素に値を代入します。  ラムダ式は、静的変数を変更して次の要素の値を生成します。  
  
```cpp  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });   
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
```  
  
 詳細については、「[生成](../Topic/generate.md)」を参照してください。  
  
 次のコード例では、前の例の関数を使用し、STL アルゴリズム `generate_n` を使用するラムダ式の例を追加しています。  このラムダ式は `vector` オブジェクトの要素を前の 2 つの要素の合計に代入します。  ラムダ式が値でキャプチャする外部変数 `mutable` と `x` のコピーをラムダ式が変更できるように、`y` キーワードを使用しています。  ラムダ式は元の変数 `x` および `y` を値でキャプチャするため、それらの値はラムダの実行後も `1` のまま残ります。  
  
```cpp  
// compile with: /W4 /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });  
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
  
int main()  
{  
    // The number of elements in the vector.  
    const int elementCount = 9;  
  
    // Create a vector object with each element set to 1.  
    vector<int> v(elementCount, 1);  
  
    // These variables hold the previous two elements of the vector.  
    int x = 1;  
    int y = 1;  
  
    // Sets each element in the vector to the sum of the   
    // previous two elements.  
    generate_n(v.begin() + 2,  
        elementCount - 2,  
        [=]() mutable throw() -> int { // lambda is the 3rd parameter  
        // Generate current value.  
        int n = x + y;  
        // Update previous two values.  
        x = y;  
        y = n;  
        return n;  
    });  
    print("vector v after call to generate_n() with lambda: ", v);  
  
    // Print the local variables x and y.  
    // The values of x and y hold their initial values because   
    // they are captured by value.  
    cout << "x: " << x << " y: " << y << endl;  
  
    // Fill the vector with a sequence of numbers  
    fillVector(v);  
    print("vector v after 1st call to fillVector(): ", v);  
    // Fill the vector with the next sequence of numbers  
    fillVector(v);  
    print("vector v after 2nd call to fillVector(): ", v);  
}  
  
```  
  
 **Output:**  
  
  **vector v after call to generate\_n\(\) with lambda: 1 1 2 3 5 8 13 21 34**  
**x: 1 y: 1**  
**vector v after 1st call to fillVector\(\): 1 2 3 4 5 6 7 8 9**  
**vector v after 2nd call to fillVector\(\): 10 11 12 13 14 15 16 17 18** 詳細については、「[generate\_n](../Topic/generate_n.md)」を参照してください。  
  
## Microsoft 固有  
 ラムダは、共通言語ランタイム \(CLR\) によって管理されるエンティティである `ref class`、`ref struct`、`value class`、または `value struct` ではサポートされていません。  
  
 [\_\_declspec](../cpp/declspec.md) などの Microsoft 固有の修飾子を使用する場合、ラムダ式内の `parameter-declaration-clause` の直後に挿入できます。次に例を示します。  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
  
```  
  
 修飾子がラムダでサポートされているかどうかを判別するには、ドキュメントの「[Microsoft 固有の修飾子](../Topic/Microsoft-Specific%20Modifiers.md)」セクションを参照してください。  
  
 Visual Studio では C\+\+11 標準ラムダ式の構文と機能をサポートしています。ただし次の点は除きます。  
  
-   ラムダは、他のすべてのクラスと同様、移動コンストラクターと移動代入演算子を自動的に生成しません。  右辺値参照動作のサポートの詳細については、「[C\+\+11\/14\/17 の機能のサポート](../Topic/Support%20For%20C++11-14-17%20Features%20\(Modern%20C++\).md)」の「右辺値参照」セクションを参照してください。  
  
-   オプションの *attribute\-specifier\-seq* はこのバージョンではサポートされていません。  
  
 Visual Studio には C\+\+11 標準ラムダ機能に加えて、次の機能が含まれています。  
  
-   ステートレス ラムダ。任意の呼び出し規約に従った関数ポインターへのオムニ変換が可能です。  
  
-   ラムダ本体の自動推測される戻り値の型は、すべての return ステートメントが同じ型である限り、`{ return expression; }` よりも複雑です   \(この点は提案されている C\+\+14 標準に含まれています\)。  
  
## 参照  
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [STL 内の関数オブジェクト](../standard-library/function-objects-in-the-stl.md)   
 [関数呼び出し](../Topic/Function%20Call%20\(C++\).md)   
 [for\_each](../Topic/for_each.md)