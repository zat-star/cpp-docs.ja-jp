---
title: "constexpr (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: constexpr_cpp
dev_langs: C++
ms.assetid: c6458ccb-51c6-4a16-aa61-f69e6f4e04f7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf1094be23074fe71e65a3077de51263f01a81c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="constexpr-c"></a>constexpr (C++)
キーワード `constexpr` が C++11 で導入され、C++14 で改良されました。 意味*定数式*です。 `const` のように、コードが値を変更しようとしたときにコンパイラ エラーが生成されるように、変数にそれを適用することができます。 `const` とは異なり、`constexpr` を関数やクラスのコンストラクターに適用することもできます。 `constexpr` は値または戻り値が定数であることを示し、可能な場合はコンパイル時に計算されます。  `constexpr` 整数値は、テンプレート引数や配列の宣言など、const の整数値が必要な場所で使用できます。 実行時ではなくコンパイル時に値を計算することができる場合、に、実行速度が向上しより少ないメモリを使用して、プログラムが役立ちます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
constexpr  literal-type  identifier = constant-expression;
constexpr  literal-type  identifier { constant-expression };
constexpr literal-type identifier(params );
constexpr ctor (params);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `params`  
 リテラル型 (以下を参照) であり、それ自身が定数式でなければならない 1 つ以上のパラメーター。  
  
## <a name="return-value"></a>戻り値  
 Constexpr 変数または関数は、リテラル型のいずれかを次に示すように返す必要があります。  
  
## <a name="literal-types"></a>リテラル型  
 定数のコンパイル時の計算の複雑さと、コンパイル時の潜在的な影響を限定するために、C++14 標準では、定数式に含まれる型は、リテラル型に制限されていることが必要です。 リテラル型は、コンパイル時にレイアウトを決定できます。 リテラル型を次に示します。  
  
1.  void  
  
2.  スカラー型  
  
3.  参照  
  
4.  Void の配列、スカラー型または参照  
  
5.  自明なデストラクターを持ち、コンストラクターを移動もコピーもしない 1 つ以上の constexpr コンストラクターを持つクラス。 さらに、すべての非静的データ メンバーと基本クラスは volatile ではなくリテラル型にする必要があります。  
  
## <a name="constexpr-variables"></a>constexpr 変数  
 const 変数と constexpr 変数の主な違いとして、const 変数の初期化は実行時まで遅延できるのに対し、constexpr 変数はコンパイル時に初期化する必要があります。  すべての constexpr 変数は、const です。  

-  リテラル型を持ち、初期化されている場合、変数は `constexpr` で宣言することができます。 初期化がコンストラクターによって実行される場合、コンストラクターは `constexpr` として宣言する必要があります。  
  
-   参照するオブジェクトが定数式で初期化され、初期化中に呼び出される暗黙の変換もすべて定数式である場合には、参照を constexpr と宣言することができます。  
  
-   `constexpr` 変数または関数のすべての宣言は、`constexpr` 指定子を持っている必要があります。  
  
 
  
 
  
```cpp  
constexpr float x = 42.0;  
constexpr float y{108};  
constexpr float z = exp(5, 3);  
constexpr int i; // Error! Not initialized  
int j = 0;  
constexpr int k = j + 1; //Error! j not a constant expression  
```  
  
## <a name="constexpr-functions"></a>constexpr 関数  
 `constexpr` 関数は、使用側コードが必要とする場合に、戻り値をコンパイル時に計算できます。  引数が `constexpr` の値であり、使用側コードがコンパイル時に戻り値を必要としている場合 (たとえば、`constexpr` 変数を初期化する場合や、非型テンプレート引数を指定する場合など)、コンパイル時定数が生成されます。 非 `constexpr` 引数を使用して呼び出されたとき、または値がコンパイル時に必要でない場合には、正規関数のように、実行時に値を生成します。  (この 2 重の動作により、同じ関数の `constexpr` と非 `constexpr` のバージョンを記述する手間が省けます。)  
 
 `constexpr` 関数またはコンストラクターは暗黙的に `inline` です。 
 
 Constexpr 関数に、次の規則が適用されます。

- `constexpr` 関数はリテラル型のみを受け入れて返す必要があります。 

- `constexpr` 関数は再帰的にすることができます。 

- できません[仮想](../cpp/virtual-cpp.md)です。 A、外側のクラスが仮想基底クラス コンス トラクターは constexpr として定義できません。

- 本体は `= default` または `= delete` として定義できます。 

- 本文は、いいえを含めることができます`goto`ステートメントまたは try ブロックします。 

- constexpr ではないテンプレートの明示的な特殊化は `constexpr` として宣言できます。  
  
- `constexpr` テンプレートの明示的な特殊化は、`constexpr` である必要はありません。 


<!--conformance note-->
以降では、Visual Studio 2017 constexpr 関数に、次の規則が適用されます。 

- 場合を含むとスイッチ ステートメント、および範囲に基づく、while など、すべてのループ ステートメントとは可能性があります-中
    
- ローカル変数の宣言を含めることがありますが、変数の初期化する必要があります、リテラルの型にする必要があります、および静的あるいはスレッド ローカルにすることはできません。 ローカルに宣言された変数は const を指定する必要はありませんし、変更可能性があります。

- Constexpr 静的でないメンバー関数は、暗黙的に const を指定する必要はありません。

  
```cpp  
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
```  
  
> [!TIP]
>  注: Visual Studio デバッガーでは、内部にブレークポイントを挿入することで、`constexpr` 関数がコンパイル時に評価されているかどうかがわかります。 ブレークポイントにヒットすると、実行時に関数が呼び出されます。  ヒットしなければ、コンパイル時に関数が呼び出されます。  
  
 
## <a name="example"></a>例  
 次の例は `constexpr` 変数、関数、およびユーザー定義の型を示します。 なお、main() の最後のステートメントでは、コンパイル時に値が既知である必要はないため `constexpr` メンバー関数 GetValue() は実行時の呼び出しです。  
  
```  
#include <iostream>  
  
using namespace std;  
  
// Pass by value   
constexpr float exp(float x, int n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp(x * x, n / 2) :  
        exp(x * x, (n - 1) / 2) * x;  
};  
  
// Pass by reference  
constexpr float exp2(const float& x, const int& n)  
{  
    return n == 0 ? 1 :  
        n % 2 == 0 ? exp2(x * x, n / 2) :  
        exp2(x * x, (n - 1) / 2) * x;  
};  
  
// Compile time computation of array length  
template<typename T, int N>  
constexpr int length(const T(&ary)[N])   
{   
    return N;   
}   
  
// Recursive constexpr function  
constexpr int fac(int n)  
{   
    return n == 1 ? 1 : n*fac(n - 1);   
}  
  
// User-defined type  
class Foo  
{  
public:  
    constexpr explicit Foo(int i) : _i(i) {}  
    constexpr int GetValue()  
    {  
        return _i;  
    }  
private:  
    int _i;  
};  
  
int main()  
{  
    //foo is const:  
    constexpr Foo foo(5);   
    // foo = Foo(6); //Error!  
  
    //Compile time:  
    constexpr float x = exp(5, 3);   
    constexpr float y { exp(2, 5) };  
    constexpr int val = foo.GetValue();   
    constexpr int f5 = fac(5);  
    const int nums[] { 1, 2, 3, 4 };  
    const int nums2[length(nums) * 2] { 1, 2, 3, 4, 5, 6, 7, 8 };  
  
    //Run time:   
    cout << "The value of foo is " << foo.GetValue() << endl;   
  
}  
  
```  
  
## <a name="requirements"></a>必要条件  
 Visual Studio 2015  
  
## <a name="see-also"></a>参照  
 [宣言と定義](../cpp/declarations-and-definitions-cpp.md)   
 [const](../cpp/const-cpp.md)