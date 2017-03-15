---
title: "decltype (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "decltype"
  - "decltype_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decltype 演算子"
  - "演算子 [C++], decltype"
  - "演算子 [C++], 推測 (式の型)"
  - "演算子 [C++], 式の型"
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# decltype (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`decltype` 型指定子は、指定された式の型を生成します。  `decltype` 型指定子は、[auto キーワード](../cpp/auto-cpp.md)と共に使用され、主にテンプレート ライブラリを記述する開発者にとって有益です。  `auto` と `decltype` を使用して、テンプレートの引数の型に応じた戻り値の型を持つテンプレート関数を宣言します。  または、`auto` と `decltype` を使用して、別の関数の呼び出しをラップしたテンプレート関数を宣言し、ラップされた関数の戻り値の型を返します。  
  
## 構文  
  
```  
decltype( expression )  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`expression`|任意の式を指定します。  詳細については、「[式](../cpp/expressions-cpp.md)」を参照してください。|  
  
## 戻り値  
 `expression` パラメーターの型。  
  
## 解説  
 `decltype` 型指定子は、Visual C\+\+ 2010 以降のバージョンでサポートされ、ネイティブ コードまたはマネージ コードと共に使用できます。  `decltype(auto)` \(C\+\+14\) は Visual Studio 2015 以降でサポートされています。  
  
 コンパイラは、`expression` パラメーターの型を特定するために以下の規則を使用します。  
  
-   `expression` パラメーターが ID または[クラス メンバー アクセス](../Topic/Member%20Access%20Operators:%20.%20and%20-%3E.md)の場合、`decltype(``expression``)` は `expression` で名前が設定されたエンティティの型になります。  このようなエンティティまたは `expression` パラメーター名で一連のオーバーロードされた関数に名前を付けると、コンパイラでエラー メッセージが生成されます。  
  
-   `expression` パラメーターが関数またはオーバーロードされた演算子関数への呼び出しの場合、`decltype(``expression``)` は関数の戻り値の型です。  オーバーロードされた演算子を囲んでいるかっこは無視されます。  
  
-   `expression` パラメーターが [rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) の場合、`decltype(``expression``)` は `expression` の型になります。  `expression` パラメーターが[左辺値](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)の場合、`decltype(``expression``)` は [lvalue 参照](../Topic/Lvalue%20Reference%20Declarator:%20&.md) の型へ `expression`になります。  
  
 `decltype` 型指定子のいくつかの使用方法を次のコード例に示します。  最初に次のステートメントを記述したとします。  
  
```  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 次に、次の表の 4 つの `decltype` ステートメントによって返される型をチェックします。  
  
|ステートメント|型|メモ|  
|-------------|-------|--------|  
|`decltype(fx());`|`const int&&`|[rvalue 参照](../cpp/rvalue-reference-declarator-amp-amp.md) への `const int`。|  
|`decltype(var);`|`int`|変数 `var` の型。|  
|`decltype(a->x);`|`double`|メンバー アクセスの型。|  
|`decltype((a->x));`|`const double&`|内側のかっこは、ステートメントをメンバー アクセスではなく式として評価します。  そして、`a` は `const` ポインターとして宣言されているため、型は `const double` への参照です。|  
  
## decltype および auto  
 C\+\+14 では、後続の戻り値の型がない  `decltype(auto)` を使用して、テンプレートの引数の型に応じて戻り値の型が異なるテンプレート関数を宣言できます。  
  
 C\+\+11 では、テンプレートの引数の型に応じて戻り値の型が異なるテンプレート関数を宣言するために、`auto` キーワードとともに、後続の戻り値の型に `decltype` 型指定子を使用できます。  たとえば、テンプレート関数の戻り値の型がテンプレート引数の型に依存している次のコード例について考えます。  コード例では、*UNKNOWN* プレースホルダーが、戻り値の型を指定できないことを示しています。  
  
```  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 `decltype` 型指定子を導入することで、開発者はテンプレート関数が返す式の型を取得できます。  *late\-specified* 戻り型を宣言するには、後述する`auto`代替関数宣言構文、`decltype` キーワード、および  *型指定子を使用します。* 遅延指定された戻り値の型は、宣言がコード化されたときではなく、コンパイルされたときに決定します。  
  
 次のプロトタイプは代替関数宣言の構文について説明します。  `const` 修飾子と `volatile` 修飾子、および `throw` [例外指定](../cpp/exception-specifications-throw-cpp.md)は省略可能であることに注意してください。  *function\_body* プレースホルダーは、関数が何を行うかを指定する複合ステートメントを表します。  コーディングのベスト プラクティスとして、`decltype` ステートメントの *expresiion* プレースホルダーは、*function\_body* で `return` ステートメントによって指定された式に一致する必要があります。  
  
 `auto` *function\_name*`(`*parameters*opt`)` `const`opt `volatile`opt `−>` `decltype(`*expression*`)` `throw`opt `{`*function\_body*`};`  
  
 次のコード例では、`myFunc` テンプレート関数の遅延指定された戻り値の型は、テンプレート引数 `t` と `u` の型によって決まります。  コーディングの推奨手順として、コード例では、右辺値の参照と`forward`完全転送をサポートする  *関数テンプレートも使用しています。* 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
```  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## Decltype および転送関数 \(C\+\+11\)  
 転送関数は、他の関数の呼び出しをラップします。  関数テンプレートで、引数、またはそれらの引数を含む式の結果を別の関数に転送する場合を考えます。  さらに、転送関数は、他の関数を呼び出した結果を返します。  このシナリオでは、転送関数の戻り値の型は、ラップされた関数の戻り値の型と同じである必要があります。  
  
 このシナリオでは、`decltype` 型指定子がないと、適切な型式を記述できません。  `decltype` 型指定子は、関数が参照型を返すかどうかに関する必須情報を失わないという理由で、ジェネリック転送関数を有効にします。  転送関数のコード例については、前の `myFunc` テンプレート関数の例を参照してください。  
  
## 使用例  
 次のコード例は、テンプレート関数 `Plus()` の遅延指定の戻り値の型を宣言します。  `Plus` の関数は `operator+` オーバーロードを持つ 2 つのオペランドを処理します。  その結果、プラス演算子 \(\+\) と `Plus` 関数の戻り値の型の解釈は、関数の引数の型によって異なります。  
  
```  
// decltype_1.cpp  
// compile with: /EHsc  
//  
#include "stdafx.h"  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
 **出力**  
  
 このコード例は次の結果を生成します。  
  
 13  
  
 13.5  
  
 Hello, world\!  
  
 42  
  
## 必要条件  
 Visual C\+\+ 2010 以降のバージョン。  
  
 decltype\(auto\) には Visual Studio 2015 以降が必要です  
  
## 参照  
 [\(NOTINBUILD\)Simple Type Names](http://msdn.microsoft.com/ja-jp/333f45cb-2c72-4d81-8e59-e346b05f55e3)