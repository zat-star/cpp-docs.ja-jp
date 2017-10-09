---
title: "C++ コンパイラ準拠の強化 | Microsoft Docs"
ms.custom: 
ms.date: 08/13/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3bd6838166a5471190e4c19c1a5f356901551dbb
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] の C++ 準拠の強化

## <a name="new-language-features"></a>新しい言語機能  
一般化された constexpr および集計用の NSDMI をサポートし、コンパイラは、C++ 14 標準で追加されたすべての機能に対応するようになりました。 コンパイラには、C++11 標準および C++98 標準の一部の機能がないことに注意してください。 コンパイラの現在の状態については、「[Visual C++ Language Conformance (Visual C++ 言語への準拠)](visual-cpp-language-conformance.md)」の表を参照してください。

### <a name="c11"></a>C++11:
**より多くのライブラリでの SFINAE 式のサポート**Visual C コンパイラは、SFINAE 式のサポートを継続的に向上させています。これは、decltype および constexpr 式がテンプレート パラメーターとして使用されるテンプレート引数の推論と代替のために必要です。 詳細については、「[Expression SFINAE improvements in Visual Studio 2017 RC](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3)」 (Visual Studio 2017 RC での SFINAE 式の機能拡張) を参照してください。 


### <a name="c-14"></a>C++ 14:
**集計用の NSDMI** 集計は、クラスの配列であり、ユーザー指定のコンストラクターがなく、プライベートまたは保護された非静的データ メンバーを持たず、基底クラスや仮想関数もありません。 C++ 14 以降、集計にメンバーの初期化子を含めることができます。 詳細については、「[Member initializers and aggregates](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html)」 (メンバー初期化子と集計) を参照してください。

**拡張された constexpr** constexpr として宣言された式には、特定の種類の宣言、if および switch ステートメント、loop ステートメント、constexpr 式の評価内で有効期間が開始されたオブジェクトの変異を含めることができます。 さらに、constexpr の非静的メンバー関数を暗黙的に構築するという要件はなくなりました。 詳細については、「[Relaxing constraints on constexpr functions](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html)」 (constexpr 関数に対する制約の緩和) を参照してください。 

### <a name="c17"></a>C++17:
**簡潔な static_assert** (/std:c++latest で利用可能) C++17 では、static_assert のメッセージ パラメーターは省略可能です。 詳細については、「[Extending static_assert, v2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf)」 (static_assert, v2 の拡張) を参照してください。 

**[[fallthrough]] 属性**  (/std:c++latest で利用可能) [[fallthrough]] 属性は、フォールスルー動作を意図するコンパイラに対するヒントとして switch ステートメントのコンテキスト内で使用できます。 これにより、コンパイラがこのような場合に警告を発行することを防止できます。 詳細については、「[Wording for [[fallthrough]] attribute](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf)」 ([[fallthrough]] 属性の用語) を参照してください。 

**汎用化された範囲ベースの for loop** (コンパイラ スイッチが不要) 範囲ベースの for loop で、begin() および end() が同じ型のオブジェクトを返す必要がなくなりました。 これにより、end() が、Ranges-V3 範囲で定義されている範囲で使用されるような sentinel オブジェクトを返すことができます。 詳細については、「[Generalizing the Range-Based For Loop](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html)」 (範囲ベースの for loop の汎用化) と「[range-v3 library on GitHub](https://github.com/ericniebler/range-v3)」 (GitHub 上の range-v3 ライブラリ) を参照してください。 

**Visual Studio 2017 バージョン 15.3**:

**constexpr ラムダ** 定数式でラムダ式を使用できるようになりました。 詳しくは、「[Constexpr Lambda (Constexpr ラムダ)](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf)」をご覧ください。

**関数テンプレートでの if constexpr** 関数テンプレートに、`if constexpr` ステートメントを含めてコンパイル時の分岐を有効にできます。 詳細については、「[if constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html)」をご覧ください。

**初期化子を含む選択ステートメント** `if`ステートメントには、ステートメント自体のブロック スコープで変数を導入する初期化子を含めることができます。 詳しくは、「[Selection statements with initializer (初期化子を持つ選択ステートメント)](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html)」をご覧ください。

**[[maybe_unused]] および [[nodiscard]] 属性** エンティティを使用しない場合に警告を発生させない、または関数呼び出しの戻り値が破棄されたら警告を発生させる、新しい属性です。 詳しくは、「[Wording for maybe_unused attribute (maybe_unused 属性の表現)](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf)」と「[Proposal of unused,nodiscard and fallthrough attributes (unused、nodiscard、fallthrough 属性の提案)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf)」をご覧ください。

**属性の名前空間の繰り返しのない使用** 1 つの属性リストで 1 つの名前空間の識別子のみを有効にする新しい構文です。 詳しくは、「[Attributes in C++ (C++ における属性)](cpp/attributes2.md)」をご覧ください。

**構造化バインド** 値が、配列、std::tuple または std::pair のいずれかである、または、すべてのパブリックの非静的データ メンバーを持つときに、1 つの宣言で、そのコンポーネントの個別の名前を持つ値を格納できるようになりました。 詳しくは、「[Structured Bindings (構造化バインド)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf)」をご覧ください。

**列挙型クラスの値の構築ルール** 定義で列挙子を導入せず、ソースがリスト初期化構文を使用している場合に、スコープ列挙の基になる型から列挙型自体への、暗黙的な/非縮小の変換が使用できるようになりました。 詳しくは、「[Construction Rules for enum class Values (列挙型クラスの値の構築ルール)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf)」をご覧ください。

***this を値でキャプチャする**  ラムダ式の "\*this" オブジェクトが値でキャプチャできるようになりました。 これにより、特に新しいコンピューター アーキテクチャで、並列で非同期の操作でラムダが呼び出されるシナリオを実現できます。 詳しくは、「[Lambda Capture of \*this by Value as [=,\*this] (*this の [=,*this] としての値によるラムダ キャプチャ)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html)」をご覧ください。

**bool** operator++ の operator++ 削除は、`bool` 型ではサポートされなくなりました。 詳しくは、「[Remove Deprecated operator++(bool) (非推奨の operator++(bool) の削除)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html)」をご覧ください。

**非推奨の "register" キーワードの削除** `register` キーワードは、以前は非推奨でしたが (Visual C++ コンパイラでは無視される)、言語から削除されました。 詳しくは、「[Remove Deprecated Use of the register Keyword (register キーワードの非推奨使用の削除)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html)」をご覧ください。

Visual Studio 2015 更新プログラム 3 での準拠の機能強化の完全な一覧については、「[Visual C++ What's New 2003 through 2015](https://msdn.microsoft.com/en-us/library/mt723604.aspx)」 (Visual C++ 2003 から 2015 の新機能) を参照してください。

## <a name="bug-fixes"></a>バグ修正
### <a name="copy-list-initialization"></a>Copy-list-initialization
Visual Studio 2017 は、初期化子リストを使用したオブジェクト作成に関連するコンパイラ エラーを正しく発生させます。このエラーは、Visual Studio 2015 でキャッチされず、そのためにクラッシュや未定義の実行時の動作の原因になることがありました。 N4594 13.3.1.7p1 のとおり、copy-list-initialization で、コンパイラは、オーバーロードの解決のために明示的なコンストラクターを考慮する必要がありますが、そのオーバーロードが実際に選択された場合にエラーを発生させる必要があります。 

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
struct MyStore {
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
Visual Studio 2017 では、条件付きで評価の演算の左のオペランドが constexpr コンテキストで無効である場合、正しくエラーが発生します。 次のコードは、Visual Studio 2015 ではコンパイルされますが、Visual Studio 2017 ではコンパイルされません (C3615 constexpr 関数 'f' の結果が定数式になることはありません)。

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // C3615    
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
CStringW を使用して構築および管理される文字列の場合、指定されている `operator LPCWSTR()` を使用して、書式設定文字列によって予期されている C ポインターに CStringW オブジェクトをキャストする必要があります。

```cpp  
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
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
### <a name="classes-declared-in-anonymous-namespaces"></a>匿名の名前空間で宣言されたクラス
C++ 標準によると、匿名の名前空間内で宣言されたクラスは内部リンケージがあるため、エクスポートすることができません。 Visual Studio 2015 以前のバージョンでは、この規則は適用されませんでした。 Visual Studio 2017 では、この規則は部分的に適用されます。 次の例は、Visual Studio 2017 で発生したエラーを表します: "エラー C2201: const anonymous namespace::S1::vftable:ブロック内に関数の宣言がありますが、extern を宣言していません。"

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>値クラス メンバー (C++/CLI) の既定の初期化子
Visual Studio 2015 以前では、コンパイラは、値クラスのメンバーの既定のメンバーの初期化子を許可しました (ただし無視しました)。 値クラスの既定の初期化子は、常にメンバーを 0 に初期化します。既定のコンストラクターは許可されません。 Visual Studio 2017 年では、この例に示すように、既定メンバー初期化子は、コンパイラ エラーを発生させます。

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

## <a name="update_153"></a>Visual Studio 2017 バージョン 15.3 でのバグ修正
### <a name="calls-to-deleted-member-templates"></a>削除されたメンバー テンプレートへの呼び出し
Visual Studio の以前のバージョンでは、実行時のクラッシュの原因になる可能性がある、削除されたメンバー テンプレートの不適切な形式の呼び出しに対して、コンパイラがエラーの生成に失敗する場合がありました。 次のコードに対しては、C2280: "'int S<int>::f<int>(void)': 削除された関数を参照しようとしています" が生成されるようになりました。
```cpp
template<typename T> 
struct S { 
   template<typename U> static int f() = delete; 
}; 
 
void g() 
{ 
   decltype(S<int>::f<int>()) i; // this should fail 
}
```
このエラーを解決するには、i を `int` として宣言します。

### <a name="pre-condition-checks-for-type-traits"></a>型の特徴に対する前提条件の確認
Visual Studio 2017 バージョン 15.3 では、型の特徴の前提条件の確認が向上し、標準にいっそう厳密に準拠するようになりました。 そのような確認の 1 つは割り当て可能に関するものです。 Update Version 15.3 では、次のコードに対して C2139 が生成されます。

```cpp
struct S; 
enum E; 
 
static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>コンパイラの新しい警告と、ネイティブからマネージへのマーシャリングの実行時チェック
マネージ関数からネイティブ関数を呼び出すには、マーシャリングが必要です。 CLR はマーシャリングを実行しますが、C++ のセマンティクスを理解していません。 ネイティブ オブジェクトを値で渡した場合、CLR はオブジェクトのコピー コンストラクターを呼び出すか、または BitBlt を使いますが、それによって実行時に未定義の動作が発生する可能性があります。 
 
今後は、削除されたコピー コンストラクターを含むネイティブ オブジェクトがネイティブとマネージの境界を越えて値で渡されることをコンパイル時に認識すると、コンパイラは警告を生成します。 コンパイル時に認識できない場合のためには、実行時チェックが挿入されて、不適切な形式のマーシャリングが発生すると直ちにプログラムが std::terminate を呼び出せるようにします。 Update Version 15.3 では、次のようなコードを実行すると、C4606 "'A': ネイティブとマネージの境界を越えて値渡しで引数を渡すには、有効なコピー コンストラクターが必要です。 それがない場合、ランタイムの動作は定義されていません" が発生します。
```cpp
class A 
{ 
public: 
   A() : p_(new int) {} 
   ~A() { delete p_; } 
 
   A(A const &) = delete; 
   A(A &&rhs) { 
   p_ = rhs.p_; 
} 
 
private: 
   int *p_; 
}; 
 
#pragma unmanaged 
 
void f(A a) 
{ 
} 
 
#pragma managed 
 
int main() 
{ 
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which will result in a double-free later. 
}
```
このエラーを解決するには、`#pragma managed` ディレクティブを削除し、呼び出し元をネイティブとしてマークして、マーシャリングを回避します。 

### <a name="experimental-api-warning-for-winrt"></a>WinRT に対する実験用 API の警告
実験とフィードバックのためにリリースされている WinRT API は、`Windows.Foundation.Metadata.ExperimentalAttribute` で修飾されます。 Visual Studio 2017 バージョン 15.3 のコンパイラは、この属性を検出すると警告 C4698 を生成します。 以前のバージョンの Windows SDK に含まれる一部の API は、この属性で既に修飾されており、これらの API を呼び出すとこのコンパイラ警告のトリガーが始まります。 新しい Windows SDK では、付属するすべての型からこの属性が削除されていますが、古い SDK を使っている場合は、付属する型のすべての呼び出しでこの警告を抑制する必要があります。
次のようなコードを実行すると、警告 C4698: "'Windows::Storage::IApplicationDataStatics2::GetForUserAsync' は、評価の目的でのみ提供されています。将来の更新で変更または削除されることがあります" が発生します。
```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() //C4698
```

警告を無効にするには、#pragma を追加します。

```cpp
#pragma warning(push) 
#pragma warning(disable:4698) 
 
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() 
 
#pragma warning(pop)
```
### <a name="out-of-line-definition-of-a-template-member-function"></a>テンプレート メンバー関数のアウトオブライン定義 
Visual Studio 2017 バージョン 15.3 では、クラスで宣言されていないテンプレート メンバー関数のアウトオブライン定義を検出すると、エラーが生成されます。 次のようなコードに対しては、エラー C2039: "'f': 'S' のメンバーではありません" が発生します。

```cpp
struct S {}; 
 
template <typename T> 
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

このエラーを解決するには、次の宣言をクラスに追加します。

```cpp
struct S { 
    template <typename T> 
    void f(T t); 
}; 
template <typename T> 
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>"this" ポインターのアドレスを取得する試み
C++ では、"this" は X へのポインター型の prvalue です。"this" のアドレスを取得すること、または左辺値参照にバインドすることはできません。 前のバージョンの Visual Studio では、キャストを実行することにより、この制限を回避できました。 Visual Studio 2017 バージョン 15.3 では、コンパイラはエラー C2664 を生成します。

### <a name="conversion-to-an-inaccessible-base-class"></a>アクセスできない基底クラスへの変換
Visual Studio 2017 バージョン 15.3 では、アクセスできない基底クラスに型を変換しようとすると、エラーになります。 コンパイラによって "エラー C2243: 'type cast': 'D *' から 'B *' の変換は存在しますが、アクセスできません" が生成されます。 次のコードは形式が不適切であり、実行時にクラッシュが発生する可能性があります。 コンパイラは、このようなコードを検出すると、C2243 を生成するようになりました。

```cpp
#include <memory> 
 
class B { }; 
class D : B { }; // C2243. should be public B { }; 
 
void f() 
{ 
   std::unique_ptr<B>(new D()); 
}
```
### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>メンバー関数のアウトオブライン定義で既定の引数が許可されない
テンプレート クラス内のメンバー関数のアウトオブライン定義では、既定の引数が許可されません。コンパイラは /permissive では警告を発し、/permissive- ではハード エラーを発します。 

Visual Studio の以前のバージョンでは、形式が間違っている次のコードでランタイム クラッシュが発生する可能性がありました。 Visual Studio 2017 バージョン 15.3 では、警告 C5034: "'A<T>::f': クラス テンプレートのメンバーのアウトオブライン定義において既定の引数を使用することはできません" が生成されます。
```cpp
 
template <typename T> 
struct A { 
    T f(T t, bool b = false); 
}; 
 
template <typename T> 
T A<T>::f(T t, bool b = false) // C5034
{ 
... 
}
```
このエラーを解決するには、既定の引数 "= false" を削除します。 

### <a name="use-of-offsetof-with-compound-member-designator"></a>複合メンバー指定子での offsetof の使用
Visual Studio 2017 バージョン 15.3 では、m が "複合メンバー指定子" である offsetof(T, m) を使用して、/Wall オプションを指定してコンパイルすると、警告が発生します。 次のコードは形式が不適切であり、実行時にクラッシュが発生する可能性があります。 Visual Studio 2017 バージョン 15.3 では、"警告 C4841: 非標準の拡張機能が使用されています:複合メンバー指定子が offsetof で使用されています" が生成されます。

```cpp
  
struct A { 
int arr[10]; 
}; 
 
// warning C4841: non-standard extension used: compound member designator in offsetof 
constexpr auto off = offsetof(A, arr[2]);
```
コードを修正するには、プラグマで警告を無効にするか、offsetof を使わないようにコードを変更します。 

```cpp
#pragma warning(push) 
#pragma warning(disable: 4841) 
constexpr auto off = offsetof(A, arr[2]); 
#pragma warning(pop) 
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>静的なデータ メンバーまたはメンバー関数での offsetof の使用
Visual Studio 2017 バージョン 15.3 では、m が静的なデータ メンバーまたはメンバー関数である offsetof(T, m) を使うと、エラーになります。 以下のコードでは、"error C4597: undefined behavior: offsetof applied to member function 'foo'" (エラー C4597: 定義されていない動作: offsetof がメンバー関数 'foo' に適用されています) および "error C4597: undefined behavior: offsetof applied to static data member 'bar'" (エラー C4597: 定義されていない動作: offsetof が静的データ メンバー 'bar' に適用されています) が発生します。
```cpp
 
#include <cstddef> 
 
struct A { 
int foo() { return 10; } 
static constexpr int bar = 0; 
}; 
 
constexpr auto off = offsetof(A, foo); 
Constexpr auto off2 = offsetof(A, bar);
```
 
このコードは形式が不適切であり、実行時にクラッシュが発生する可能性があります。 このエラーを解決するには、定義されていない動作を呼び出さないようにコードを変更します。 これは、C++ 標準で許可されていない移植性のないコードです。

### <a name="new-warning-on-declspec-attributes"></a>declspec 属性についての新しい警告
Visual Studio 2017 バージョン 15.3 では、extern "C" リンケージ指定の前に __declspec(…) を適用した場合、コンパイラは属性を無視しないようになりました。 以前のコンパイラは属性を無視し、実行時に影響する可能性がありました。 `/Wall /WX` オプションが設定されている場合、次のコードでは、"warning C4768: __declspec attributes before linkage specification are ignored" (警告 C4768: リンケージ指定の前の __declspec 属性は無視されます) が発生します。

```cpp
 
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

この警告を解決するには、extern "C" を先頭に配置します。

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```
この警告は既定ではオフになっており、`/Wall /WX` でコンパイルされたコードにのみ影響します。

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype と削除されたデストラクターの呼び出し
以前のバージョンの Visual Studio では、"decltype" と関連付けられた式での削除されたデストラクターの呼び出しを、コンパイラは検出しませんでした。 Visual Studio 2017 バージョン 15.3 では、次のようなコードでは、"エラー C2280: 'A<T>::~A(void)': 削除された関数を参照しようとしています" が発生します。

```cpp
template<typename T> 
struct A 
{ 
   ~A() = delete; 
}; 
 
template<typename T> 
auto f() -> A<T>; 
 
template<typename T> 
auto g(T) -> decltype((f<T>())); 
 
void h() 
{ 
   g(42); 
}
```
### <a name="uninitialized-const-variables"></a>初期化されていない const 変数
Visual Studio 2017 RTW リリースには、"const" 変数が初期化されていないと C++ コンパイラが診断を生成しないという回帰がありました。 この回帰は、Visual Studio 2017 バージョン 15.3 で修正されました。 次のコードでは、"警告 C4132: 'Value': const オブジェクトは初期化しなければなりません" が生成されます。

```cpp
const int Value; //C4132
```
このエラーを解決するに、`Value` に値を割り当てます。

### <a name="empty-declarations"></a>空の宣言
Visual Studio 2017 バージョン 15.3 では、組み込み型だけでなくすべての型で、空の宣言が警告されるようになりました。 次のコードでは、4 つの宣言すべてに対し、レベル 2 の警告 C4091 が生成されます。

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };
 
int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

警告を解決するには、空の宣言をコメントにするか、削除します。 名前のないオブジェクトが副作用 (RAII など) を意図したものである場合、名前を指定する必要があります。
 
警告は、/Wv:18 では除外され、警告レベル W2 では既定で有効になります。


### <a name="stdisconvertible-for-array-types"></a>配列型の std::is_convertible
以前のバージョンのコンパイラでは、配列型の [std::is_convertible](standard-library/is-convertible-class.md) で正しい結果が得られませんでした。 そのため、ライブラリの作成者は `std::is_convertible<…>` 型の特徴を使用する場合に、Visual C++ コンパイラを特例処理する必要がありました。 次の例では、静的アサートは以前のバージョンの Visual Studio では成功しますが、Visual Studio 2017 バージョン 15.3 では失敗します。

```cpp
#include <type_traits>
 
using Array = char[1];
 
static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

**std::is_convertible<From, To>** は、以下のように、虚数関数定義の形式が適切であるかどうかを確認して計算されます。
```cpp 
   To test() { return std::declval<From>(); }
``` 

### <a name="private-destructors-and-stdisconstructible"></a>プライベート デストラクターと std::is_constructible
以前のバージョンのコンパイラでは、[std::is_constructible](standard-library/is-constructible-class.md) の結果の判定時にデストラクターがプライベートかどうかは無視されていました。 ここではこれについて考えます。 次の例では、静的アサートは以前のバージョンの Visual Studio では成功しますが、Visual Studio 2017 バージョン 15.3 では失敗します。

```cpp
#include <type_traits>
 
class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};
 
// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```  

プライベート デストラクターの場合、型が構成不可となります。 **std::is_constructible<T, Args…>** は、以下の宣言が書き込まれているかのように計算されます。
```cpp 
   T obj(std::declval<Args>()…)
``` 
この呼び出しはデストラクターの呼び出しを意味します。

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: あいまいなオーバーロードの解決
以前のバージョンのコンパイラでは、宣言と引数依存の参照の両方を使用して、複数の候補が見つかったときに、あいまいさを検出できない場合がありました。 このような場合、誤ったオーバーロードが選択され、ランタイムが予期しない動作になることがあります。 次の例では、Visual Studio 2017 バージョン 15.3 で適切に "C2668 'f': オーバーロードされた関数への呼び出しがあいまいです" と示されます。

```cpp
namespace N {
   template<class T>
   void f(T&, T&);
 
   template<class T>
   void f();
}
 
template<class T>
void f(T&, T&);
 
struct S {};
void f()
{
   using N::f; 
 
   S s1, s2;
   f(s1, s2); // C2668
}
```
このコードを修正するには、::f() の呼び出しを意図していた場合は using N::f ステートメントを削除します。

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: ローカル関数宣言と引数依存の参照
ローカル関数宣言では、外側のスコープ内の関数が非表示になり、引数依存の参照が無効になります。
ただし、以前のバージョンの Visual C++ コンパイラでは引数依存の参照が実行され、誤ったオーバーロードが選択されて、ランタイムが予期しない動作になる可能性がありました。 通常、このエラーは、ローカル関数宣言のシグネチャが正しくないことが原因で発生します。 次の例では、Visual Studio 2017 バージョン 15.3 で "C2660 'f': 関数に 2 個の引数を指定できません" というエラーが正しく発生します。

```cpp
struct S {}; 
void f(S, int);
 
void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

問題を修正するには、**f(S)** シグネチャを変更するか、削除します。

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: 初期化子リストの初期化の順序
クラス メンバーは、初期化子リストに表示される順序ではなく、宣言される順序で初期化されます。 以前のバージョンのコンパイラでは、初期化子リストの順序が宣言の順序と異なる場合に警告されませんでした。 そのため、あるメンバーの初期化が、既に初期化されている、リスト内の別のメンバーに依存していた場合に、ランタイム動作が未定義になることがありました。 次の例では、Visual Studio 2017 バージョン 15.3 (/Wall を使用) は、"C5038: データ メンバー 'A::x' の後にデータ メンバー 'A::y' が初期化されます" という内容の警告を出します。

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};

```
問題を修正するには、宣言と同じ順序になるように初期化子リストを並べ替えます。 初期化子のいずれかまたは両方で基底クラス メンバーが参照される場合に同様の警告が発生します。

警告は既定ではオフになっており、/Wall でコンパイルされたコードにのみ影響することに注意してください。

## <a name="see-also"></a>関連項目  
[Visual C++ 言語への準拠](visual-cpp-language-conformance.md)  

