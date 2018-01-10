---
title: "Visual C++ 2003 ～ 2015 の新機能 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c4afde6f-3d75-40bf-986f-be57e3818e26
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 512665a243a0c24c143242084a51f6b3025c1a19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="visual-c-what39s-new-2003-through-2015"></a>Visual C++ 2003 ～ 2015 の新機能

**注:** Visual Studio 2017 の詳細については、「[What's new for Visual C++ in Visual Studio 2017](../what-s-new-for-visual-cpp-in-visual-studio.md)」(Visual Studio 2017 の Visual C++ の新機能)、「[Conformance Improvements in Visual C++ in Visual Studio 2017](../cpp-conformance-improvements-2017.md)」(Visual Studio 2017 の C++ 準拠の強化) を参照してください。

Visual C++ 2015 以降では、コンパイラの準拠に関する継続的な強化によって、コンパイラが既存のソース コードを認識する方法が変わる可能性があります。 このような場合、以前にビルドして問題なく実行できていたコードでも、ビルド時に新しいエラーや異なるエラーが発生したり、動作が変わったりする可能性があります。  
  
 幸いなことに、これらの変更はほとんどのソース コードにほとんど、またはまったく影響がありません。また、変更に対応するためにソース コードやその他の変更が必要な場合でも、通常は軽微で簡単な変更で済みます。 以前は問題がなかったソース コードで、変更が必要な *(修正前の)* コード例と、正しい *(修正後の)* コード例を多数紹介します。  
  
 これらの変更点はソース コードや他のビルド成果物に影響はあっても、Visual C++ の異なるバージョン間のバイナリの互換性には影響がありません。 より重大な変更で、*互換性に影響する変更*の場合、バイナリの互換性に影響が及ぶ可能性がありますが、このようなバイナリの互換性に影響する変更は、Visual C++ のメジャーバージョンが異なる場合にのみ発生します。 たとえば、Visual C++ 2013 と Visual C++ 2015 間などです。 Visual C++ 2013 と Visual C++ 2015 の間の互換性に影響する変更点については、「[Visual C++ 2003 ～ 2015 の変更履歴](../porting/visual-cpp-change-history-2003-2015.md)」を参照してください。  
  
-   [Visual C++ 2015 の準拠の強化](#VS_RTM)  
  
-   [更新プログラム 1 の準拠の強化](#VS_Update1)  
  
-   [更新プログラム 2 の準拠の強化](#VS_Update2)  
  
-   [更新プログラム 3 の準拠の強化](#VS_Update3)  
  
##  <a name="VS_RTM"></a> Visual C++ 2015 の準拠の強化  
  
-   /Zc:forScope - オプション  
  
     コンパイラ オプション **/Zc:forScope-** は使用できなくなりました。今後のリリースからは削除されます。  
  
    ```  
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release  
    ```  
  
     このオプションは通常、標準ではスコープから外れるポイントの後のループ変数を使用する、非標準のコードを許可するために使用されていました。 これは /Za オプションを使ってコンパイルするときにのみ必要でした。/Za がない場合は、ループの後でも常に for ループ変数が使用できるからです。 標準への準拠を考慮しない場合 (たとえば、コードを他のコンパイラに移植しない場合)、/Za オプションをオフにする (または、[言語拡張機能の無効化] プロパティを [いいえ] に設定する) こともできます。 移植可能で標準に準拠したコードの記述を考慮する場合、標準に準拠するようコードを再記述する必要があります。そのためには、変数の宣言をループの外側に移動します。  
  
    ```  
    // zc_forScope.cpp  
    // compile with: /Zc:forScope- /Za  
    // C2065 expected  
    int main() {  
       // Uncomment the following line to resolve.  
       // int i;  
       for (int i =0; i < 1; i++)  
          ;  
       i = 20;   // i has already gone out of scope under /Za  
    }  
    ```  
  
-   **/Zg コンパイラ オプション**  
  
     /Zg コンパイラ オプション (関数プロトタイプの生成) は使用できなくなりました。 前バージョンで、このコンパイラ オプションは使用できなくなりました。  
  
-   mstest.exe のコマンド ラインから C++/CLI で単体テストを実行できなくなりました。 代わりに、vstest.console.exe を使用します。 「[VSTest.Console.exe のコマンド ライン オプション](/devops-test-docs/test/vstest-console-exe-command-line-options)」を参照してください。  
  
-   **mutable キーワード**  
  
     `mutable` ストレージ クラス指定子は、エラーなしで以前コンパイルされていた場所で使用できなくなりました。 現在、コンパイラによってエラー C2071 (無効なストレージ クラス) が出されます。 標準では、変更可能な指定子はクラスのデータ メンバーの名前にのみ適用でき、const または static として宣言された名前には適用できません。また、参照メンバーにも適用できません。  
  
     次に例を示します。  
  
    ```  
    struct S {  
        mutable int &r;  
    };  
    ```  
  
     以前のバージョンの Visual C++ コンパイラはこれを受け入れていましたが、現在のコンパイラでは次のエラーが出されます。  
  
    ```Output  
    error C2071: 'S::r': illegal storage class  
    ```  
  
     エラーを修正するには、単に冗長の変更可能なキーワードを削除します。  
  
-   **char_16_t と char32_t**  
  
     `char16_t` または `char32_t` を typedef の別名として使用できなくなりました。これらの型は現在、組み込みとして扱われているからです。 ユーザーとライブラリの作成者が char16_t と char32_t をそれぞれ、uint16_t、uint32_t の別名として定義することが一般的でした。  
  
    ```  
    #include <cstdint>  
  
    typedef uint16_t char16_t; //C2628  
    typedef uint32_t char32_t; //C2628  
  
    int main(int argc, char* argv[])  
    {  
    uint16_t x = 1; uint32_t y = 2;  
    char16_t a = x;   
    char32_t b = y;   
    return 0;  
    }  
    ```  
  
     コードを更新するには、typedef 宣言を削除してこれらの名前と競合するその他の ID の名前を変更します。  
  
-   **非型テンプレート パラメーター**  
  
     非型テンプレート パラメーターを含む特定のコードは現在、明示的なテンプレート引数を指定すると、型の互換性について正しくチェックされます。 たとえば、次のコードは、以前のバージョンの Visual C++ でエラーなしでコンパイルしたものです。  
  
    ```  
    struct S1  
    {  
    void f(int);  
    void f(int, int);  
    };  
  
    struct S2  
    {  
    template <class C, void (C::*Function)(int) const> void f() {}  
    };  
  
    void f()  
    {  
    S2 s2;  
    s2.f<S1, &S1::f>();  
    }  
  
    ```  
  
     現在のコンパイラは、正しくエラーを出します。テンプレート パラメーターの型がテンプレートの引数と一致しないからです (パラメーターは const メンバーへのポインターですが、関数 f は非 const です)。  
  
    ```Output  
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'  
    ```  
  
     コードのこのエラーに対処するには、使用するテンプレート引数の型が、テンプレート パラメーターの宣言された型と一致することを確認してください。  
  
-   **__declspec(align)**  
  
     コンパイラは関数で `__declspec(align)` を受け入れなくなりました。 これは常に無視されていましたが、コンパイラ エラーを生成するようになりました。  
  
    ```  
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations  
    ```  
  
     この問題を修正するには、関数の宣言から `__declspec(align)` を削除してください。 これは影響がなかったため、削除しても何も変わりません。  
  
-   **例外処理**  
  
     例外処理への変更がいくつかあります。 まず、例外オブジェクトはコピー可能または移動可能にする必要があります。 次のコードは [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] ではコンパイルされますが、[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] ではコンパイルされません。  
  
    ```  
    struct S {  
    public:  
        S();  
    private:  
        S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     問題は、コピー コンストラクターはプライベートであるために通常の例外処理とは異なりオブジェクトをコピーできないことです。 コピー コンストラクターが `explicit`として宣言されている場合も同じことが当てはまります。  
  
    ```  
    struct S {  
        S();  
        explicit S(const S &);  
    };  
  
    int main()  
    {  
        throw S(); // error  
    }  
  
    ```  
  
     コードを更新するには、例外オブジェクトのコピー コンストラクターがパブリックであり、 `explicit`とマークされていないことを確認します。  
  
     値によって例外をキャッチする場合も、例外オブジェクトをコピー可能にする必要があります。 次のコードは [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] ではコンパイルされますが、[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] ではコンパイルされません。  
  
    ```  
    struct B {  
    public:  
        B();  
    private:  
        B(const B &);  
    };  
  
    struct D : public B {  
    };  
  
    int main()  
    {  
        try  
        {  
        }  
        catch (D d) // error  
        {  
        }  
    }  
  
    ```  
  
     この問題を解決するには、 `catch` のパラメーターの型を参照に変更します。  
  
    ```  
    catch(D& d)  
    {  
    }  
    ```  
  
-   **マクロに続く文字列リテラル**  
  
     このバージョンでは、コンパイラはユーザー定義リテラルをサポートするようになりました。 その結果、空白文字の介入がないマクロに続く文字列リテラルはユーザー定義のリテラルとして解釈されます。これにより、エラーまたは予期しない結果が起こる可能性があります。 たとえば、以前のコンパイラでは次のコードが正常にコンパイルされていました。  
  
    ```  
    #define _x "there"  
    char* func() {  
        return "hello"_x;  
    }  
    int main()  
    {  
        char * p = func();  
        return 0;  
    }  
    ```  
  
     コンパイラはこれを、マクロに続く "hello" というリテラル文字列として解釈していました。これは "there" に拡張され、2 つの文字列リテラルが 1 つに連結されていました。 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] では、コンパイラはこれをユーザー定義リテラルと解釈しますが、一致するユーザー定義リテラル _x が定義されていないため、エラーになります。  
  
    ```  
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found  
    note: Did you forget a space between the string literal and the prefix of the following string literal?  
  
    ```  
  
     この問題を解決するには、文字列リテラルとマクロの間に空白に追加します。  
  
-   **隣接する文字列リテラル**  
  
     以前と同様、文字列の解析に関連する変更のため、空白なしの隣接する文字列リテラル (ワイド文字列リテラルまたはナロー文字列リテラルのいずれか) は、以前のバージョンの Visual C++ では、単一の連結文字列と解釈されていました。 [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] では、2 つの文字列間に空白を追加する必要があります。 たとえば、次のコードを変更する必要があります。  
  
    ```  
    char * str = "abc""def";  
    ```  
  
     単に 2 つの文字列間に空白を追加します。  
  
    ```  
    char * str = "abc" "def";  
    ```  
  
-   **placement new と delete**  
  
     C++14 標準に準拠させるために delete 演算子に対して変更が加えられました。 標準の変更について詳しくは、「 [C++ サイズの割り当て解除](http://isocpp.org/files/papers/n3778.html)」をご覧ください。 変更により、size パラメーターを取るグローバルな delete 演算子のフォームが追加されます。 互換性に影響する変更は、(placement new 演算子と一致させるために) 以前同じシグネチャで delete 演算子を使用していた場合、コンパイラ エラーを受け取ります (これは C2956 というエラーで、placement new が使用されるポイントで発生します。それは、一致する適切な delete 演算子の識別をコンパイラが試行するコードの場所だからです)。  
  
     関数 `void operator delete(void *, size_t)` は、C++11 の placement new 関数 "void \* operator new(size_t, size_t)" に対応する placement delete 演算子でした。 現在、C++14 サイズの割り当て解除では、この delete 関数は *通常の解放関数* (グローバルな delete 演算子) です。 標準では、placement new の使用で対応する delete 関数を検索し、通常の解放関数を見つけた場合、プログラムの形式が不適切である必要があります。  
  
     たとえば、コードで placement new と placement delete の両方を定義するとします。  
  
    ```  
    void * operator new(std::size_t, std::size_t);  
    void operator delete(void*, std::size_t) noexcept;  
  
    ```  
  
     この問題は、定義した placement delete 演算子と新しいグローバル サイズの delete 演算子の間の関数シグネチャの一致により発生します。 placement new 演算子および delete 演算子で size_t とは異なる型を使用できるかどうかを検討してください。  size_t typedef の型はコンパイラによって異なります。これは Visual C++ の符号なし整数の typedef です。 適切なソリューションでは、次のように列挙型を使用します。  
  
    ```  
    enum class my_type : size_t {};  
  
    ```  
  
     次に、placement new と delete の定義を変更し、size_t の代わりにこの型を 2 番目の引数として使用します。 placement new の呼び出しを更新して新しい型を渡したり (たとえば、 `static_cast<my_type>` を使用することにより整数値から変換する)、new と delete の定義を更新して整数型にキャスト バックしたりする必要もあります。 これに対して列挙型を使用する必要はありません。size_t メンバーを持つクラス型も機能します。  
  
     代わりの方法として、placement new を完全に除去することもできます。 コードで placement new を使用してメモリ プールを実装する場合 (placement 引数が割り振られるまたは削除されるオブジェクトのサイズである)、独自のカスタム メモリ プール コードをサイズ割り当て解除機能で置き換えるほうが良い可能性があります。配置関数を削除でき、配置関数の代わりに独自の 2 つの引数 delete 演算子だけを使用することができます。  
  
     コードを即時に更新しない場合は、コンパイラ オプション /Zc:sizedDealloc- を使用して、従来の動作に戻すことができます。 このオプションを使用すると、2 つの引数を持つ削除関数が存在せず、placement delete 演算子との競合は発生しません。  
  
-   **共用体データ メンバー**  
  
     共用体データ メンバーで参照型を使用することはできなくなりました。 次のコードは [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] で正常にコンパイルされますが、[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] ではエラーになります。  
  
    ```  
    union U1 {  
        const int i;  
    };  
    union U2 {  
       int &i;  
    };  
    union U3 {  
        struct {int &i;};  
    };  
    ```  
  
     上のコードを実行すると、次のエラーが生成されます。  
  
    ```Output  
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type  
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type  
    ```  
  
     この問題に対処するには、参照型をポインターか値に変更します。 ポインターに型を変更する場合、共用体フィールドを使用するコードでの変更が必要です。 コードを値に変更すると、共用体に格納されているデータが変更されます。これは、他のフィールドに影響を与えます。共用体型のフィールドは同じメモリを共有するからです。 値のサイズによっては、共用体のサイズも変更される場合があります。  
  
-   匿名共用体の標準への適合が改善されました。 以前のバージョンのコンパイラでは、匿名共用体に対して明示的なコンストラクターとデストラクターが生成されていました。 これらは [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] で削除されています。  
  
    ```  
    struct S {  
      S();  
     };  
  
     union {  
      struct {  
       S s;  
      };  
     } u; // C2280  
    ```  
  
     上のコードを実行すると、[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] で次のエラーが生成されます。  
  
    ```  
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function  
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here  
    ```  
  
     この問題を解決するには、コンストラクターおよび/またはデストラクターの独自の定義を提供してください。  
  
    ```  
    struct S {  
    // Provide a default constructor by adding an empty function body.  
    S() {}   
    };  
  
    union {  
    struct {  
    S s;  
    };  
    } u;  
    ```  
  
-   **匿名構造体を持つ共用体**  
  
     標準と準拠させるために、共用体の匿名構造体メンバーのランタイムの動作が変更されました。 共用体の匿名構造体のメンバーのコンストラクターは、そのような共用体の作成時に暗黙的に呼び出されなくなりました。 また、共用体の匿名構造体のメンバーのデストラクターも、共用体がスコープから外れたときに暗黙的に呼び出されなくなりました。 次のコードを検討します。共用体 U に匿名構造体が含まれています。この匿名構造体には、名前付き構造体 S のメンバーが含まれており、その構造体にはデストラクターが含まれています。  
  
    ```  
    #include <stdio.h>  
    struct S {  
        S() { printf("Creating S\n"); }  
        ~S(){ printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
        S s;  
    };  
        U() {}  
        ~U(){}  
    };  
  
    void f()  
    {  
        U u;  
        // Destructor implicitly called here.  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     [!INCLUDE[cpp_dev12_long](../build/reference/includes/cpp_dev12_long_md.md)] では、S のコンストラクターは共用体の作成時に呼び出され、S のデストラクターは関数 f のスタックがクリーンアップされるときに呼び出されます。 しかし、[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] では、コンストラクターとデストラクターは呼び出されません。 コンパイラによって、この動作の変更に関する警告が出されます。  
  
    ```Output  
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called  
    ```  
  
     元の動作を復元するには、匿名構造体に名前を付けます。 非匿名構造体の実行時の動作は、コンパイラのバージョンに関係なく、同じです。  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        S() { printf("Creating S.\n"); }  
        ~S() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        } namedStruct;  
        U() {}  
        ~U() {}  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
        char s[1024];  
        printf("Press any key.\n");  
        gets_s(s);  
        return 0;  
    }  
    ```  
  
     別の方法として、新しい関数にコンストラクターとデストラクターのコードを移動し、共用体のコンストラクターおよびデストラクターからこれらの関数の呼び出しを追加します。  
  
    ```  
    #include <stdio.h>  
  
    struct S {  
        void Create() { printf("Creating S.\n"); }  
        void Destroy() { printf("Destroying S\n"); }  
    };  
    union U {  
        struct {  
            S s;  
        };  
        U() { s.Create();  }  
        ~U() { s.Destroy(); }  
    };  
  
    void f()  
    {  
        U u;  
    }  
  
    int main()  
    {  
        f();  
  
    char s[1024];  
    printf("Press any key.\n");  
    gets_s(s);  
    return 0;  
    }  
    ```  
  
-   **テンプレートの解決**  
  
     テンプレートの名前解決に変更が加えられています。 C++ では、名前解決の候補を検討する場合、一致の可能性として検討されている 1 つ以上の名前により、無効なテンプレート インスタンス化が生成される可能性があります。 これらの無効なインスタンス化は通常、それ自体はコンパイラ エラーの原因にはなりません。これは SFINAE (Substitution Failure Is Not An Error: 置き換えの失敗はエラーではない) と呼ばれます。  
  
     SFINAE のコンパイラがクラス テンプレートの特殊化のインスタンス化を必要とする場合は、この処理中に発生したエラーはコンパイラ エラーです。 以前のバージョンでは、コンパイラはこのようなエラーを無視していました。 次に例を示します。  
  
    ```  
    #include <type_traits>  
  
    template<typename T>  
    struct S  
    {  
    S() = default;  
    S(const S&);  
    S(S&&);  
  
    template<typename U, typename = typename std::enable_if<std::is_base_of<T, U>::value>::type>  
    S(S<U>&&);  
    };  
  
    struct D;  
  
    void f1()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    struct B  
    {  
    };  
  
    struct D : public B  
    {  
    };  
  
    void f2()  
    {  
    S<D> s1;  
        S<D> s2(s1);  
    }  
  
    ```  
  
     現在のコンパイラでコンパイルすると、次のエラーが表示されます。  
  
    ```Output  
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'  
    ..\t331.cpp(14): note: see declaration of 'D'  
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled  
            with  
            [  
                T=D,  
                U=D  
            ]  
    ```  
  
     これは、is_base_of の最初の呼び出しの時点でクラス 'D' がまだ定義されていないためです。  
  
     この場合の修正は、クラスが定義されるまでそのような型の特徴を使用しないことです。 B と D の定義をコード ファイルの先頭に移動すると、エラーが解決されます。 定義がヘッダー ファイルにある場合、ヘッダー ファイルの include ステートメントの順序を確認し、問題のあるテンプレートが使用される前にクラス定義がコンパイルされるようにしてください。  
  
-   **コピー コンストラクター**  
  
     [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] と Visual Studio 2015 の両方において、コンパイラは、クラスにユーザー定義の移動コンストラクターがあり、ユーザー定義のコピー コンストラクターはない場合に、そのクラスのコピー コンストラクターを生成します。 Dev14 では、この暗黙的に生成されたコピー コンストラクターは "= delete" とマークされています。  
  
##  <a name="VS_Update1"></a>更新プログラム 1 の準拠の強化  
  
-   **プライベートの仮想基底クラスと間接継承**  
  
     以前のバージョンのコンパイラでは、派生クラスは*間接的に派生した*`private virtual`基本クラスのメンバー関数を呼び出すことができました。 この従来の動作は正しい動作ではなく、C++ 標準に準拠していません。 コンパイラはこの方法で記述されたコードを受け入れなくなりました。その結果、コンパイラ エラー C2280 を発行します。  
  
    ```Output  
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    class base  
    {  
    protected:  
        base();  
        ~base();  
    };  
  
    class middle: private virtual base {};class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  //   
    }  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    class base;  // as above  
  
    class middle: protected virtual base {};  
    class top: public virtual middle {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
     - または -  
  
    ```  
    class base;  // as above  
  
    class middle: private virtual base {};  
    class top: public virtual middle, private virtual bottom {};  
  
    void destroy(top *p)  
    {  
        delete p;  
    }  
    ```  
  
-   **オーバーロードされた operator new と operator delete**  
  
     以前のバージョンのコンパイラでは、メンバー以外の `operator new` とメンバー以外の `operator delete` を static として宣言することや、グローバル名前空間以外の名前空間で宣言することが許可されていました。  この従来の動作のせいで、プログラマが意図した `new` または `delete` 演算子の実装がプログラムによって呼び出されないという危険性が生じ、結果として、問題のあるランタイム動作が警告なしに生じていました。 コンパイラはこの方法で記述されたコードを受け入れなくなりました。代わりにコンパイラ エラー C2323 を発行します。  
  
    ```Output  
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'  
    ```  
  
     また、コンパイラは特定の診断を行いませんが、インラインの operator new の形式は不適切であると見なされます。  
  
-   **非クラス型で 'operator *type*()' (ユーザー定義の変換) を呼び出す**  
  
     以前のバージョンのコンパイラでは 'operator *type*()' を非クラス型で呼び出すことが許可されていましたが、それは何の警告もなく無視されていました。 この従来の動作のせいで、問題のあるコードが警告なしに生成される危険性が生じ、結果として、予期しないランタイム動作の原因となっていました。 コンパイラはこの方法で記述されたコードを受け入れなくなりました。代わりにコンパイラ エラー C2228 を発行します。  
  
    ```Output  
    error C2228: left of '.operator type' must have class/struct/union  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column.operator index_t());  // error C2228  
    }  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    typedef int index_t;  
  
    void bounds_check(index_t index);  
  
    void login(int column)  
    {  
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'  
    }  
    ```  
  
-   **詳細な型指定子の冗長な typename**  
  
     以前のバージョンのコンパイラでは、詳細な型指定子内で `typename` を指定できました。この方法で記述されたコードは意味的に正しくありません。 コンパイラはこの方法で記述されたコードを受け入れなくなりました。代わりにコンパイラ エラー C3406 を発行します。  
  
    ```Output  
    error C3406: 'typename' cannot be used in an elaborated type specifier  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    template <typename class T>  
    class container;  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case  
    class container;  
    ```  
  
-   **初期化子リストからの配列の型推論**  
  
     以前のバージョンのコンパイラでは、初期化子リストからの配列の型推論はサポートされていませんでした。 コンパイラでこの形式の型推論がサポートされるようになりました。その結果、初期化子リストを使用した関数テンプレートへの呼び出しがあいまいになったり、以前のバージョンのコンパイラとは異なるオーバーロードが選ばれたりする可能性があります。 これらの問題を解決するには、プログラマの意図したオーバーロードをプログラムが明示的に指定する必要があります。  
  
     この新しい動作により、オーバーロードの解決で過去の候補と同程度に優れた追加候補が検討されると、呼び出しはあいまいになり、結果としてコンパイラはコンパイラ エラー C2668 を発行します。  
  
    ```Output  
    error C2668: 'function' : ambiguous call to overloaded function.  
    ```  
  
     例 1: オーバーロード関数のあいまいな呼び出し (変更前)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now considers this call ambiguous, and issues a compiler error  
        f({3});  error C2668: 'f' ambiguous call to overloaded function  
    }  
    ```  
  
     例 1: オーバーロード関数のあいまいな呼び出し (変更後)  
  
    ```cpp  
    template <typename... Args>  
    void f(int, Args...);  //   
  
    template <int N, typename... Args>  
    void f(const int (&)[N], Args...);  
  
    int main()  
    {  
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.  
        f(3);  
    }  
    ```  
  
     この新しい動作により、オーバーロードの解決で過去の候補よりも適合度の高い追加候補が検討されると、呼び出しはあいまいにならずに新しい候補に解決され、プログラムの動作は変化します。これはプログラマの意図した動作とは異なる場合があります。  
  
     例 2: オーバーロードの解決の変更 (変更前)  
  
    ```cpp  
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)  
    struct S  
    {  
        int i;  
        int j;  
    };  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead  
        f({1, 2});  
    }  
    ```  
  
     例 2: オーバーロードの解決の変更 (変更後)  
  
    ```cpp  
    struct S;  // as before  
  
    template <typename... Args>  
    void f(S, Args...);  
  
    template <int N, typename... Args>  
    void f(const int *&)[N], Args...);  
  
    int main()  
    {  
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.  
        f(S{1, 2});  
    }  
    ```  
  
-   **switch ステートメントの警告の復元**  
  
     前のバージョンのコンパイラで、 `switch` ステートメント関連の、以前から存在していた警告が削除されました。今ではこれらの警告は復元されています。 コンパイラは復元された警告を発行するようになり、特定の case (既定の case を含む) に関連する警告が、switch ステートメントの最後の行ではなく、問題のある case を含む行で発行されるようになりました。 この結果、以前とは異なる行でそれらの警告が発行されるようになり、以前は `#pragma warning(disable:####)` を使用して抑制できていた警告も、意図どおりに抑制できなくなる可能性があります。 意図どおりにこれらの警告を抑制するには、問題がある可能性のある最初の case の上の行まで `#pragma warning(disable:####)` ディレクティブを移動しなければならない場合があります。 復元された警告を次に示します。  
  
    ```Output  
    warning C4060: switch statement contains no 'case' or 'default' labels  
    ```  
  
    ```Output  
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label  
    ```  
  
    ```Output  
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled  
    ```  
  
    ```Output  
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'  
    ```  
  
    ```Output  
    warning C4064: switch of incomplete enum 'flags'  
    ```  
  
    ```Output  
    warning C4065: switch statement contains 'default' but no 'case' labels  
    ```  
  
    ```Output  
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'  
    ```  
  
    ```Output  
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given  
    ```  
  
     C4063 の例 (変更前)  
  
    ```cpp  
    class settings  
    {  
    public:  
        enum flags  
        {  
            bit0 = 0x1,  
            bit1 = 0x2,  
            ...  
        };  
        ...  
    };  
  
    int main()  
    {  
        auto val = settings::bit1;  
  
        switch (val)  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // warning C4063  
            break;  
        }  
    };  
    ```  
  
     C4063 の例 (変更後)  
  
    ```cpp  
    class settings {...};  // as above  
  
    int main()  
    {  
        // since C++11, use std::underlying_type to determine the underlying type of an enum  
        typedef std::underlying_type<settings::flags>::type flags_t;  
  
        auto val = settings::bit1;  
  
        switch (static_cast<flags_t>(val))  
        {  
        case settings::bit0:  
            break;  
  
        case settings::bit1:  
            break;  
  
        case settings::bit0 | settings::bit1:  // ok  
            break;  
        }  
    };  
    ```  
  
     その他の復元の警告の例については、それらのドキュメントをご覧ください。  
  
-   **#include: パス名で親ディレクトリの指定子 '..' を使用する** (/Wall /WX にのみ影響)  
  
     以前のバージョンのコンパイラでは、親ディレクトリの指定子の使用が検出されませんでした '… ' パス名で  `#include` ディレクティブです。 この方法で記述されたコードは通常、プロジェクトの相対パスが正しく使用されていないためにプロジェクトの外部に存在するヘッダーをインクルードすることを目的としています。 この従来の動作のせいで、プログラマが意図したものとは異なるソース ファイルをインクルードしてプログラムがコンパイルされる危険性や、これらの相対パスを他のビルド環境に移植できない危険性が生じました。 コンパイラは、この方法で書かれたコードを検出してプログラマに通知し、有効な場合にはオプションのコンパイラ警告 C4464 を発行するようになりました。  
  
    ```Output  
    warning C4464: relative include path contains '..'  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    #include "..\headers\C4426.h"  // emits warning C4464  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories  
    ```  
  
     さらに、コンパイラは特定の診断を示しませんが、プロジェクトのインクルード ディレクトリを指定する場合、親ディレクトリの指定子".." を使用することもお勧めします。  
  
-   **#pragma optimize() がヘッダー ファイルの終わりを超える** (/Wall /WX にのみ影響)  
  
     以前のバージョンのコンパイラでは、翻訳単位内に含まれるヘッダー ファイルをエスケープする最適化フラグの設定の変更は検出されませんでした。 コンパイラは、この方法で書かれたコードを検出してプログラマに通知し、有効な場合には、問題のある `#include`の位置でオプションのコンパイラ警告 C4426 を発行するようになりました。 この警告が発行されるのは、この変更が、コンパイラに対するコマンドライン引数によって設定された最適化フラグと競合する場合のみです。  
  
    ```Output  
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  // warning C4426  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    // C4426.h  
    #pragma optimize("g", off)  
    ...  
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments  
    // C4426.h ends  
  
    // C4426.cpp  
    #include "C4426.h"  
    ```  
  
-   **#pragma warning(push)** と **#pragma warning(pop) の不一致** (/Wall /WX にのみ影響)  
  
     以前のバージョンのコンパイラでは、`#pragma warning(push)` の状態の変更が、異なるソース ファイルの `#pragma warning(pop)` 状態の変更とペアになっていても (故意であることはまれですが)、それを検出しませんでした。 この従来の動作のせいで、プログラマの意図と異なる一連の警告が有効な状態でプログラムがコンパイルされる危険性が生じ、結果として、問題のあるランタイム動作が警告なしに発生する原因となっていました。 コンパイラは、この方法で書かれたコードを検出してプログラマに通知し、有効な場合には、一致する `#pragma warning(pop)` の位置でオプションのコンパイラの警告 C5031 を発行するようになりました。 この警告には、対応する #pragma warning(push) の場所を参照するメモが含まれます。  
  
    ```Output  
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    ...  
    #pragma warning(pop)  // pops a warning state not pushed in this source file   
    ...  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'  
    ...  
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031  
    ...  
  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    // C5031_part1.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  // pops the warning state pushed in this source file  
    // C5031_part1.h ends without #pragma warning(pop)  
  
    // C5031_part2.h  
    #pragma warning(push)  // pushes the warning state pushed in this source file  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop)  
    // C5031_part1.h ends  
  
    // C5031.cpp  
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.  
    ...  
    #include "C5031_part2.h"  
    ...  
  
    ```  
  
     一般的ではありませんが、意図的にこの方法でコードを記述する場合があります。 この方法で記述されたコードは `#include` の順序の変更の影響を受けます。可能な場合は、自己完結型の方法を使用してソース コード ファイルで警告状態を管理することをお勧めします。  
  
-   **一致していない #pragma warning(push)** (/Wall /WX にのみ影響)  
  
     以前のバージョンのコンパイラでは、翻訳単位の末尾で一致していない `#pragma warning(push)` の状態の変更は検出されませんでした。 コンパイラは、この方法で書かれたコードを検出してプログラマに通知し、有効な場合には、一致していない #pragma warning(push) の位置でオプションのコンパイラ警告 C5032 を発行するようになりました。 この警告が発行されるのは、翻訳単位にコンパイル エラーがない場合のみです。  
  
    ```Output  
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    // C5032.h ends without #pragma warning(pop)  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    // C5032.h  
    #pragma warning(push)  
    #pragma warning(disable:####)  
    ...  
    #pragma warning(pop) // matches #pragma warning (push) on line 1  
    // C5032.h ends  
  
    // C5032.cpp  
    #include "C5032.h"  
    ...  
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)  
    ```  
  
-   **#pragma 警告状態の追跡が強化された結果、追加の警告が発行される場合があります。**  
  
     以前のバージョンのコンパイラでは、#pragma 警告状態の変化の追跡が不十分なため、すべての意図された警告を発行できませんでした。 この動作により、プログラマの意図したものとは異なる状況で、事実上、特定の警告が抑制される危険性がありました。 コンパイラは #pragma 警告状態をより確実に追跡するようになりました (特にテンプレート内部での #pragma 警告状態の変化に関連するもの)。また `#pragma warning(push)` と `#pragma warning(pop)`の意図しない使用をプログラマが見つける手助けとして、新しい警告 C5031 と C5032 を必要に応じて発行するようになりました。  
  
     \#pragma 警告状態の変更の追跡が強化された結果、以前は誤って抑制されていた警告、または以前は誤って診断されていた問題に関連する警告が発行されるようになる場合があります。  
  
-   **制御が渡らないコードの識別の強化**  
  
     C++ 標準ライブラリが変更されたり、以前のバージョンのコンパイラよりも関数呼び出しのインライン化機能が強化されたりしたため、コンパイラは特定のコードに制御が渡らないことを示せるようになりました。 この新しい動作の結果、警告 C4720 のインスタンスが新しく、あるいはより頻繁に発行される可能性があります。  
  
    ```Output  
    warning C4720: unreachable code  
    ```  
  
     多くの場合、この警告が発行されるのは、最適化を有効にしてコンパイルするときだけです。最適化により、より多くの関数呼び出しがインライン化されたり、冗長なコードが削除されたり、コードに制御が渡っていないことを他の方法で判別できるようになったりするためです。 警告 C4720 の新しいインスタンスが try/catch ブロックで頻繁に発生 (特に [std::find](assetId:///std::find?qualifyHint=False&autoUpgrade=True)の使用に関連して) していることが確認されています。  
  
     例 (変更前)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // ok   
    }  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    try   
    {   
        auto iter = std::find(v.begin(), v.end(), 5);   
    }   
    catch(...)   
    {   
        do_something();  // warning C4702: unreachable code  
    }  
    ```  
  
##  <a name="VS_Update2"></a> 更新プログラム 2 の準拠の強化  
  
-   **SFINAE 式の部分的なサポートの結果として、追加の警告とエラーが発行される場合がある**  
  
     以前のバージョンのコンパイラは、SFINAE 式のサポートがなかったため、`decltype` 指定子内の特定の種類の式を解析しませんでした。 この従来の動作は正しい動作ではなく、C++ 標準に準拠していません。 コンパイラは、継続的な適合性の向上により、これらの式を解析し、SFINAE 式を部分的にサポートするようになりました。 その結果、コンパイラは、以前のバージョンのコンパイラが解析しなかった式で検出された警告とエラーを発行します。  
  
     この新しい動作が、まだ宣言されていない型を含む `decltype` 式を解析するとき、コンパイラは結果としてコンパイラ エラー C2039 を発行します。  
  
    ```Output  
    error C2039: 'type': is not a member of '`global namespace''  
    ```  
  
     例 1: 宣言されていない型の使用 (変更前)  
  
    ```cpp  
    struct s1  
    {  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  // error C2039  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     例 1 (変更後)  
  
    ```cpp  
    struct s1  
    {  
      template <typename>  // forward declare s2struct s2;  
  
      template <typename T>  
      auto f() -> decltype(s2<T>::type::f());  
  
      template<typename>  
      struct s2 {};  
    }  
    ```  
  
     依存名が型であることを指定するために必要な `typename` キーワードが欠落している `decltype` 式がこの新しい動作によって解析されると、コンパイラは、コンパイラ エラー C2923 と共にコンパイラの警告 C4346 を発行します。  
  
    ```Output  
    warning C4346: 'S2<T>::Type': dependent name is not a type  
    ```  
  
    ```Output  
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'  
    ```  
  
     例 2: 依存名が型ではない (変更前)  
  
    ```cpp  
    template <typename T>  
    struct s1  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    struct s2  
    {  
      typedef T type;  
    };  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<S2<T>::type>::type>()));  // warning C4346, error C2923  
    };  
    ```  
  
     例 2 (変更後)  
  
    ```cpp  
    template <typename T> struct s1 {...};  // as above  
    template <typename T> struct s2 {...};  // as above  
  
    template <typename T>  
    T declval();  
  
    struct s  
    {  
      template <typename T>  
      auto f(T t) -> decltype(t(declval<S1<typename S2<T>::type>::type>()));  
    };  
    ```  
  
-   `volatile` **メンバー変数が、暗黙的に定義されたコンストラクターと代入演算子を防止する**  
  
     以前のバージョンのコンパイラは、`volatile` メンバー変数を持つクラスが、自動的に生成された既定のコピー/移動コンストラクターと既定のコピー/移動代入演算子を持つことを許可していました。 この従来の動作は正しい動作ではなく、C++ 標準に準拠していません。 コンパイラは、揮発性のメンバー変数を持つクラスが、非単純コンストラクションと代入演算子を持つとみなすようになりました。それにより、これらの演算子の既定の実装が自動的に生成されることを防止します。  そのようなクラスが共用体 (またはクラス内の無名共用体) のメンバーである場合は、共用体のコピー/移動コンストラクターとコピー/移動代入演算子 (または無名共用体を含むクラス) は、暗黙的に削除済みとして定義されます。 明示的に定義することなく、共用体 (または無名共用体を含むクラス) を構築またはコピーしようとするとエラーとなり、結果として、コンパイラはコンパイラ エラー C2280 を発行します。  
  
    ```Output  
    error C2280: 'B::B(const B &)': attempting to reference a deleted function  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    struct A  
    {  
      volatile int i;  
      volatile int j;  
    };  
  
    extern A* pa;  
  
    struct B  
    {  
      union  
      {  
        A a;  
        int i;  
      };  
    };  
  
    B b1 {*pa};  
    B b2 (b1);  // error C2280  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    struct A  
    {  
      int i;int j;  
    };  
  
    extern volatile A* pa;  
  
    A getA()  // returns an A instance copied from contents of pa  
    {  
      A a;  
      a.i = pa->i;  
      a.j = pa->j;  
      return a;  
    }  
  
    struct B;  // as above  
  
    B b1 {GetA()};  
    B b2 (b1);  // error C2280  
    ```  
  
-   **静的メンバー関数は、CV 修飾子をサポートしていません。**  
  
     以前のバージョンの Visual C++ 2015 は、静的メンバー関数が CV 修飾子を持つことを許可していました。 この動作は、Visual C++ 2015 および Visual C++ 2015 Update 1 での回帰が原因です。Visual C++ 2013 および Visual C++ の以前のバージョンは、この方法で記述されたコードを拒否します。 Visual C++ 2015 および Visual C++ 2015 Update 1 の動作は正しいものではなく、C++ 標準に準拠していません。  Visual Studio 2015 Update 2 は、この方法で記述されたコードを拒否し、コンパイラ エラー C2511 を代わりに発行します。  
  
    ```Output  
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'  
    ```  
  
     例 (変更前)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() const {}  // C2511  
  
    ```  
  
     例 (変更後)  
  
    ```  
    struct A  
    {  
      static void func();  
    };  
  
    void A::func() {}  // removed const  
  
    ```  
  
-   **列挙型の事前宣言は、WinRT コードでは許可されていません** (/ZW にのみ影響)  
  
     管理された C++ コードが /clr コンパイラ スイッチを使用して .Net Framework 用にコンパイルされる場合と同様に、Windows ランタイム (WinRT) 用にコンパイルされたコードは、`enum` 型が事前に宣言されることを許可しません。 この動作により、列挙型のサイズが常にわかり、WinRT 型システムに正しくプロジェクションを実行することができます。 コンパイラは、この方法で記述されたコードを拒否し、コンパイラ エラー C3197 と共にコンパイラ エラー C2599 を発行します。  
  
    ```Output  
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed  
    ```  
  
    ```Output  
    error C3197: 'public': can only be used in definitions  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    namespace A {  
      public enum class CustomEnum: int32;  // forward declaration; error C2599, error C3197  
    }  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
     例 (変更後)  
  
    ```cpp  
              // forward declaration of CustomEnum removed  
  
    namespace A {  
      public enum class CustomEnum: int32  
      {  
        Value1  
      };  
    }  
  
    public ref class Component sealed  
    {  
    public:  
      CustomEnum f()  
      {  
        return CustomEnum::Value1;  
      }  
    };  
    ```  
  
-   **オーバーロードされた非メンバー operator new と operator delete をインラインで宣言できない** (レベル 1 (/W1) 既定で有効)  
  
     以前のバージョンのコンパイラは、非メンバー operator new と operator delete 関数がインラインで宣言されるときに警告を発行しません。 この方法で記述されたコードは、形式が正しくなく (診断は必要なし)、new 演算子と delete 演算子の不一致 (特に、サイズ割り当て解除と共に使用された場合) から生じるメモリの問題を引き起こす可能性があります。この問題を診断するのは難しい場合があります。   コンパイラは警告 C4595 を発行するようになったので、この方法で記述されたコードを識別しやすくなりました。  
  
    ```Output  
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline  
    ```  
  
     例 (変更前)  
  
    ```cpp  
              inline void* operator new(size_t sz)  // warning C4595  
    {  
      ...  
    }  
    ```  
  
     例 (変更後)  
  
    ```cpp  
              void* operator new(size_t sz)  // removed inline  
    {  
      ...  
    }  
    ```  
  
     この方法で記述されたコードを修正するには、演算子の定義をヘッダー ファイルから対応するソース ファイルに移動することが必要な場合があります。  
  
##  <a name="VS_Update3"></a> 更新プログラム 3 の準拠の強化  
  
-   **std::is_convertable は self-assignment** (標準ライブラリ) を検出するようになりました  
  
     以前のバージョンの `std::is_convertable` type-trait は、コピー コンストラクターが削除済みまたはプライベートの場合、クラス型の自己代入を正しく検出していませんでした。 コピー コンストラクターが削除済みまたはプライベートの場合でも、クラス型の自己代入時にも `std::is_convertable<>::value` が正しく `false` に設定されるようになりました。  
  
     この変更に関連するコンパイラの診断はありません。  
  
     例  
  
    ```cpp  
    #include <type_traits>  
  
    class X1  
    {  
    public:  
        X1(const X1&) = delete;  
    };  
  
    class X2  
    {  
    private:  
        X2(const X2&);  
    };  
  
    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");  
    ```  
  
     以前のバージョンの Visual C++ では、`std::is_convertable<>::value` が不適切に `true` に設定されているため、この例の一番下にある静的なアサーションは成功します。 新しいバージョンでは、`std::is_convertable<>::value` は正しく `false` に設定され、静的なアサーションが失敗するようになりました。  
  
-   **既定値にされた、または削除された単純なコピー コンストラクターと移動コンストラクターのアクセス指定子の尊重**  
  
     以前のバージョンのコンパイラは、既定値にされた、または削除された単純なコピー コンストラクターと移動コンストラクターを呼び出し前に確認していませんでした。 この従来の動作は正しい動作ではなく、C++ 標準に準拠していません。 場合によっては、この従来の動作のせいで、問題のあるコードが警告なしに生成される危険性が生じ、結果として、予期しないランタイム動作の原因となっていました。 コンパイラは、既定値に指定された、または削除された単純なコピー コンストラクターと移動コンストラクターをチェックし、呼び出し可能かどうかを判断し、呼び出し不能と判断した場合に、コンパイラの警告 C2248 を結果として返します。  
  
    ```Output  
    error C2248: 'S::S' cannot access private member declared in class 'S'  
    ```  
  
     例 (変更前)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(S);  // pass S by value  
  
    int main()  
    {  
        S s;  
        f(s);  // error C2248, can't invoke private copy constructor  
    }  
    ```  
  
     例 (変更後)  
  
    ```cpp  
    class S {  
    public:  
           S() = default;  
    private:  
        S(const S&) = default;  
    };  
  
    void f(const S&);  // pass S by reference  
  
    int main()  
    {  
        S s;  
        f(s);  
    }  
    ```  
  
-   **属性が指定された ATL コードのサポートの非推奨化** (デフォルトでレベル 1 (/W1))  
  
     以前のバージョンのコンパイラは、属性が指定された ATL コードをサポートしていました。 [Visual C++ 2008 から始まった](https://msdn.microsoft.com/library/bb384632\(v=vs.90\).aspx)、属性が指定された ATL コードのサポートを停止する次のフェーズとして、属性が指定された ATL コードは非推奨になりました。 コンパイラは、非推奨になったこの種類のコードを特定するために、コンパイラの警告 C4467 を発行するようになりました。  
  
    ```Output  
    warning C4467: Usage of ATL attributes is deprecated  
    ```  
  
     コンパイラからサポートが削除されるまで、属性が指定された ATL コードを今後も使い続ける場合は、`/Wv:18` または `/wd4467` コマンド ライン引数をコンパイラに渡すことで、またはソース コードに `#pragma warning(disable:4467)` を追加することで、この警告を無効にすることができます。  
  
     例 1 (変更前)  
  
    ```cpp  
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]  
    class A {};  
    ```  
  
     例 1 (変更後)  
  
    ```cpp  
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};  
  
    ```  
  
     非推奨になった ATL 属性の使用を防ぐために、次のコード例のように、IDL ファイルを作成する場合があります。  
  
     例 2 (変更後)  
  
    ```cpp  
    [emitidl];  
    [module(name="Foo")];  
  
    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
    __interface ICustom {  
        HRESULT Custom([in] long l, [out, retval] long *pLong);  
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);  
    };  
  
    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
    class CFoo : public ICustom  
    {  
        // ...  
    };  
    ```  
  
     まず、*.idl ファイルを作成します。vc140.idl で生成されるファイルを使用して、インターフェイスと注釈を含む \*.idl ファイルを取得することができます。  
  
     次に、MIDL 手順をビルドに追加し、C++ インターフェイス定義が生成されるようにします。  
  
     例 2 IDL (変更後)  
  
    ```cpp  
    import "docobj.idl";  
  
    [  
        object,local,uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)  
    ]  
  
    interface ICustom : IUnknown {  
        HRESULT  Custom([in] long l, [out,retval] long *pLong);  
        [local] HRESULT  CustomLocal([in] long l, [out,retval] long *pLong);  
    };  
  
    [ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]  
    library Foo  
    {  
        importlib("stdole2.tlb");  
        importlib("olepro32.dll");  
            [  
                version(1.0),  
                appobject,uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)  
            ]  
  
        coclass CFoo {  
            interface ICustom;  
        };  
    }  
    ```  
  
     次に、以下のコード例のように、実装ファイルで ATL を直接使用します。  
  
     例 2 実装 (変更後)  
  
    ```cpp  
    #include <idl.header.h>  
    #include <atlbase.h>  
  
    class ATL_NO_VTABLE CFooImpl :  
        public ICustom,  
        public ATL::CComObjectRootEx<CComMultiThreadModel>  
    {  
    public:  
        BEGIN_COM_MAP(CFooImpl)  
        COM_INTERFACE_ENTRY(ICustom)  
        END_COM_MAP()  
    };  
    ```  
  
-   **プリコンパイル済みヘッダー (PCH) ファイルと一致しない #include ディレクティブ** (/Wall /WX にのみ影響)  
  
     以前のバージョンのコンパイラは、プリコンパイル済みヘッダー (PCH) ファイルの使用時に、`-Yc` と `-Yu` のコンパイル間のソース ファイルの `#include` ディレクティブ一致しない場合でも、受け入れていました。 この方法で記述されたコードは、コンパイラで処理できなくなります。   コンパイラは、PCH ファイルの使用時に `#include` ディレクティブの不一致を特定できるようにコンパイラの警告 CC4598 を発行するようになりました。  
  
    ```Output  
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position  
    ```  
  
     例 (変更前):  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"  
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "b.h"  
    #include "a.h"  // mismatched order relative to X.cpp  
    #include "c.h"  
    ```  
  
     例 (変更後)  
  
     X.cpp (-Ycc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h"   
    #include "c.h"  
    ```  
  
     Z.cpp (-Yuc.h)  
  
    ```cpp  
    #include "a.h"  
    #include "b.h" // matched order relative to X.cpp  
    #include "c.h"  
    ```  
  
-   **プリコンパイル済みヘッダー (PCH) ファイルと一致しない include ディレクトリ** (/Wall /WX にのみ影響)  
  
     プリコンパイル済みヘッダー (PCH) ファイルの使用時に、以前のバージョンのコンパイラは、コンパイラ `-Yc` と `-Yu` のコンパイルで一致しない include ディレクトリ (`-I`) コマンド ライン引数を受け入れていました。 この方法で記述されたコードは、コンパイラで処理できなくなります。   コンパイラは、PCH ファイルの使用時に include ディレクトリ (`-I`) コマンド ライン引数を特定できるコンパイラの警告 CC4599 を発行するようになりました。  
  
    ```Output  
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position  
    ```  
  
     例 (変更前)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h Z.cpp  
    ```  
  
     例 (変更後)  
  
    ```ms-dos  
    cl /c /Wall /Ycc.h -I.. X.cpp  
    cl /c /Wall /Yuc.h -I.. Z.cpp  
    ```