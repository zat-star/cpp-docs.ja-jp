---
title: "locale クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::locale"
  - "std::locale"
  - "std.locale"
  - "locale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "locale クラス"
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
caps.latest.revision: 28
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# locale クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定のローカライズされた環境を集合的に定義する一連のファセットとして、カルチャ固有の情報をカプセル化するロケール オブジェクトを表すクラス。  
  
## <a name="syntax"></a>構文  
  
```  
class locale;  
```  
  
## <a name="remarks"></a>コメント  
 ファセットはクラスから派生したクラスのオブジェクトへのポインター [ファセット](#facet_class) を持つ、フォームのパブリック オブジェクト。  
  
```  
static locale::id id;  
```  
  
 制約のない一連のファセットを定義できます。 任意の数のファセットを指定するロケール オブジェクトを構築することもできます。  
  
 これらのファセットの定義済みのグループを表す、 [ロケールのカテゴリ](#locale__category) 関数によって従来、標準 C ライブラリの管理されている `setlocale`します。  
  
 collate カテゴリ (LC_COLLATE) には、次のファセットが含まれます。  
  
```  
collate<char>  
collate<wchar_t>  
```  
  
 ctype カテゴリ (LC_CTYPE) には、次のファセットが含まれます。  
  
```  
ctype<char>  
ctype<wchar_t>  
codecvt<char, char, mbstate_t>  
codecvt<wchar_t, char, mbstate_t>  
codecvt<char16_t, char, mbstate_t>  
codecvt<char32_t, char, mbstate_t>  
```  
  
 monetary カテゴリ (LC_MONETARY) には、次のファセットが含まれます。  
  
```  
moneypunct<char, false>  
moneypunct<wchar_t, false>  
moneypunct<char, true>  
moneypunct<wchar_t, true>  
money_get<char, istreambuf_iterator<char>>  
money_get<wchar_t, istreambuf_iterator<wchar_t>>  
money_put<char, ostreambuf_iterator<char>>  
money_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 numeric カテゴリ (LC_NUMERIC) には、次のファセットが含まれます。  
  
```  
num_get<char, istreambuf_iterator<char>>  
num_get<wchar_t, istreambuf_iterator<wchar_t>>  
num_put<char, ostreambuf_iterator<char>>  
num_put<wchar_t, ostreambuf_iterator<wchar_t>>  
numpunct<char>  
numpunct<wchar_t>  
```  
  
 time カテゴリ (LC_TIME) には、次のファセットが含まれます。  
  
```  
time_get<char, istreambuf_iterator<char>>  
time_get<wchar_t, istreambuf_iterator<wchar_t>>  
time_put<char, ostreambuf_iterator<char>>  
time_put<wchar_t, ostreambuf_iterator<wchar_t>>  
```  
  
 messages カテゴリ (LC_MESSAGES) には、次のファセットが含まれます。  
  
```  
messages<char>  
messages<wchar_t>  
```  
  
 (最後のカテゴリは Posix で必要ですが、C 標準では必要ありません。)  
  
 これらの定義済みのファセットの一部は、数値とテキスト シーケンスとの変換を制御するために、iostreams クラスによって使用されます。  
  
 クラス ロケールのオブジェクトは、クラスのオブジェクトとして、ロケール名を格納するも [文字列](../Topic/%3Cstring%3E%20typedefs.md#string)します。 クラスのオブジェクトをスローする無効なロケール名を使用して、ロケールのファセットまたはロケール オブジェクトを作成する [runtime_error](../Topic/runtime_error%20Class.md)します。 ロケール オブジェクトで、C スタイルのロケールがオブジェクトによって表されるロケールに正確に対応するかどうかを確認できない場合、格納されるロケール名は `"*"` です。 ロケール オブジェクト用の標準 C ライブラリ内で一致するロケールを確立する場合は、 `_Loc`, を呼び出して `setlocale`(LC_ALL `,` `_Loc`します。 [名前](#locale__name)`().c_str()`)。  
  
 この実装では、次の静的メンバー関数を呼び出すことによって、  
  
```  
static locale empty();
```  
  
 ファセットがないロケール オブジェクトを構築することもできます。 ロケールは透過的ロケールも場合テンプレート関数は、 [has_facet](../Topic/%3Clocale%3E%20functions.md#has_facet) と [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) 要求されたファセットを見つけることができませんを透過的ロケール内で最初に、グローバル ロケールを参照してが透過的にする場合、クラシック ロケールです。 したがって、次のように記述できます。  
  
```  
cout.imbue(locale::empty());
```  
  
 後続の挿入 [cout](../Topic/%3Ciostream%3E%20functions.md#cout) グローバル ロケールの現在の状態に基づいて仲介されます。 次のように記述することもできます。  
  
```  
locale loc(locale::empty(),
    locale::classic(),  
    locale::numeric);

cout.imbue(loc);
```   
  
 `cout` への以降の挿入についての数値書式設定規則は、グローバル ロケールで日付や金額の挿入についての変更規則が提供されている場合でも、C のロケールの場合と同様です。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[ロケール](#locale__locale)|ロケール、ロケールのコピー、またはファセットやカテゴリが別のロケールのファセットやカテゴリで置換されたロケールのコピーを作成します。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[カテゴリ](#locale__category)|標準ファセット ファミリを示すビットマスク値を指定する整数型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[結合](#locale__combine)|ターゲット ロケールに指定されたロケールのファセットを挿入します。|  
|[名](#locale__name)|格納されているロケール名を返します。|  
  
### <a name="static-functions"></a>静的関数  
  
|||  
|-|-|  
|[クラシック](#locale__classic)|この静的メンバー関数は、クラシック C ロケールを表すロケール オブジェクトを返します。|  
|[グローバル](#locale__global)|プログラムの既定のロケールをリセットします。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator! =](#locale__operator_neq)|2 つのロケールが等しくないかどうかをテストします。|  
|[operator)](#locale__operator__)|2 つの `basic_string` オブジェクトを比較します。|  
|[演算子 = =](#locale__operator_eq_eq)|2 つのロケールが等しいかどうかをテストします。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[ファセット](#facet_class)|すべてのロケールのファセットの基底クラスとして機能するクラス。|  
|[id](#id_class)|このメンバー クラスは、ロケール内でファセットを検索するためのインデックスとして使用される一意のファセット ID を提供します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namelocalecategorya-localecategory"></a><a name="locale__category"></a>  locale::category  
 標準ファセット ファミリを示すビットマスク値を指定する整数型。  
  
```  
typedef int category;  
static const int collate = LC_COLLATE;  
static const int ctype = LC_CTYPE;  
static const int monetary = LC_MONETARY;  
static const int numeric = LC_NUMERIC;  
static const int time = LC_TIME;  
static const int messages = LC_MESSAGES;  
static const int all = LC_ALL;  
static const int none = 0;  
```  
  
### <a name="remarks"></a>コメント  
 型のシノニムは、 `int` ビットマスクの一意の要素のグループを表すことのできる型がクラス ロケールのローカルを入力または対応する C ロケールのカテゴリのいずれかを表すために使用できます。 要素は次のとおりです。  
  
- **collate**, LC_COLLATE C カテゴリに対応する、  
  
- **ctype**, LC_CTYPE C カテゴリに対応する、  
  
- **通貨**, LC_MONETARY C カテゴリに対応する、  
  
- **数値**, C lc_numeric に対応する、  
  
- **時間**, LC_TIME C カテゴリに対応する、  
  
- **メッセージ**, LC_MESSAGES Posix のカテゴリに対応する、  
  
 さらに、2 つ値が使用されます。  
  
- **[なし]**, C カテゴリの [なし] に対応する、  
  
- **すべて**, LC_ALL のすべてのカテゴリの C の共用体に対応する、  
  
 使用してカテゴリの任意のグループを表すことができます `OR` に示すように、これらの定数 **通貨** &#124; **時間**します。  
  
##  <a name="a-namelocaleclassica-localeclassic"></a><a name="locale__classic"></a>  locale::classic  
 この静的メンバー関数は、クラシック C ロケールを表すロケール オブジェクトを返します。  
  
```  
static const locale& classic();
```  
  
### <a name="return-value"></a>戻り値  
 C ロケールへの参照。  
  
### <a name="remarks"></a>コメント  
 クラシック C ロケールがアメリカ国際化しないプログラムで暗黙的に使用されている標準 C ライブラリ内でのロケールを英語 ASCII です。  
  
### <a name="example"></a>例  
  
```  
// locale_classic.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: " << loc2.name( )  
        << "." << endl;  
   cout << "The name of the current locale is: " << loc1.name( )   
        << "." << endl;  
  
   if (loc2 == locale::classic( ) )  
      cout << "The previous locale was classic." << endl;  
   else  
      cout << "The previous locale was not classic." << endl;  
  
   if (loc1 == locale::classic( ) )  
      cout << "The current locale is classic." << endl;  
   else  
      cout << "The current locale is not classic." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
The previous locale was classic.  
The current locale is not classic.  
```  
  
##  <a name="a-namelocalecombinea-localecombine"></a><a name="locale__combine"></a>  locale::combine  
 ターゲット ロケールに指定されたロケールのファセットを挿入します。  
  
```  
template <class Facet>  
locale combine(const locale& _Loc) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Loc`  
 対象のロケールに挿入するファセットを含むロケールです。  
  
### <a name="return-value"></a>戻り値  
 メンバー関数で置換したりを追加したりするロケール オブジェクトを返します。 **\*この** ファセット `Facet` に示されている `_Loc`します。  
  
### <a name="example"></a>例  
  
```  
// locale_combine.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main() {  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   locale loc2 ( "C" );  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
}  
```  
  
##  <a name="a-namefacetclassa-facet-class"></a><a name="facet_class"></a>  facet クラス  
 すべてのロケールのファセットの基底クラスとして機能するクラス。  
  
クラスのファセット {保護: 明示的なファセット (size_t _Refs = 0); 仮想 ~ facet(); プライベート: facet(const facet&)/void 演算子が定義されていない/=(const facet&)/が定義されていない/}。  
  
### <a name="remarks"></a>コメント  
 コピーまたはクラスのファセットのオブジェクトを代入できませんに注意してください。 作成し、クラスから派生したオブジェクトを破棄する `locale::facet` が、適切な基本クラスのオブジェクトではありません。 通常、オブジェクトを構築する `_Myfac` ファセットから派生したように、ロケールを構築するときに **localeloc**( `locale::classic`()、 **新しい**`_Myfac`) です。  
  
 このような場合の基本クラスのファセット コンス トラクターは、0 が付きますが `_Refs` 引数。 オブジェクトが不要になったときに削除されます。 このため、0 以外の値 _ を指定する *Refs* オブジェクトの有効期間中に責任を行う場合にのみ引数。  
  
##  <a name="a-namelocaleglobala-localeglobal"></a><a name="locale__global"></a>  locale::global  
 プログラムの既定のロケールをリセットします。 これにより、グローバル ロケールが C および C++ の両方に影響します。  
  
```  
static locale global(const locale& _Loc);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Loc`  
 プログラムによって既定のロケールとして使用するロケール。  
  
### <a name="return-value"></a>戻り値  
 以前は、既定のロケールをリセットする前にロケールです。  
  
### <a name="remarks"></a>コメント  
 プログラムの起動時には、グローバル ロケールは、クラシック ロケールと同じです。  `global()` 関数呼び出し `setlocale( LC_ALL, loc.name. c_str())` 標準 C ライブラリに一致するロケールを確立します。  
  
### <a name="example"></a>例  
  
```cpp  
// locale_global.cpp  
// compile by using: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_germany" );  
   locale loc1;  
   cout << "The initial locale is: " << loc1.name( ) << endl;  
   locale loc2 = locale::global ( loc );  
   locale loc3;  
   cout << "The current locale is: " << loc3.name( ) << endl;  
   cout << "The previous locale was: " << loc2.name( ) << endl;  
}  
```  
  
```Output  
The initial locale is: C  
The current locale is: German_Germany.1252  
The previous locale was: C  
```  
  
##  <a name="a-nameidclassa-id-class"></a><a name="id_class"></a>  id クラス  
 このメンバー クラスは、ロケール内でファセットを検索するためのインデックスとして使用される一意のファセット ID を提供します。  
  
クラス id {保護: id(); プライベート: id(const id&)/void 演算子が定義されていない/=(const id&)/が定義されていない/}。  
  
### <a name="remarks"></a>コメント  
 このメンバー クラスは、それぞれ固有のロケールのファセットで必要な静的メンバー オブジェクトを表します。 コピーやクラスのオブジェクトを割り当てることはできません **id**します。  
  
##  <a name="a-namelocalelocalea-localelocale"></a><a name="locale__locale"></a>  locale::locale  
 ロケール、ロケールのコピー、またはファセットやカテゴリが別のロケールのファセットやカテゴリで置換されたロケールのコピーを作成します。  
  
```  
locale();

explicit locale(
    const char* _Locname,  
    category _Cat = all);

explicit locale(
    const string& _Locname);

locale(
    const locale& _Loc);

locale(
    const locale& _Loc,   
    const locale& _Other,  
    category _Cat);

locale(
    const locale& _Loc,   
    const char* _Locname,  
    category _Cat);

template <class Facet>  
locale(
 const locale& _Loc,   
    const Facet* _Fac);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Locname`  
 ロケールの名前です。  
  
 `_Loc`  
 新しいロケールを作成する際にコピーするロケール。  
  
 `_Other`  
 カテゴリを選択するロケール。  
  
 `_Cat`  
 構築されたロケールに置き換えられるカテゴリです。  
  
 `_Fac`  
 構築されたロケールに置き換えられるファセット。  
  
### <a name="remarks"></a>コメント  
 最初のコンス トラクターは、グローバル ロケールと一致するオブジェクトを初期化します。 2 番目と 3 番目のコンス トラクターは、ロケール名との整合性の動作が存在するすべてのロケールのカテゴリを初期化 `_Locname`します。 残りのコンス トラクターはコピー `_Loc`, 、例外については。  
  
 `locale(const locale& _Loc, const locale& _Other, category _Cat);`  
  
 置換 `_Other` する C の C のカテゴリに対応する、ファセット & `_Cat` がゼロ以外です。  
  
 `locale(const locale& _Loc, const char* _Locname, category _Cat);`  
  
 `locale(const locale& _Loc, const string& _Locname, category _Cat);`  
  
 置換 `locale(_Locname, _All)` する C の C のカテゴリに対応する、ファセット & `_Cat`がゼロ以外です。  
  
 `template<class Facet> locale(const locale& _Loc, Facet* _Fac);`  
  
 置き換えられます (または追加) `_Loc` ファセット `_Fac`, 場合は、 `_Fac` が null ポインターでないです。  
  
 場合は、ロケール名 `_Locname` null ポインターに達したり、それ以外の場合に無効な関数のスロー [runtime_error](../Topic/runtime_error%20Class.md)します。  
  
### <a name="example"></a>例  
  
```  
// locale_locale.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <tchar.h>  
using namespace std;  
  
int main( ) {  
  
   // Second constructor  
   locale loc ( "German_germany" );  
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet  
   _TCHAR * s2 = _T("Das ist weizzz.");  
   int result1 = use_facet<collate<_TCHAR> > ( loc ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;  
  
   // The first (default) constructor  
   locale loc2;  
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;  
  
   // Third constructor  
   locale loc3 (loc2,loc, _M_COLLATE );  
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;  
  
   // Fourth constructor  
   locale loc4 (loc2, "German_Germany", _M_COLLATE );  
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).  
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );  
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;  
}  
```  
  
##  <a name="a-namelocalenamea-localename"></a><a name="locale__name"></a>  locale::name  
 格納されているロケール名を返します。  
  
```  
string name() const;
```  
  
### <a name="return-value"></a>戻り値  
 ロケールの名前を指定する文字列。  
  
### <a name="example"></a>例  
  
```  
// locale_name.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "german" );  
   locale loc2 = locale::global( loc1 );  
   cout << "The name of the previous locale is: "   
        << loc2.name( ) << "." << endl;  
   cout << "The name of the current locale is: "   
        << loc1.name( ) << "." << endl;  
}  
```  
  
```Output  
The name of the previous locale is: C.  
The name of the current locale is: German_Germany.1252.  
```  
  
##  <a name="a-namelocaleoperatorneqa-localeoperator"></a><a name="locale__operator_neq"></a>  locale::operator! =  
 2 つのロケールが等しくないかどうかをテストします。  
  
```  
bool operator!=(const locale& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 非等値をテストするロケールのいずれかです。  
  
### <a name="return-value"></a>戻り値  
 ブール値 **true** ロケールが、同じロケールのコピーではない場合 **false** ロケールが、同じロケールのコピーである場合。  
  
### <a name="remarks"></a>コメント  
 同じ名前があるか、その他のコピーがある場合、同じロケールしている場合、2 つのロケールが等しい。  
  
### <a name="example"></a>例  
  
```  
// locale_op_ne.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 != loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;  
  
   if ( loc1 != loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252) and  
 loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252) and  
 loc3 (English_United States.1252) are not equal.  
```  
  
##  <a name="a-namelocaleoperatora-localeoperator"></a><a name="locale__operator__"></a>  locale::operator()  
 2 つの `basic_string` オブジェクトを比較します。  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` left`  
 左側の文字列です。  
  
 ` right`  
 右側の文字列。  
  
### <a name="return-value"></a>戻り値  
 メンバー関数を返します。  
  
-   最初のシーケンスを比較未満の 2 番目のシーケンスを返します。  
  
-   2 番目のシーケンスを比較して最初のシーケンスよりも小さい場合は +1。  
  
-   シーケンスが等しい場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は効率的に実行します。  
  
```  
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) <0);
```  
  
 したがって、関数オブジェクトとしてロケール オブジェクトを使用することができます。  
  
### <a name="example"></a>例  
  
```  
// locale_op_compare.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
int main( )   
{  
   using namespace std;  
   wchar_t *sa = L"ztesting";  
   wchar_t *sb = L"\0x00DFtesting";  
   basic_string<wchar_t> a( sa );  
   basic_string<wchar_t> b( sb );  
  
   locale loc( "German_Germany" );  
   cout << loc( a,b ) << endl;  
  
   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );  
   cout << ( fac.compare( sa, sa + a.length( ),  
       sb, sb + b.length( ) ) < 0) << endl;  
}  
```  
  
```Output  
0  
0  
```  
  
##  <a name="a-namelocaleoperatoreqeqa-localeoperator"></a><a name="locale__operator_eq_eq"></a>  locale::operator = =  
 2 つのロケールが等しいかどうかをテストします。  
  
```  
bool operator==(const locale& right) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 等しいかどうかをテストするロケールのいずれかです。  
  
### <a name="return-value"></a>戻り値  
 ブール値 **true** 場合は、同じロケールのコピーであるロケール **false** ロケールが、同じロケールのコピーではない場合。  
  
### <a name="remarks"></a>コメント  
 同じ名前があるか、その他のコピーがある場合、同じロケールしている場合、2 つのロケールが等しい。  
  
### <a name="example"></a>例  
  
```  
// locale_op_eq.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string>  
#include <locale>  
  
using namespace std;  
  
int main( )   
{  
   locale loc1( "German_Germany" );  
   locale loc2( "German_Germany" );  
   locale loc3( "English" );  
  
   if ( loc1 == loc2 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."   
      << endl;  
  
   if ( loc1 == loc3 )  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."   
      << endl;  
   else  
      cout << "locales loc1 (" << loc1.name( )  
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."   
      << endl;  
}  
```  
  
```Output  
locales loc1 (German_Germany.1252)  
 and loc2 (German_Germany.1252) are equal.  
locales loc1 (German_Germany.1252)  
 and loc3 (English_United States.1252) are not equal.  
```  
  
## <a name="see-also"></a>関連項目  
 [\< ロケール>](../standard-library/locale.md)   
 [コード ページ](../c-runtime-library/code-pages.md)   
 [ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

