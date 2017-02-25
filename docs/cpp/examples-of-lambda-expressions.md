---
title: "ラムダ式の例 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ラムダ式 [C++], 例"
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# ラムダ式の例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

この記事では、プログラムでラムダ式を使用する方法を示します。  ラムダ式の概要については、「[ラムダ式](../cpp/lambda-expressions-in-cpp.md)」を参照してください。  ラムダ式の構造の詳細については、「[ラムダ式の構文](../cpp/lambda-expression-syntax.md)」を参照してください。  
  
##  <a name="top"></a> この記事の内容  
 [ラムダ式の宣言](#declaringLambdaExpressions)  
  
 [ラムダ式の呼び出し](#callingLambdaExpressions)  
  
 [ラムダ式の入れ子](#nestingLambdaExpressions)  
  
 [高階ラムダ関数](#higherOrderLambdaExpressions)  
  
 [関数でのラムダ式の使用](#methodLambdaExpressions)  
  
 [テンプレートでのラムダ式の使用](#templateLambdaExpressions)  
  
 [例外処理](#ehLambdaExpressions)  
  
 [マネージ型でのラムダ式の使用 (C++/CLI)](#managedLambdaExpressions)  
  
##  <a name="declaringLambdaExpressions"></a> ラムダ式の宣言  
  
### 例 1  
 ラムダ式は型指定されているため、この例に示すように `auto` 変数または [function](../standard-library/function-class.md) オブジェクトに割り当てることもできます。  
  
### コード  
  
```cpp  
// declaring_lambda_expressions1.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
  
    using namespace std;  
  
    // Assign the lambda expression that adds two numbers to an auto variable.  
    auto f1 = [](int x, int y) { return x + y; };  
  
    cout << f1(2, 3) << endl;  
  
    // Assign the same lambda expression to a function object.  
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };  
  
    cout << f2(3, 4) << endl;  
}  
```  
  
### 出力  
  **5**  
**7**   
### コメント  
 詳細については、「[auto](../cpp/auto-cpp.md)」、「[function クラス](../standard-library/function-class.md)」、および「[関数呼び出し](../Topic/Function%20Call%20\(C++\).md)」を参照してください。  
  
 ラムダ式は関数の本体で最も頻繁に宣言されますが、変数を初期化できる場所ならどこでも宣言できます。  
  
### 例 2  
 Visual C\+\+ コンパイラは、式が呼び出されるときではなく式が宣言されるときに、ラムダ式をキャプチャされた変数にバインドします。  次の例では、ローカル変数 `i` を明示的に値でキャプチャし、ローカル変数 `j` を暗黙的に参照でキャプチャするラムダ式を示しています。  ラムダ式は `i` を値でキャプチャするため、プログラムが後で `i` を再割り当てしても式の結果に影響しません。  ただし、ラムダ式は `j` を参照でキャプチャするため、`j` の再割り当ては式の結果に影響します。  
  
### コード  
  
```cpp  
// declaring_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
  
   int i = 3;  
   int j = 5;  
  
   // The following lambda expression captures i by value and  
   // j by reference.  
   function<int (void)> f = [i, &j] { return i + j; };  
  
   // Change the values of i and j.  
   i = 22;  
   j = 44;  
  
   // Call f and print its result.  
   cout << f() << endl;  
}  
```  
  
### 出力  
  **47** \[[この記事の内容](#top)\]  
  
##  <a name="callingLambdaExpressions"></a> ラムダ式の呼び出し  
 次のコード スニペットに示しているように、ラムダ式は直接呼び出すことができます。  2 番目のスニペットでは、`find_if` などの標準テンプレート ライブラリ \(STL\) アルゴリズムに引数として渡す方法を示しています。  
  
### 例 1  
 この例は、2 つの整数値の合計を返し、引数 `5` と `4` で直接、式を呼び出すラムダ式を宣言します。  
  
### コード  
  
```cpp  
// calling_lambda_expressions1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
   int n = [] (int x, int y) { return x + y; }(5, 4);  
   cout << n << endl;  
}  
```  
  
### 出力  
  **9**   
### 例 2  
 この例は、`find_if` 関数の引数としてラムダ式を渡します。  ラムダ式は、パラメーターが偶数の場合、`true` を返します。  
  
### コード  
  
```cpp  
// calling_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <algorithm>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // Create a list of integers with a few initial elements.  
    list<int> numbers;  
    numbers.push_back(13);  
    numbers.push_back(17);  
    numbers.push_back(42);  
    numbers.push_back(46);  
    numbers.push_back(99);  
  
    // Use the find_if function and a lambda expression to find the   
    // first even number in the list.  
    const list<int>::const_iterator result =   
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });  
  
    // Print the result.  
    if (result != numbers.end()) {  
        cout << "The first even number in the list is " << *result << "." << endl;  
    } else {  
        cout << "The list contains no even numbers." << endl;  
    }  
}  
```  
  
### 出力  
  **リスト内の最初の偶数は 42 です。**   
### コメント  
 `find_if` 関数の詳細については、「[find\_if](../Topic/find_if.md)」を参照してください。  共通のアルゴリズムを実行する STL 関数の詳細については、「[\<algorithm\>](../standard-library/algorithm.md)」を参照してください。  
  
 \[[この記事の内容](#top)\]  
  
##  <a name="nestingLambdaExpressions"></a> ラムダ式の入れ子  
  
### 例  
 この例に示しているように、ラムダ式を別のラムダ式の入れ子にすることができます。  内側のラムダ式は、その引数を 2 倍し、その結果を返します。  外側のラムダ式は、引数を持つ内側のラムダ式を呼び出し、結果に 3 を追加します。  
  
### コード  
  
```cpp  
// nesting_lambda_expressions.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // The following lambda expression contains a nested lambda  
    // expression.  
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);  
  
    // Print the result.  
    cout << timestwoplusthree << endl;  
}  
  
```  
  
### 出力  
  **13**   
### コメント  
 この例では、`[](int y) { return y * 2; }` は入れ子になったラムダ式です。  
  
 \[[この記事の内容](#top)\]  
  
##  <a name="higherOrderLambdaExpressions"></a> 高階ラムダ関数  
  
### 例  
 多くのプログラミング言語は*高階関数*の概念をサポートしています。 高階関数は、引数として別のラムダ式を受け取るか、ラムダ式を返すラムダ式です。  [function](../standard-library/function-class.md) クラスを使用すると、C\+\+ ラムダ式が高階関数のように動作できるようになります。  この例は、`function` オブジェクトを返すラムダ式と、`function` オブジェクトを引数として受け取るラムダ式を示しています。  
  
### コード  
  
```cpp  
// higher_order_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
#include <functional>  
  
int main()  
{  
    using namespace std;  
  
    // The following code declares a lambda expression that returns   
    // another lambda expression that adds two numbers.   
    // The returned lambda expression captures parameter x by value.  
    auto addtwointegers = [](int x) -> function<int(int)> {   
        return [=](int y) { return x + y; };   
    };  
  
    // The following code declares a lambda expression that takes another  
    // lambda expression as its argument.  
    // The lambda expression applies the argument z to the function f  
    // and multiplies by 2.  
    auto higherorder = [](const function<int(int)>& f, int z) {   
        return f(z) * 2;   
    };  
  
    // Call the lambda expression that is bound to higherorder.   
    auto answer = higherorder(addtwointegers(7), 8);  
  
    // Print the result, which is (7+8)*2.  
    cout << answer << endl;  
}  
  
```  
  
### 出力  
  **30** \[[この記事の内容](#top)\]  
  
##  <a name="methodLambdaExpressions"></a> 関数でのラムダ式の使用  
  
### 例  
 関数の本体でラムダ式を使用できます。  ラムダ式は、外側の関数がアクセスできる任意の関数またはデータ メンバーにアクセスできます。  `this` ポインターを明示的または暗黙的にキャプチャして、外側のクラスの関数とデータ メンバーへのアクセスを提供できます。  
  
 ここで示しているように、関数内で `this` ポインターを明示的に使用できます。  
  
```cpp  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [this](int n) { cout << n * _scale << endl; });  
}  
```  
  
 `this` ポインターを暗黙的にキャプチャすることもできます。  
  
```  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [=](int n) { cout << n * _scale << endl; });  
}  
```  
  
 次の例は、スケール値をカプセル化する `Scale` クラスを示しています。  
  
```cpp  
// function_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Scale  
{  
public:  
    // The constructor.  
    explicit Scale(int scale) : _scale(scale) {}  
  
    // Prints the product of each element in a vector object   
    // and the scale value to the console.  
    void ApplyScale(const vector<int>& v) const  
    {  
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });  
    }  
  
private:  
    int _scale;  
};  
  
int main()  
{  
    vector<int> values;  
    values.push_back(1);  
    values.push_back(2);  
    values.push_back(3);  
    values.push_back(4);  
  
    // Create a Scale object that scales elements by 3 and apply  
    // it to the vector object. Does not modify the vector.  
    Scale s(3);  
    s.ApplyScale(values);  
}  
  
```  
  
### 出力  
  **3**  
**6**  
**9**  
**12**   
### コメント  
 `ApplyScale` 関数は、ラムダ式を使用してスケール値と `vector` オブジェクト内の各要素の積を出力します。  ラムダ式は、`this` メンバーにアクセスできるように `_scale` を暗黙的にキャプチャします。  
  
 \[[この記事の内容](#top)\]  
  
##  <a name="templateLambdaExpressions"></a> テンプレートでのラムダ式の使用  
  
### 例  
 ラムダ式は型指定されているため、それらを C\+\+ テンプレートで使用できます。  `negate_all` 関数および `print_all` 関数の例を次に示します。  `negate_all` 関数は、単項 `operator-` を `vector` オブジェクトの各要素に適用します。  `print_all` 関数は、`vector` オブジェクトの各要素をコンソールに出力します。  
  
### コード  
  
```cpp  
// template_lambda_expression.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
// Negates each element in the vector object. Assumes signed data type.  
template <typename T>  
void negate_all(vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });  
}  
  
// Prints to the console each element in the vector object.  
template <typename T>  
void print_all(const vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });  
}  
  
int main()  
{  
    // Create a vector of signed integers with a few elements.  
    vector<int> v;  
    v.push_back(34);  
    v.push_back(-43);  
    v.push_back(56);  
  
    print_all(v);  
    negate_all(v);  
    cout << "After negate_all():" << endl;  
    print_all(v);  
}  
  
```  
  
### 出力  
  **34**  
**\-43**  
**56**  
**After negate\_all\(\):**  
**\-34**  
**43**  
**\-56**   
### コメント  
 C\+\+ テンプレートの詳細については、「[テンプレート](../Topic/Templates%20\(C++\).md)」を参照してください。  
  
 \[[この記事の内容](#top)\]  
  
##  <a name="ehLambdaExpressions"></a> 例外処理  
  
### 例  
 ラムダ式の本体は、構造化例外処理 \(SEH: Structured Exception Handling\) および C\+\+ 例外処理の規則に従います。  発生した例外をラムダ式の本体で処理するか、または例外処理を外側のスコープに延期することができます。  この例は、`for_each` 関数とラムダ式を使用して、`vector` オブジェクトに別の vector オブジェクトの値を挿入します。  `try`\/`catch` ブロックを使用して、最初のベクターへの無効なアクセスを処理します。  
  
### コード  
  
```cpp  
// eh_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <algorithm>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // Create a vector that contains 3 elements.  
    vector<int> elements(3);  
  
    // Create another vector that contains index values.  
    vector<int> indices(3);  
    indices[0] = 0;  
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.  
    indices[2] = 2;  
  
    // Use the values from the vector of index values to   
    // fill the elements vector. This example uses a   
    // try/catch block to handle invalid access to the   
    // elements vector.  
    try  
    {  
        for_each(indices.begin(), indices.end(), [&](int index) {   
            elements.at(index) = index;   
        });  
    }  
    catch (const out_of_range& e)  
    {  
        cerr << "Caught '" << e.what() << "'." << endl;  
    };  
}  
```  
  
### 出力  
  **Caught 'invalid vector\<T\> subscript'.**   
### コメント  
 例外処理の詳細については、「[例外処理](../cpp/exception-handling-in-visual-cpp.md)」を参照してください。  
  
 \[[この記事の内容](#top)\]  
  
##  <a name="managedLambdaExpressions"></a> マネージ型でのラムダ式の使用 \(C\+\+\/CLI\)  
  
### 例  
 ラムダ式の capture 句には、マネージ型の変数を含めることができません。  ただし、ラムダ式のパラメーター リストにマネージ型の引数を渡すことができます。  この例に示しているラムダ式は、ローカル非マネージ型変数 `ch` を値でキャプチャし、<xref:System.String?displayProperty=fullName> オブジェクトをパラメーターとして受け取ります。  
  
### コード  
  
```cpp  
// managed_lambda_expression.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
    char ch = '!'; // a local unmanaged variable  
  
    // The following lambda expression captures local variables  
    // by value and takes a managed String object as its parameter.  
    [=](String ^s) {   
        Console::WriteLine(s + Convert::ToChar(ch));   
    }("Hello");  
}  
  
```  
  
### 出力  
  **Hello\!**   
### コメント  
 ラムダ式を STL\/CLR ライブラリで使用することもできます。  詳細については、「[STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)」を参照してください。  
  
> [!IMPORTANT]
>  ラムダは、共通言語ランタイム \(CLR\) によって管理されるエンティティである `ref class`、`ref struct`、`value class`、`value struct` ではサポートされていません。  
  
 \[[この記事の内容](#top)\]  
  
## 参照  
 [ラムダ式](../cpp/lambda-expressions-in-cpp.md)   
 [ラムダ式の構文](../cpp/lambda-expression-syntax.md)   
 [auto](../cpp/auto-cpp.md)   
 [function クラス](../standard-library/function-class.md)   
 [find\_if](../Topic/find_if.md)   
 [\<algorithm\>](../standard-library/algorithm.md)   
 [関数呼び出し](../Topic/Function%20Call%20\(C++\).md)   
 [テンプレート](../Topic/Templates%20\(C++\).md)   
 [例外処理](../cpp/exception-handling-in-visual-cpp.md)   
 [STL\/CLR ライブラリ](../dotnet/stl-clr-library-reference.md)