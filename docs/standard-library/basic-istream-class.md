---
title: "basic_istream クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_istream
- istream/std::basic_istream
- std::basic_istream
- std.basic_istream
dev_langs:
- C++
helpviewer_keywords:
- basic_istream class
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
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
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 32308d4cd6a3cc1409f04958dde8dad9204718bc
ms.lasthandoff: 02/24/2017

---
# <a name="basicistream-class"></a>basic_istream クラス
`Elem` 型の要素を含むストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。この型は [char_type](../standard-library/basic-ios-class.md#basic_ios__char_type) とも呼ばれ、その文字特性は、[traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type) とも呼ばれるクラス *Tr* によって決定されます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_istream : virtual public basic_ios<Elem, Tr>  
```  
  
## <a name="remarks"></a>コメント  
 [operator>>](#basic_istream__operator_gt__gt_) をオーバーロードするメンバー関数のほとんどは、書式設定された入力関数です。 これらは以下のパターンに従います。  
  
```cpp  
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```  
  
 その他のメンバー関数の多くは、書式が設定されていない入力関数です。 これらは以下のパターンに従います。  
  
```cpp  
iostate state = goodbit;
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```  
  
 要素の抽出中にファイルの終わりに到達した場合、どちらの関数グループも [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) を呼び出します。  
  
 クラス `basic_istream`< `Elem`, *Tr*> のオブジェクトは次のものを格納します。  
  
-   クラス [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, *Tr*> `.` の仮想パブリック基本オブジェクト  
  
-   最後の書式設定されていない入力操作の抽出カウント (以前のコードで **count** と呼ばれていたもの)。  
  
## <a name="example"></a>例  
 入力ストリームの詳細は、[basic_ifstream クラス](../standard-library/basic-ifstream-class.md)の例を参照してください。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[basic_istream](#basic_istream__basic_istream)|`basic_istream` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[gcount](#basic_istream__gcount)|書式設定されていない最後の入力中に読まれた文字数を返します。|  
|[get](#basic_istream__get)|入力ストリームから&1; つ以上の文字を読み取ります。|  
|[getline](#basic_istream__getline)|入力ストリームから行を読み取ります。|  
|[ignore](#basic_istream__ignore)|複数の要素を、現在読み取った位置からスキップさせます。|  
|[peek](#basic_istream__peek)|読み取る次の文字を返します。|  
|[putback](#basic_istream__putback)|ストリームに指定された文字を配置します。|  
|[read](#basic_istream__read)|指定された数の文字をストリームから読み取り、配列に保存します。|  
|[readsome](#basic_istream__readsome)|バッファーからのみ読み取ります。|  
|[seekg](#basic_istream__seekg)|ストリームでの読み取り位置を移動させます。|  
|[sentry](#basic_istream__sentry)|この入れ子になったクラスは、オブジェクトの宣言が書式設定された入力関数と書式設定されていない入力関数を構築するオブジェクトについて記述します。|  
|[swap](#basic_istream__swap)|この `basic_istream` オブジェクトを、指定した `basic_istream` オブジェクト パラメーターと交換します。|  
|[sync](#basic_istream__sync)|ストリームのバッファー付のストリームと関連付けられている入力デバイスを同期します。|  
|[tellg](#basic_istream__tellg)|ストリーム内の現在の読み取り位置を報告します。|  
|[unget](#basic_istream__unget)|最後に読み取った文字をストリームに戻します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator>>](#basic_istream__operator_gt__gt_)|入力ストリームで関数を呼び出すか、または入力ストリームから書式設定されたデータを読み取ります。|  
|[operator=](#basic_istream__operator_eq)|演算子の右辺の `basic_istream` をこのオブジェクトに代入します。 これは、コピーを残さない `rvalue` 参照を伴う移動代入です。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<istream>  
  
 **名前空間:** std  
  
##  <a name="a-namebasicistreambasicistreama--basicistreambasicistream"></a><a name="basic_istream__basic_istream"></a>  basic_istream::basic_istream  
 `basic_istream` 型のオブジェクトを構築します。  
  
```  
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` strbuf`  
 [basic_streambuf](../standard-library/basic-streambuf-class.md) 型のオブジェクト。  
  
 `_Isstd`  
これが標準ストリームの場合は  `true`、それ以外の場合は `false`。  
  
 ` right`  
 コピーする `basic_istream` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 最初のコンストラクターが [init](../standard-library/basic-ios-class.md#basic_ios__init)(_S `trbuf`) を呼び出して基底クラスを初期化します。 ゼロも抽出カウントに格納されます。 この抽出カウントの詳細については、「[basic_istream クラス](../standard-library/basic-istream-class.md)」の概要トピックの「コメント」セクションを参照してください。  
  
 2 番目のコンストラクターが `move``( right)` を呼び出して基底クラスを初期化します。 _R `ight.gcount()` も抽出カウントに格納し、ゼロを _R `ight` の抽出カウントに格納します。  
  
### <a name="example"></a>例  
  入力ストリームの詳細は、[basic_ifstream::basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream__basic_ifstream) の例を参照してください。  
  
##  <a name="a-namebasicistreamgcounta--basicistreamgcount"></a><a name="basic_istream__gcount"></a>  basic_istream::gcount  
 書式設定されていない最後の入力中に読まれた文字数を返します。  
  
```  
streamsize gcount() const;
```  
  
### <a name="return-value"></a>戻り値  
 抽出カウント。  
  
### <a name="remarks"></a>コメント  
 書式設定されていない文字を読み取るには、[basic_istream::get](#basic_istream__get) を使用します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_gcount.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   cout << "Type the letter 'a': ";  
  
   ws( cin );  
   char c[10];  
  
   cin.get( &c[0],9 );  
   cout << c << endl;  
  
   cout << cin.gcount( ) << endl;  
}  
```  
  
```Output  
  
a  
  
```  
  
```Output  
  
      aType the letter 'a':  
a  
1  
```  
  
##  <a name="a-namebasicistreamgeta--basicistreamget"></a><a name="basic_istream__get"></a>  basic_istream::get  
 入力ストリームから&1; つ以上の文字を読み取ります。  
  
```  
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```  
  
### <a name="parameters"></a>パラメーター  
 ` count`  
 `strbuf` から読み取る文字の数。  
  
 `Delim`  
 ` count` の前に見つかった場合に、読み取りを終了する文字。  
  
 ` str`  
 書き込み先の文字列。  
  
 `Ch`  
 取得する文字。  
  
 ` strbuf`  
 書き込み先のバッファー。  
  
### <a name="return-value"></a>戻り値  
 get のパラメーターなしの形式は、整数またはファイルの終わりとして読み取られる要素を返します。 残りの形式はストリーム (* `this`) を返します。  
  
### <a name="remarks"></a>コメント  
 これらの書式設定されていない&1; 番目の入力関数は、可能であれば、`rdbuf`-> `sbumpc` を返す場合と同じように、要素を抽出します。 それ以外の場合は、**traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof) を返します。 関数が要素を抽出しなかった場合、[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。  
  
 2 番目の関数は、同じ方法で [int_type](../standard-library/basic-ios-class.md#basic_ios__int_type) 要素 `meta` を抽出します。 `meta` が **traits_type::eof** と等しい場合、関数は `setstate`( **failbit**) を呼び出します。 それ以外の場合は、**traits_type::**[to_char_type](../standard-library/char-traits-struct.md#char_traits__to_char_type)( `meta`) を `Ch` に格納します。 関数は **\*this** を返します。  
  
 3 番目の関数は、**get**(_ *Str*, ` count`, `widen`('\ **n**')) を返します。  
  
 4 番目の関数は、最大 ` count` - 1 の要素を抽出し、それらを _ *Str* で始まる配列に格納します。 これは格納する抽出した要素の後に常に `char_type` を格納します。 テストの順に抽出は停止します。  
  
-   ファイルの終わり。  
  
-   関数が `Delim` と等しい要素を抽出した後。この場合、抽出された要素が制御対象シーケンスに戻されます。  
  
-   関数が ` count` - 1 要素を抽出した後。  
  
 関数が要素を抽出しなかった場合、`setstate`( **failbit**) を呼び出します。 いずれの場合も、**\*this** を返します。  
  
 5 番目の関数は、**get**( **strbuf**, `widen`('\ **n**')) を返します。  
  
 6 番目の関数は、要素を抽出し、それらを **strbuf** に挿入します。 抽出は、ファイルの終わりまたは _ *Delim* と等しい要素で停止し、抽出はされません。 また、挿入が失敗した場合または (キャッチされるが再スローされない) 例外をスローする場合は、対象の要素を抽出せずに停止します。 関数が要素を抽出しなかった場合、`setstate`( **failbit**) を呼び出します。 いずれの場合も関数は **\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_get.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   c[0] = cin.get( );  
   cin.get( c[1] );  
   cin.get( &c[2],3 );  
   cin.get( &c[4], 4, '7' );  
  
   cout << c << endl;  
}  
```  
  
```Output  
  
1111  
```  
  
##  <a name="a-namebasicistreamgetlinea--basicistreamgetline"></a><a name="basic_istream__getline"></a>  basic_istream::getline  
 入力ストリームから行を取得します。  
  
```  
basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count,   
    char_type Delim);
```  
  
### <a name="parameters"></a>パラメーター  
 ` count`  
 **strbuf** から読み取る文字の数。  
  
 `Delim`  
 ` count` の前に見つかった場合に、読み取りを終了する文字。  
  
 ` str`  
 書き込み先の文字列。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 これらの書式設定されていない最初の入力関数は、**getline**(_ *Str*, ` count`, `widen`(' `\`**n**')) を返します。  
  
 2 番目の関数は、最大 ` count` - 1 の要素を抽出し、それらを _ *Str* で始まる配列に格納します。 これは格納する抽出した要素の後に常に文字列終端文字を格納します。 テストの順に抽出は停止します。  
  
-   ファイルの終わり。  
  
-   関数が `Delim` と等しい要素を抽出した場合。このとき、抽出された要素が制御対象シーケンスに戻されたり、追加されたりすることはありません。  
  
-   関数が ` count` - 1 要素を抽出した後。  
  
 関数が要素を抽出しなかった場合、または ` count` - 1 要素を抽出した場合、[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。 いずれの場合も、**\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_getline.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   cin.getline( &c[0], 5, '2' );  
   cout << c << endl;  
}  
```  
  
```Output  
  
121  
```  
  
##  <a name="a-namebasicistreamignorea--basicistreamignore"></a><a name="basic_istream__ignore"></a>  basic_istream::ignore  
 複数の要素を、現在読み取った位置からスキップさせます。  
  
```  
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,  
    int_type Delim = traits_type::eof());
```  
  
### <a name="parameters"></a>パラメーター  
 ` count`  
 現在の読み取り位置からスキップする要素の数。  
  
 `Delim`  
 カウントの前に出現した場合には **ignore** を返し、`Delim` の後のすべての要素の読み取りを許可する要素。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 書式設定されていない入力関数は、最大 ` count` の要素を抽出し、これらを破棄します。 ただし、` count` が **numeric_limits\<int>::max** と等しい場合、任意の大きさとして取得されます。 抽出は、**traits_type::**[to_int_type](../standard-library/char-traits-struct.md#char_traits__to_int_type)( `Ch`) が (同じく抽出された) _ *Delim* と等しくなるように、ファイルの終わりまたは要素 `Ch` の早い段階で停止します。 関数は **\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_ignore.cpp  
// compile with: /EHsc  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   char chararray[10];  
   cout << "Type 'abcdef': ";  
   cin.ignore( 5, 'c' );  
   cin >> chararray;  
   cout << chararray;  
}  
```  
  
```Output  
  
abcdef  
  
```  
  
```Output  
  
abcdefdef  
```  
  
##  <a name="a-namebasicistreamoperatorgtgta--basicistreamoperatorgtgt"></a><a name="basic_istream__operator_gt__gt_"></a>  basic_istream::operator&gt;&gt;
  
入力ストリームで関数を呼び出すか、または入力ストリームから書式設定されたデータを読み取ります。  
    
```  
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));  
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `Pfn`  
 関数ポインター。  
  
 ` strbuf`  
 **stream_buf** 型のオブジェクト。  
  
 ` val`  
 ストリームから読み取る値。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 `<istream>` ヘッダーは複数のグローバル抽出演算子も定義します。 詳細については、「[operator>> (\<istream>)](../standard-library/istream-operators.md#operator_gt__gt_)」を参照してください。  
  
 最初のメンバー関数は、**istr** >> `ws` 形式の式が [ws](../standard-library/istream-functions.md#ws)( **istr**) を呼び出し、**\*this** を返すことを保証します。 2 番目と&3; 番目の関数は、[hex](../standard-library/ios-functions.md#hex) などの他のマニピュレーターが同じように動作することを保証します。 残りの関数は、書式設定された入力関数を構成します。  
  
 関数:  
  
```  
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```  
  
 _ *Strbuf*が Null ポインターではない場合に、要素を抽出し、それらを ` strbuf` に挿入します。 抽出は、ファイルの終わりで停止します。 また、挿入が失敗した場合または (キャッチされるが再スローされない) 例外をスローする場合は、対象の要素を抽出せずに停止します。 関数が要素を抽出しなかった場合、[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。 いずれの場合も関数は **\*this** を返します。  
  
 関数:  
  
```  
basic_istream& operator>>(bool& val);
```  
  
 フィールドを抽出し、[use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [get](../standard-library/ios-base-class.md#ios_base__getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), `Init`(0), **\*this**, `getloc`, ` val`) を呼び出して、それをブール値に変換します。 ここで、**InIt** は [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**> として定義されます。 関数は **\*this** を返します。  
  
 関数:  
  
```  
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val); 
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val); 
basic_istream& operator>>(void *& val);
```  
  
 それぞれがフィールドを抽出し、`use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). [get](#basic_istream__get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`) を呼び出して、それを数値に変換します。 ここで、**InIt** は `istreambuf_iterator`\< **Elem**, **Tr**> として定義され、必要に応じて ` val` に **long***、*`unsigned long`*、*、**void \*** のいずれかの型を指定します。  
  
 変換後の値を ` val` の型として表すことができない場合、関数は [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。 いずれの場合も関数は **\*this** を返します。  
  
 関数:  
  
```  
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
 それぞれがフィールドを抽出し、`use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`) を呼び出して、それを数値に変換します。 ここで、**InIt** は `istreambuf_iterator`\< **Elem**, **Tr**> として定義され、必要に応じて ` val` に **double** または `long double` の型を指定します。  
  
 変換後の値を ` val` の型として表すことができない場合、関数は `setstate`( **failbit**) を呼び出します。 いずれの場合も、**\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// istream_basic_istream_op_is.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )   
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)  
{  
   if ( i == cin )   
   {  
      cerr << "i is cin" << endl;  
   }  
   return i;  
}  
  
int main( )   
{  
   int i = 0;  
   cin >> somefunc;  
   cin >> i;  
   cout << i << endl;  
   cin >> hex2;  
   cin >> i;  
   cout << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamoperatoreqa--basicistreamoperator"></a><a name="basic_istream__operator_eq"></a>  basic_istream::operator=  
 演算子の右辺の `basic_istream` をこのオブジェクトに代入します。 これは、コピーを残さない `rvalue` 参照を伴う移動代入です。  
  
```  
basic_istream& operator=(basic_istream&& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 `basic_ifstream` オブジェクトへの `rvalue` 参照。  
  
### <a name="return-value"></a>戻り値  
 *this を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー演算子は、swap `( right)` を呼び出します。  
  
##  <a name="a-namebasicistreampeeka--basicistreampeek"></a><a name="basic_istream__peek"></a>  basic_istream::peek  
 読み取る次の文字を返します。  
  
```  
int_type peek();
```  
  
### <a name="return-value"></a>戻り値  
 読み取る次の文字。  
  
### <a name="remarks"></a>コメント  
 これらの書式設定されていない入力関数は、可能であれば、`rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sgetc) を返すように、要素を抽出します。 それ以外の場合は、**traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_peek.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
   cout << "Type 'abcde': ";  
  
   c2 = cin.peek( );  
   cin.getline( &c[0], 9 );  
  
   cout << c2 << " " << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
a abcde  
```  
  
##  <a name="a-namebasicistreamputbacka--basicistreamputback"></a><a name="basic_istream__putback"></a>  basic_istream::putback  
 ストリームに指定された文字を配置します。  
  
```  
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```  
  
### <a name="parameters"></a>パラメーター  
 `Ch`  
 ストリームに戻す文字。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 [書式設定されていない入力関数](../standard-library/basic-istream-class.md)は、可能な場合には [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#basic_streambuf__sputbackc) を呼び出すのと同じように `Ch`を戻します。 rdbuf が Null ポインターの場合、または `sputbackc` への呼び出しが **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof) を返す場合、関数は [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**) を呼び出します。 いずれの場合も、**\*this** を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_putback.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2, c3;  
  
   c2 = cin.get( );  
   c3 = cin.get( );  
   cin.putback( c2 );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
qwq  
```  
  
##  <a name="a-namebasicistreamreada--basicistreamread"></a><a name="basic_istream__read"></a>  basic_istream::read  
 指定された数の文字をストリームから読み取り、配列に保存します。  
  
 渡された値が正しいことの確認を呼び出し元に依存するため、このメソッドは安全ではない可能性があります。  
  
```  
basic_istream<Elem, Tr>& read(
    char_type* str,   
    streamsize count);
```  
  
### <a name="parameters"></a>パラメーター  
 ` str`  
 文字の読み取り先の配列。  
  
 ` count`  
 読み取る文字の数。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( `*this`)。  
  
### <a name="remarks"></a>コメント  
 書式設定されていない入力関数は、最大 `count` の要素を抽出し、それらを _ `Str` で始まる配列に格納します。 抽出は、関数が [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( `failbit`) を呼び出す場合には、ファイルの終わりの早い段階で停止します。 いずれの場合も、`*this` を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_read.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    char c[10];  
    int count = 5;  
  
    cout << "Type 'abcde': ";  
  
    // Note: cin::read is potentially unsafe, consider  
    // using cin::_Read_s instead.  
    cin.read(&c[0], count);  
    c[count] = 0;  
  
    cout << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
abcde  
```  
  
##  <a name="a-namebasicistreamreadsomea--basicistreamreadsome"></a><a name="basic_istream__readsome"></a>  basic_istream::readsome  
 指定した文字の値の数を読み取ります。  
  
 渡された値が正しいことの確認を呼び出し元に依存するため、このメソッドは安全ではない可能性があります。  
  
```  
streamsize readsome(
    char_type* str,  
    streamsize count);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 `readsome` が読み取る文字を格納する配列。  
  
 `count`  
 読み取る文字の数。  
  
### <a name="return-value"></a>戻り値  
 実際に読み取った文字数、[gcount](#basic_istream__gcount)。  
  
### <a name="remarks"></a>コメント  
 この書式設定されていない入力関数は、最大 `count` の要素を入力ストリームから抽出し、それらを配列 `str` に格納します。  
  
 この関数は入力を待機しません。 使用できる任意のデータを読み取ります。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_readsome.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char c[10];  
   int count = 5;  
  
   cout << "Type 'abcdefgh': ";  
  
   // cin.read blocks until user types input.  
   // Note: cin::read is potentially unsafe, consider  
   // using cin::_Read_s instead.  
   cin.read(&c[0], 2);  
  
   // Note: cin::readsome is potentially unsafe, consider  
   // using cin::_Readsome_s instead.  
   int n = cin.readsome(&c[0], count);  // C4996  
   c[n] = 0;  
   cout << n << " characters read" << endl;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamseekga--basicistreamseekg"></a><a name="basic_istream__seekg"></a>  basic_istream::seekg  
 ストリームでの読み取り位置を移動させます。  
  
```  
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```  
  
### <a name="parameters"></a>パラメーター  
 `pos`  
 読み取りポインターの移動先の絶対位置。  
  
 `off`  
 `way` に対して相対的に読み取りポインターを移動するオフセット。  
  
 `way`  
 [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir) 列挙体のうちの&1; つ。  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 1 つ目のメンバー関数は絶対シークを実行し、2 つ目のメンバー関数は相対シークを実行します。  
  
> [!NOTE]
>  標準 C++ ではテキスト ファイルでの相対シークをサポートしていないため、2 つ目のメンバー関数をテキスト ファイルで使用しないでください。  
  
 [fail](../standard-library/basic-ios-class.md#basic_ios__fail) が false の場合、1 つ目のメンバー関数は、一部の**pos_type** の一時オブジェクト **newpos** に対し、**newpos** = [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)( `pos`) を呼び出します。 **fail** が false の場合、2 つ目の関数は **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)( `off`, `way`) を呼び出します。 いずれの場合も、( `off_type`) **newpos** == ( `off_type`)(-1) (位置指定操作が失敗) の場合、関数は **istr**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。 どちらの関数も **\*this** を返します。  
  
 [fail](../standard-library/basic-ios-class.md#basic_ios__fail) が true の場合、メンバー関数は何もしません。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_seekg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )   
{  
   using namespace std;  
   ifstream file;  
   char c, c1;  
  
   file.open( "basic_istream_seekg.txt" );  
   file.seekg(2);   // seek to position 2  
   file >> c;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamsentrya--basicistreamsentry"></a><a name="basic_istream__sentry"></a>  basic_istream::sentry  
 この入れ子になったクラスは、オブジェクトの宣言が書式設定された入力関数と書式設定されていない入力関数を構築するオブジェクトについて記述します。  
  
class sentry {  
   public:  
   explicit sentry( basic_istream\<Elem, Tr>& _Istr,  
   bool _Noskip = false); operator bool() const; };  
  
### <a name="remarks"></a>コメント  
 `_Istr``.`[good](../standard-library/basic-ios-class.md#basic_ios__good) が true の場合、コンストラクターは以下を実行します。  
  
-   `_Istr`. [tie](../standard-library/basic-ios-class.md#basic_ios__tie) -> [flush](../standard-library/basic-ostream-class.md#basic_ostream__flush) を呼び出す (`_Istr`. `tie` が Null ポインターでない場合)  
  
-   [ws](../standard-library/istream-functions.md#ws)( `_Istr`) を効果的に呼び出す (`_Istr`. [flags](../standard-library/ios-base-class.md#ios_base__flags)**&**[skipws](../standard-library/ios-functions.md#skipws) がゼロ以外の場合)  
  
 このような準備作業の後に、`_Istr`. **good** が false の場合、コンストラクターは `_Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**) を呼び出します。 いずれの場合も、コンストラクターは `_Istr`. **good** で返された値を **status** に格納します。 **operator bool** への以降の呼び出しは、格納されているこの値を提供します。  
  
##  <a name="a-namebasicistreamswapa--basicistreamswap"></a><a name="basic_istream__swap"></a>  basic_istream::swap  
 2 つの `basic_istream` オブジェクトの内容を交換します。  
  
```  
void swap(basic_istream& right);
```  
  
### <a name="parameters"></a>パラメーター  
 ` right`  
 `basic_istream` オブジェクトへの左辺値参照。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)` を呼び出します。 また、抽出カウントを ` right` の抽出カウントと交換します。  
  
##  <a name="a-namebasicistreamsynca--basicistreamsync"></a><a name="basic_istream__sync"></a>  basic_istream::sync  
 ストリームのバッファー付のストリームと関連付けられている入力デバイスを同期します。  
  
```  
int sync();
```  
  
### <a name="return-value"></a>戻り値  
 [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) が Null ポインターの場合、この関数は -1 を返します。 そうでない場合は、`rdbuf` -> [pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync) を呼び出します。 -1 を返す場合、関数は [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**)を呼び出して -1 を返します。 それ以外の場合、関数は&0; を返します。  
  
##  <a name="a-namebasicistreamtellga--basicistreamtellg"></a><a name="basic_istream__tellg"></a>  basic_istream::tellg  
 ストリーム内の現在の読み取り位置を報告します。  
  
```  
pos_type tellg();
```  
  
### <a name="return-value"></a>戻り値  
 ストリームの現在の位置。  
  
### <a name="remarks"></a>コメント  
 [fail](../standard-library/basic-ios-class.md#basic_ios__fail) が false の場合、メンバー関数は [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**) を返します。 それ以外の場合は、`pos_type`(-1) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_tellg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main()  
{  
    using namespace std;  
    ifstream file;  
    char c;  
    streamoff i;  
  
    file.open("basic_istream_tellg.txt");  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamungeta--basicistreamunget"></a><a name="basic_istream__unget"></a>  basic_istream::unget  
 最後に読み取った文字をストリームに戻します。  
  
```  
basic_istream<Elem, Tr>& unget();
```  
  
### <a name="return-value"></a>戻り値  
 ストリーム ( **\*this**)。  
  
### <a name="remarks"></a>コメント  
 [書式設定されていない入力関数](../standard-library/basic-istream-class.md)は、可能であれば、`rdbuf` -> [sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc) を呼び出した場合と同じように、前の要素をストリームに戻します。 [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) が Null ポインターの場合、または `sungetc` への呼び出しが **traits_type::**[eof](../standard-library/basic-ios-class.md#basic_ios__eof) を返す場合、関数は [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**) を呼び出します。 いずれの場合も、**\*this** を返します。  
  
 `unget` がどのように失敗する可能性があるかについては、「[basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc)」を参照してください。  
  
### <a name="example"></a>例  
  
```cpp  
// basic_istream_unget.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
  
   cout << "Type 'abc': ";  
   c2 = cin.get( );  
   cin.unget( );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
abc  
  
```  
  
```Output  
  
      abcType 'abc': abc  
abc  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)


