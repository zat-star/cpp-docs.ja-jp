---
title: "C++ コンパイラ準拠の強化 | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a769a69a788c2c7ae1fd9854afe89d1feccf9278
ms.openlocfilehash: bc9ac2892eb9372586f101d706e744e60ebda3ce
ms.lasthandoff: 03/02/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] の C++ 準拠の強化

## <a name="new-language-features"></a>新しい言語機能  
一般化された constexpr および集計用の NSDMI をサポートし、コンパイラは、C++&14; 標準で追加されたすべての機能に対応するようになりました。 コンパイラには、C++11 標準および C++98 標準の一部の機能がないことに注意してください。

### <a name="c11"></a>C++11:
**より多くのライブラリでの SFINAE 式のサポート**Visual C コンパイラは、SFINAE 式のサポートを継続的に向上させています。これは、decltype および constexpr 式がテンプレート パラメーターとして使用されるテンプレート引数の推論と代替のために必要です。 詳細については、「[Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)」 (Visual Studio 2017 RC での SFINAE 式の機能拡張) を参照してください。 


### <a name="c-14"></a>C++ 14:
**集計用の NSDMI** 集計は、クラスの配列であり、ユーザー指定のコンストラクターがなく、プライベートまたは保護された非静的データ メンバーを持たず、基底クラスや仮想関数もありません。 C++&14; 以降、集計にメンバーの初期化子を含めることができます。 詳細については、「[Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html)」 (メンバー初期化子と集計) を参照してください。

**拡張された constexpr** constexpr として宣言された式には、特定の種類の宣言、if および switch ステートメント、loop ステートメント、constexpr 式の評価内で有効期間が開始されたオブジェクトの変異を含めることができます。 さらに、constexpr の非静的メンバー関数を暗黙的に構築するという要件はなくなりました。 詳細については、「[Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)」 (constexpr 関数に対する制約の緩和) を参照してください。 

### <a name="c17"></a>C++17:
**簡潔な static_assert** (/std:c++latest で利用可能) C++17 では、static_assert のメッセージ パラメーターは省略可能です。 詳細については、「[Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)」 (static_assert, v2 の拡張) を参照してください。 

**[[fallthrough]] 属性**  (/std:c++latest で利用可能) [[fallthrough]] 属性は、フォールスルー動作を意図するコンパイラに対するヒントとして switch ステートメントのコンテキスト内で使用できます。 これにより、コンパイラがこのような場合に警告を発行することを防止できます。 詳細については、「[Wording for [[fallthrough]] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf)」 ([[fallthrough]] 属性の用語) を参照してください。 

**汎用化された範囲ベースの for loop** (コンパイラ スイッチが不要) 範囲ベースの for loop で、begin() および end() が同じ型のオブジェクトを返す必要がなくなりました。 これにより、end() が、Ranges-V3 範囲で定義されている範囲で使用されるような sentinel オブジェクトを返すことができます。 詳細については、「[Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)」 (範囲ベースの for loop の汎用化) と「[range-v3 library on GitHub](https://github.com/ericniebler/range-v3)」 (GitHub 上の range-v3 ライブラリ) を参照してください。 


Visual Studio 2015 更新プログラム 3 での準拠の機能強化の完全な一覧については、「[Visual C++ What's New 2003 through 2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx)」 (Visual C++ 2003 から 2015 の新機能) を参照してください。

## <a name="bug-fixes"></a>バグ修正
### <a name="copy-list-initialization"></a>Copy-list-initialization
Visual Studio 2017 は、初期化子リストを使用したオブジェクト作成に関連するコンパイラ エラーを正しく発生させます。このエラーは、Visual Studio 2015 でキャッチされず、そのためにクラッシュや未定義の実行時の動作の原因になることがありました。  N4594 13.3.1.7p1 のとおり、copy-list-initialization で、コンパイラは、オーバーロードの解決のために明示的なコンストラクターを考慮する必要がありますが、そのオーバーロードが実際に選択された場合にエラーを発生させる必要があります。 

次の 2 つの例は、Visual Studio 2017 ではなく Visual Studio 2015 でコンパイルします。
```cpp  
struct A
{
    explicit A(int) {} 
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```
このエラーを修正するには、直接の初期化を使用します。
```cpp  
A a1{ 1 };
const A& a2{ 1 };
```

Visual Studio 2015 では、コンパイラは、誤って copy-list-initialization を通常の copy-initialization と同じ方法で処理しました。これは、単なるオーバーロードの解決のためのコンストラクターの変換と見なされます。 次の例では、Visual Studio 2015 は、MyInt(23) を選択しましたが、Visual Studio 2017 は正しくエラーを発生させます。 

```cpp  
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

この例は、前に似ていますが、別のエラーを発生させます。 Visual Studio 2015 では成功し、Visual Studio 2017 と C2668 では失敗します。 

```cpp  
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>非推奨の typedef
Visual Studio 2017 は、クラスまたは構造体で宣言されている非推奨の typedef に関する正しい警告を発行するようになりました。 次の例では、Visual Studio 2015 では警告なしでコンパイルしますが、Visual Studio 2017 は C4996 を生成します。

```cpp  
struct A 
{
    // also for __declspec(deprecated) 
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr
Visual Studio 2017 では、条件付きで評価の演算の左のオペランドが constexpr コンテキストで無効である場合、正しくエラーが発生します。 次のコードは、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではコンパイルされません。

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // error starting in Visual Studio 2017
}
```
エラーを修正するには、 array::size() 関数を constexpr として宣言するか、f から constexpr 修飾子を削除します。 

### <a name="class-types-passed-to-variadic-functions"></a>可変個引数関数に渡されるクラス型
Visual Studio 2017 では、printf などの可変個引数関数に渡されるクラスまたは構造体は普通にコピー可能である必要があります。 このようなオブジェクトを渡すときには、コンパイラは単にビットごとのコピーを作成し、コンストラクターまたはデストラクターを呼び出しません。 

```cpp  
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function
                        // note: the constructor and destructor will not be called; 
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```
エラーを解決するために、普通にコピー可能な型を返すメンバー関数を呼び出すことができます。 

```cpp  
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```
または、オブジェクトを渡す前にオブジェクトを変換するための静的キャストを実行します。
```cpp  
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```
CStringW を使用して構築および管理される文字列の場合、指定されている ‘operator LPCWSTR()’ を使用して、書式設定文字列によって予期されている C ポインターに CStringW オブジェクトをキャストする必要があります。

```cpp  
CStringW str1;
CStringW str2;
str1.Format(… , static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>クラス コンストラクションの cv 修飾子
Visual Studio 2015 では、コンストラクターを呼び出してクラス オブジェクトを生成するときに、コンパイラが誤って cv 修飾子を無視することがあります。 これにより、クラッシュまたは予期しない実行時動作が発生する可能性があります。 次の例は、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではコンパイラ エラーが発生します。

```cpp  
struct S 
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```
エラーを解決するには、operator int() を定数として宣言します。 

### <a name="access-checking-on-qualified-names-in-templates"></a>テンプレートの修飾名のアクセス確認
以前のバージョンのコンパイラでは、一部のテンプレートのコンテキストで修飾名のアクセス確認が実行されませんでした。 これは、名前にアクセスできないために置換が失敗すると予想される場合に、予期される SFINAE の動作に干渉する可能性があります。 コンパイラが演算子の誤ったオーバーロードを誤って呼び出すために、これが原因でクラッシュまたは実行時に予期しない動作が発生する可能性があります。 Visual Studio 2017 年では、コンパイラ エラーが発生します。 特定のエラーは異なる場合がありますが、通常は、"C2672: 一致するオーバーロードされた関数が見つかりませんでした。" が表示されます。 次のコードは、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではエラーが発生します。

```cpp  
#include <type_traits>

template <class T> class S {
       typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
       f(10); // C2672: No matching overloaded function found. 
}
```

### <a name="missing-template-argument-lists"></a>見つからないテンプレート引数リスト
Visual Studio 2015 以前では、テンプレートがテンプレート パラメーター リストに (たとえば、既定のテンプレート引数または非型テンプレート パラメーターの一部として) 表示されるときに、見つからないテンプレート引数リストを診断しませんでした これにより、コンパイラのクラッシュや実行時の予期しない動作などの予期しない動作が発生する可能性があります。 次のコードは、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではエラーが発生します。

```cpp  
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;  
```

### <a name="expression-sfinae"></a>SFINAE 式
SFINAE 式をサポートするために、コンパイラは、テンプレートがインスタンス化されるときではなく宣言されるときに、decltype 引数を解析するようになりました。 その結果、decltype 引数に非依存の特殊化が見つかった場合、インスタンス化時まで遅延されずにすぐに処理され、結果として発生したエラーは、その時点で診断されます。  

次の例は、宣言時に発生するこのようなコンパイラ エラーを示しています。

```cpp  
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
       struct BadType {};
       template <class U>
       static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
       template <class U>
       static BadType Test(...);
       static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="default-initializers-for-value-class-members-ccli"></a>値クラス メンバー (C++/CLI) の既定の初期化子
Visual Studio 2015 以前では、コンパイラは、値クラスのメンバーの既定のメンバーの初期化子を許可しました (ただし無視しました)。  値クラスの既定の初期化子は、常にメンバーを&0; に初期化します。既定のコンストラクターは許可されません。  Visual Studio 2017 年では、この例に示すように、既定メンバー初期化子は、コンパイラ エラーを発生させます。

```cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>既定のインデクサー (C++/CLI)
Visual Studio 2015 以前では、場合によっては、コンパイラは、既定のプロパティを誤って既定のインデクサーとして識別します。 識別子 "default" を使用してプロパティにアクセスすることで、この問題を回避できました。 C++11 で default がキーワードとして導入された後は、この回避策自体が問題になりました。 そのため、Visual Studio 2017 では、この回避策を必要とするバグが修正され、クラスの既定のプロパティにアクセスするために "default" が使用された場合は、コンパイラがエラーを発生させるようになりました。

```cpp  
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

 
// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

Visual Studio 2017 年では、名前を指定して両方の Value プロパティにアクセスできます。

```cpp  
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="see-also"></a>関連項目  
[Visual C と C++ 言語への準拠](c-cpp-language-conformance.md)  

