---
title: "basic_ios クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.basic_ios
- ios/std::basic_ios
- basic_ios
- std::basic_ios
dev_langs:
- C++
helpviewer_keywords:
- basic_ios class
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6987d9c75785ebb716324395e0ce295d4155e55f
ms.lasthandoff: 02/24/2017

---
# <a name="basicios-class"></a>basic_ios クラス
このテンプレート クラスは、テンプレート パラメーターに依存する、入力ストリーム([basic_istream](../standard-library/basic-istream-class.md) テンプレート クラス) と出力ストリーム ([basic_ostream](../standard-library/basic-ostream-class.md) テンプレート クラス) の両方に共通のストレージとメンバー関数を表します。 (クラス [ios_base](../standard-library/ios-base-class.md) は、テンプレート パラメーターに依存しない、共通の要素を記述します。)クラス **basic_ios\<class Elem, class Traits>** のオブジェクトは、**Elem** 型の要素を含むストリームを制御するのに役立ちます。この型の特性は **Traits** クラスによって決まります。  
  
## <a name="syntax"></a>構文  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>パラメーター  
 `Elem`  
 型。  
  
 `Traits`  
 `char_traits` 型の変数。  
  
## <a name="remarks"></a>コメント  
 **basic_ios\<class Elem, class Traits>** クラスのオブジェクトは以下を格納します。  
  
-   [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>** 型のオブジェクトを指し示すリンク付けポインター。  
  
-   [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >** 型のオブジェクトを指し示すストリーム バッファー ポインター。  
  
- [書式設定情報](../standard-library/ios-base-class.md)。  
  
- [ios_base](../standard-library/ios-base-class.md) 型のベース オブジェクトの[ストリームの状態情報](../standard-library/ios-base-class.md)。  
  
-   `char_type` 型のオブジェクトの充てん文字。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_ios](#basic_ios__basic_ios)|`basic_ios` クラスを構築します。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#basic_ios__char_type)|テンプレート パラメーター `Elem` のシノニム。|  
|[int_type](#basic_ios__int_type)|`Traits::int_type` と同義。|  
|[off_type](#basic_ios__off_type)|`Traits::off_type` と同義。|  
|[pos_type](#basic_ios__pos_type)|`Traits::pos_type` と同義。|  
|[traits_type](#basic_ios__traits_type)|テンプレート パラメーター `Traits` のシノニム。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[bad](#basic_ios__bad)|ストリーム バッファーの整合性の損失を示します。|  
|[clear](#basic_ios__clear)|すべてのエラー フラグをクリアします。|  
|[copyfmt](#basic_ios__copyfmt)|1 つのストリームから別のストリームにフラグをコピーします。|  
|[eof](#basic_ios__eof)|ストリームの末尾に達しているかどうかを示します。|  
|[exceptions](#basic_ios__exceptions)|ストリームによってどの例外がスローされるかを示します。|  
|[fail](#basic_ios__fail)|ストリームからの有効フィールドの抽出エラーを示します。|  
|[fill](#basic_ios__fill)|テキストがストリームの幅に満たない場合に使用される文字を指定するか、返します。|  
|[good](#basic_ios__good)|ストリームの状態が良好であることを示します。|  
|[imbue](#basic_ios__imbue)|ロケールを変更します。|  
|[init](#basic_ios__init)|`basic_ios` コンストラクターによって呼び出されます。|  
|[move](#basic_ios__move)|ストリーム バッファーへのポインターを除くすべての値を、パラメーターから現在のオブジェクトに移動します。|  
|[narrow](#basic_ios__narrow)|指定された `char_type` と同等の文字を検索します。|  
|[rdbuf](#basic_ios__rdbuf)|指定したバッファーにストリームをルーティングします。|  
|[rdstate](#basic_ios__rdstate)|フラグのビットの状態を読み取ります。|  
|[set_rdbuf](#basic_ios__set_rdbuf)|ストリーム バッファーを割り当てて、このストリーム オブジェクトの読み取りバッファーとして使用します。|  
|[setstate](#basic_ios__setstate)|追加のフラグを設定します。|  
|[swap](#basic_ios__swap)|`basic_ios` オブジェクトの値を別の `basic_ios` オブジェクトの値と交換します。 ストリーム バッファーへのポインターは交換されません。|  
|[tie](#basic_ios__tie)|1 つのストリームが別のストリームの前に処理されるようにします。|  
|[widen](#basic_ios__widen)|指定された char と同等の `char_type` を検索します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[explicit operator bool](#basic_ios__operator_bool)|`basic_ios` オブジェクトを `bool` として使用できるようにします。 しばしば発生する意図しない副作用を防ぐため、自動型変換は無効になっています。|  
|[operator void *](#basic_ios__operator_void_star)|ストリームが依然として良好かどうかを示します。|  
|[operator!](#basic_ios__operator_not)|ストリームが悪化していないかどうかを示します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<ios>  
  
 **名前空間:** std  
  
##  <a name="a-namebasiciosbada--basiciosbad"></a><a name="basic_ios__bad"></a>  basic_ios::bad  
 ストリーム バッファーの整合性の損失を示します。  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>戻り値  
 `rdstate & badbit` が&0; 以外の場合は `true`、それ以外の場合は `false`。  
  
 `badbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照してください。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosbasiciosa--basiciosbasicios"></a><a name="basic_ios__basic_ios"></a>  basic_ios::basic_ios  
 basic_ios クラスを構築します。  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>パラメーター  
 `sb`  
 入力要素または出力要素を格納する標準のバッファー。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターは、[init](#basic_ios__init)(_ *Sb*) を呼び出すことによってそのメンバー オブジェクトを初期化します。 2 つ目の (保護された) コンストラクターは、そのメンバー オブジェクトを初期化前の状態のままにします。 以降の **init** への呼び出しは、オブジェクトを安全に破棄する前に、初期化する必要があります。  
  
##  <a name="a-namebasicioschartypea--basicioschartype"></a><a name="basic_ios__char_type"></a>  basic_ios::char_type  
 テンプレート パラメーター **Elem** のシノニム。  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="a-namebasicioscleara--basiciosclear"></a><a name="basic_ios__clear"></a>  basic_ios::clear  
 すべてのエラー フラグをクリアします。  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>パラメーター  
 `state` (省略可能)  
 すべてのフラグをクリアした後に設定するフラグ。 既定値は `goodbit` です。  
  
 `reraise` (省略可能)  
 例外を再発生させるかどうかを指定します。 既定値は `false` (例外を再発生させない) です。  
  
### <a name="remarks"></a>コメント  
 フラグは **goodbit**、**failbit**、**eofbit**、および **badbit** です。 [good](#basic_ios__good)、[bad](#basic_ios__bad)、[eof](#basic_ios__eof)、および [fail](#basic_ios__fail) で、これらのフラグをテストします。  
  
 このメンバー関数は、格納されているストリームの状態情報を次のものに置き換えます。  
  
 `state` &#124; `(`[rdbuf](#basic_ios__rdbuf) != 0 **goodbit** : **badbit**)  
  
 `state`**&**[exceptions](#basic_ios__exceptions) が&0; 以外の場合、[failure](../standard-library/ios-base-class.md#ios_base__failure) クラスのオブジェクトをスローします。  
  
### <a name="example"></a>例  
  **clear** の使用例については、「[rdstate](#basic_ios__rdstate)」と「[getline](../standard-library/string-functions.md#getline)」を参照してください。  
  
##  <a name="a-namebasicioscopyfmta--basicioscopyfmt"></a><a name="basic_ios__copyfmt"></a>  basic_ios::copyfmt  
 1 つのストリームから別のストリームにフラグをコピーします。  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 フラグをコピーするストリーム。  
  
### <a name="return-value"></a>戻り値  
 フラグをコピーするストリームの **this** オブジェクト。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、コールバック イベント erase_event を報告します。 その後、` right` から **\*this** に充填文字、リンク付けポインター、および書式設定情報をコピーします。 例外マスクを変更する前に、コールバック イベント copyfmt_event を報告します。 コピーの完了後、**state &**[exceptions](#basic_ios__exceptions) が&0; 以外の場合、関数は引数 [rdstate](#basic_ios__rdstate) を使って効果的に [clear](#basic_ios__clear) を呼び出します。 **\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="a-namebasicioseofa--basicioseof"></a><a name="basic_ios__eof"></a>  basic_ios::eof  
 ストリームの末尾に達しているかどうかを示します。  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>戻り値  
 ストリームの末尾に達している場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
 [rdstate](#basic_ios__rdstate) `& eofbit` が&0; 以外の場合、メンバー関数は `true` を返します。 `eofbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照してください。  
  
### <a name="example"></a>例  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosexceptionsa--basiciosexceptions"></a><a name="basic_ios__exceptions"></a>  basic_ios::exceptions  
 ストリームによってどの例外がスローされるかを示します。  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>パラメーター  
 *Newexcept*  
 例外をスローするフラグ。  
  
### <a name="return-value"></a>戻り値  
 ストリームに対して例外をスローするように現在指定されているフラグ。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、格納されている例外マスクを返します。 2 つ目のメンバー関数は、*_Except* を例外マスクに格納し、その前に格納されていた値を返します。 新しい例外マスクを格納することで、[clear](#basic_ios__clear)( [rdstate](#basic_ios__rdstate) ) の呼び出しと同じように例外をスローできます。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="a-namebasiciosfaila--basiciosfail"></a><a name="basic_ios__fail"></a>  basic_ios::fail  
 ストリームからの有効フィールドの抽出エラーを示します。  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>戻り値  
 [rdstate](#basic_ios__rdstate) `& (badbit|failbit)` が&0; 以外の場合は `true`、それ以外の場合は `false`。  
  
 `failbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照してください。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosfilla--basiciosfill"></a><a name="basic_ios__fill"></a>  basic_ios::fill  
 テキストがストリームの幅に満たない場合に使用される文字を指定するか、返します。  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>パラメーター  
 `Char`  
 充填文字として必要な文字。  
  
### <a name="return-value"></a>戻り値  
 現在の充填文字。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、格納されている充填文字を返します。 2 つ目のメンバー関数は、`Char` を充填文字に格納し、その前に格納されていた値を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="a-namebasiciosgooda--basiciosgood"></a><a name="basic_ios__good"></a>  basic_ios::good  
 ストリームの状態が良好であることを示します。  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>戻り値  
 [rdstate](#basic_ios__rdstate) `== goodbit` (設定されている状態フラグがない) 場合は `true`、それ以外の場合は `false`。  
  
 `goodbit` の詳細については、「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照してください。  
  
### <a name="example"></a>例  
  `good` の使用例については、「[basic_ios::bad](#basic_ios__bad)」を参照してください。  
  
##  <a name="a-namebasiciosimbuea--basiciosimbue"></a><a name="basic_ios__imbue"></a>  basic_ios::imbue  
 ロケールを変更します。  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>パラメーター  
 `Loc`  
 ロケールの文字列。  
  
### <a name="return-value"></a>戻り値  
 以前のロケール。  
  
### <a name="remarks"></a>コメント  
 [rdbuf](#basic_ios__rdbuf) が Null ポインターではない場合、メンバー関数は以下を呼び出します。  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#basic_streambuf__pubimbue)(_ *Loc*)  
  
 いずれの場合も、[ios_base::imbue](../standard-library/ios-base-class.md#ios_base__imbue)(_ *Loc*) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosinita--basiciosinit"></a><a name="basic_ios__init"></a>  basic_ios::init  
 basic_ios コンストラクターによって呼び出されます。  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Sb`  
 入力要素または出力要素を格納する標準のバッファー。  
  
 `_Isstd`  
 これが標準のストリームかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、以下のようにするため、すべてのメンバー オブジェクトに値を格納します。  
  
- [rdbuf](#basic_ios__rdbuf) が *_Sb* を返す。  
  
- [tie](#basic_ios__tie) が Null ポインターを返す。  
  
- `_Sb` が&0; 以外の場合に [rdstate](#basic_ios__rdstate) が [goodbit](../standard-library/ios-base-class.md#ios_base__iostate) を返し、それ以外の場合には [badbit](../standard-library/ios-base-class.md#ios_base__iostate) を返す。  
  
- [exceptions](#basic_ios__exceptions) が **goodbit** を返す。  
  
- [flags](../standard-library/ios-base-class.md#ios_base__flags) が [skipws](../standard-library/ios-base-class.md#ios_base__fmtflags) &#124; [dec](../standard-library/ios-base-class.md#ios_base__fmtflags) を返す。  
  
- [width](../standard-library/ios-base-class.md#ios_base__width) が 0 を返す。  
  
- [precision](../standard-library/ios-base-class.md#ios_base__precision) が 6 を返す。  
  
- [fill](#basic_ios__fill) が空白文字を返す。  
  
- [getloc](../standard-library/ios-base-class.md#ios_base__getloc) が `locale::classic` を返す。  
  
- [iword](../standard-library/ios-base-class.md#ios_base__iword) が&0; を返し、[pword](../standard-library/ios-base-class.md#ios_base__pword) がすべての引数値に Null ポインターを返す。  
  
##  <a name="a-namebasiciosinttypea--basiciosinttype"></a><a name="basic_ios__int_type"></a>  basic_ios::int_type  
 **traits_type::int_type** のシノニム。  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="a-namebasiciosmovea--basiciosmove"></a><a name="basic_ios__move"></a>  basic_ios::move  
 ストリーム バッファーへのポインターを除くすべての値を、パラメーターから現在のオブジェクトに移動します。  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 値の移動元となる `ios_base` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロテクト メンバー関数は、` right` に格納されているすべての値を `*this` に移動します。ただし、格納されている `stream buffer pointer` は除きます。これは、` right` で変更されず、`*this` で Null ポインターに設定されます。 格納されている `tie pointer` は ` right` で Null ポインターに設定されます。  
  
##  <a name="a-namebasiciosnarrowa--basiciosnarrow"></a><a name="basic_ios__narrow"></a>  basic_ios::narrow  
 指定された `char_type` と同等の文字を検索します。  
  
```  
 
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Char`  
 変換対象の `char`。  
  
 `Default`  
 同等のものが見つからない場合に返す `char`。  
  
### <a name="return-value"></a>戻り値  
 指定された `char_type` と同等の `char`。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<** **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)( ) ). `narrow`( `Char`, `Default`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosofftypea--basiciosofftype"></a><a name="basic_ios__off_type"></a>  basic_ios::off_type  
 **traits_type::off_type** のシノニム。  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="a-namebasiciosoperatorvoidstara--basiciosoperator-void-"></a><a name="basic_ios__operator_void_star"></a>  basic_ios::operator void *  
 ストリームが依然として良好かどうかを示します。  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>戻り値  
 演算子は [fail](#basic_ios__fail) の場合にのみ Null ポインターを返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="a-namebasiciosoperatornota--basiciosoperator"></a><a name="basic_ios__operator_not"></a>  basic_ios::operator!  
 ストリームが悪化していないかどうかを示します。  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>戻り値  
 [fail](#basic_ios__fail) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="a-namebasiciosoperatorboola--basiciosoperator-bool"></a><a name="basic_ios__operator_bool"></a>  basic_ios::operator bool  
 `basic_ios` オブジェクトを `bool` として使用できるようにします。 しばしば発生する意図しない副作用を防ぐため、自動型変換は無効になっています。  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>コメント  
 この演算子は、`fail``()` の場合にのみ `false` に変換可能な値を返します。 戻り値の型は、`void *` またはその他の既知のスカラー型ではなく、`bool` 型にのみ変換可能です。  
  
##  <a name="a-namebasiciospostypea--basiciospostype"></a><a name="basic_ios__pos_type"></a>  basic_ios::pos_type  
 **traits_type::pos_type** のシノニム。  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="a-namebasiciosrdbufa--basiciosrdbuf"></a><a name="basic_ios__rdbuf"></a>  basic_ios::rdbuf  
 指定したバッファーにストリームをルーティングします。  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Sb`  
 ストリーム。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は、格納されているストリーム バッファー ポインターを返します。  
  
 2 つ目のメンバー関数は、`_Sb` を格納されているストリーム バッファー ポインターに格納し、その前に格納されていた値を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="a-namebasiciosrdstatea--basiciosrdstate"></a><a name="basic_ios__rdstate"></a>  basic_ios::rdstate  
 フラグのビットの状態を読み取ります。  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納されているストリームの状態情報。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="a-namebasiciossetstatea--basiciossetstate"></a><a name="basic_ios__setstate"></a>  basic_ios::setstate  
 追加のフラグを設定します。  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 設定する追加のフラグ。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は効果的に [clear](#basic_ios__clear)(_ *State* &#124; [rdstate](#basic_ios__rdstate)) を呼び出します。  
  
### <a name="example"></a>例  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="a-namebasiciossetrdbufa--basiciossetrdbuf"></a><a name="basic_ios__set_rdbuf"></a>  basic_ios::set_rdbuf  
 ストリーム バッファーを割り当てて、このストリーム オブジェクトの読み取りバッファーとして使用します。  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>パラメーター  
 ` strbuf`  
 読み取りバッファーになるストリーム バッファー。  
  
### <a name="remarks"></a>コメント  
 プロテクト メンバー関数は、` strbuf` を `stream buffer pointer` に格納します。`clear` は呼び出しません。  
  
##  <a name="a-namebasiciostiea--basiciostie"></a><a name="basic_ios__tie"></a>  basic_ios::tie  
 1 つのストリームが別のストリームの前に処理されるようにします。  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>パラメーター  
 ` str`  
 ストリーム。  
  
### <a name="return-value"></a>戻り値  
 1 つ目のメンバー関数は、格納されているリンク付けポインターを返します。 2 つ目のメンバー関数は、` str` をリンク付けポインターに格納し、その前に格納されていた値を返します。  
  
### <a name="remarks"></a>コメント  
 `tie` は&2; つのストリームを同期させて、一方のストリームでの操作が完了すると、もう一方のストリームで操作が行われるようにします。  
  
### <a name="example"></a>例  
  この例では、cout に cin にリンクすることで、"Enter a number:" 文字列がコンソールに移動した後で、数字が cin から抽出されることを保証します。 これにより、数値の読み取り時に "Enter a number:" 文字列がバッファーにまだ残っている可能性を排除して、ユーザーが応答するプロンプトが必ずいくつかあるようにします。 既定では、cin と cout は関連付けられています。  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="a-namebasiciostraitstypea--basiciostraitstype"></a><a name="basic_ios__traits_type"></a>  basic_ios::traits_type  
 テンプレート パラメーター **Traits** のシノニム。  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="a-namebasicioswidena--basicioswiden"></a><a name="basic_ios__widen"></a>  basic_ios::widen  
 指定された `char` と同等の `char_type` を検索します。  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `Char`  
 変換する文字。  
  
### <a name="return-value"></a>戻り値  
 指定された `char` と同等の `char_type` を検索します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)) を返します。 `widen`( `Char`).  
  
### <a name="example"></a>例  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosswapa--basiciosswap"></a><a name="basic_ios__swap"></a>  basic_ios::swap  
 `basic_ios` オブジェクトの値を別の `basic_ios` オブジェクトの値と交換します。 ただし、ストリーム バッファーへのポインターは交換されません。  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 `right`  
 値を交換するために使用される `basic_ios` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロテクト メンバー関数は、格納されている `stream buffer pointer` を除き、` right` に格納されているすべての値を `*this` と交換します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)


