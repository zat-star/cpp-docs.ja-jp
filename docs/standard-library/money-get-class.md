---
title: "money_get クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocmon/std::money_get"
  - "money_get"
  - "std.money_get"
  - "std::money_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_get クラス"
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# money_get クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、`CharType` 型のシーケンスから通貨値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class money_get : public locale::facet;
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
 `InputIterator`  
 get 関数が入力を読み取る反復子の型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 **id。**  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[money_get](#money_get__money_get)|通貨値を表すシーケンスから数値を抽出するために使用される `money_get` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[char_type](#money_get__char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[iter_type](#money_get__iter_type)|入力反復子を表す型。|  
|[string_type](#money_get__string_type)|`CharType` 型の文字を格納する文字列を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[do_get](#money_get__do_get)|通貨値を表す文字シーケンスから数値を抽出するために呼び出される仮想関数。|  
|[取得](#money_get__get)|通貨値を表す文字シーケンスから数値を抽出します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namemoneygetchartypea-moneygetchartype"></a><a name="money_get__char_type"></a>  money_get::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **CharType**します。  
  
##  <a name="a-namemoneygetdogeta-moneygetdoget"></a><a name="money_get__do_get"></a>  money_get::do_get  
 呼び出される仮想関数では、通貨の値を表す文字シーケンスから数値を抽出します。  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const
```  
  
### <a name="parameters"></a>パラメーター  
 `first`  
 変換するシーケンスの先頭を示す反復子を入力します。  
  
 `last`  
 変換するシーケンスの末尾を示す入力反復子。  
  
 `_Intl`  
 シーケンスで期待される通貨記号の種類を示すブール値: **true** 場合は、国際的な **false** 国内場合。  
  
 `_Iosbase`  
 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要です。  
  
 `_State`  
 操作が成功か失敗かどうかに従ってストリームの状態の適切なビットマスクの要素を設定します。  
  
 `val`  
 変換後のシーケンスを格納する文字列。  
  
### <a name="return-value"></a>戻り値  
 通貨入力フィールドの最初の要素を示す入力反復子。  
  
### <a name="remarks"></a>コメント  
 1 つ目の仮想の保護されたメンバー関数は、シーケンスの先頭から始まる連続した要素を照合しようとしています [ `first`, 、`last`) nonempty 通貨入力フィールドであることを認識する完全なまでです。 かどうかは成功すると、このフィールドに変換、一連の 1 つまたは複数 10 進数字、マイナス記号に続く ( `–`) を表すで結果を格納し、 [string_type](#money_get__string_type) オブジェクト `val`します。 通貨入力フィールドの最初の要素を指定する反復子を返します。 関数がで空のシーケンスを格納する場合は、 `val` 設定と `ios_base::failbit` で `_State`します。 任意のプレフィックスの有効な通貨入力フィールドの最初の要素を指定する反復子を返します。 いずれの場合、戻り値と等しい場合 `last`, 、関数のセット `ios_base::eofbit` で `_State`します。  
  
 2 つ目の仮想の保護されたメンバー関数と同様に動作、1 つ目は、型の値を必要に応じて符号付き数値シーケンス正常終了した場合に変換する点を除いて `long double` でその値を格納および `val`です。  
  
 通貨入力フィールドの形式はによって決まります、 [ロケールのファセット](../standard-library/locale-class.md#facet_class)**要素** 効果的な呼び出しで返される [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../Topic/moneypunct%20Class.md)\< **CharType**, 、**intl**>> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。  
  
 具体的には、次のように使用します。  
  
- **要素**します。 [neg_format](../Topic/moneypunct%20Class.md#moneypunct__neg_format) フィールドのコンポーネントが出現する順序を決定します。  
  
- **要素**します。 [curr_symbol](../Topic/moneypunct%20Class.md#moneypunct__curr_symbol) 通貨記号を構成する要素のシーケンスを決定します。  
  
- **要素**します。 [positive_sign](../Topic/moneypunct%20Class.md#moneypunct__positive_sign) 正の符号を構成する要素のシーケンスを決定します。  
  
- **要素**します。 [negative_sign](../Topic/moneypunct%20Class.md#moneypunct__negative_sign) 負の符号を構成する要素のシーケンスを決定します。  
  
- **要素**します。 [グループ化](../Topic/moneypunct%20Class.md#moneypunct__grouping) 数字が小数点の左側にグループ化方法を決定します。  
  
- **要素**します。 [thousands_sep](../Topic/moneypunct%20Class.md#moneypunct__thousands_sep) 、小数点の左側にある数字のグループを区切る要素を調べます。  
  
- **要素**します。 [decimal_point](../Topic/moneypunct%20Class.md#moneypunct__decimal_point) を小数点以下桁数の整数部の桁数を区切る要素を調べます。  
  
- **要素**します。 [frac_digits](../Topic/moneypunct%20Class.md#moneypunct__frac_digits) 、小数点の右側にある重要な部分数字の数を決定します。 小数桁数を超えるに対して呼び出されると金額を解析するときに `frac_digits`, 、`do_get` 多くてに消費した解析を停止します `frac_digits` 文字です。  
  
 場合、記号の文字列 ( **要素**します。 `negative_sign` または **要素**します。 `positive_sign`) が 1 つ以上の要素である最初の要素のみが一致すると、要素と等しい **money_base::sign** フォーマット パターンが表示されます ( **要素**します。 `neg_format`) 残りの要素は、通貨入力フィールドの末尾に一致します。 どちらの文字列に通貨入力フィールド内の次の要素に一致する最初の要素がある場合は、記号の文字列が空としては取得され、符号が正の値。  
  
 場合 **iosbase**します。 [フラグ](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) 0 以外の場合、文字列 **要素**します。 `curr_symbol` 場所に一致する必要があります、要素と等しい **money_base::symbol** フォーマット パターンが表示されます。 それ以外の場合 **money_base::symbol** フォーマット パターンでの最後に発生し、照合するために署名文字列の要素が残っていない場合、通貨記号が一致しません。 それ以外の場合、通貨記号は必要に応じて一致します。  
  
 インスタンスがない場合 **要素**します。 `thousands_sep` 通貨入力フィールドの値の部分で発生する (場所と等しい要素 **money_base::value** フォーマット パターンが表示されます)、グループ化の制約は適用されません。 によって、グループ化の制約が課されるそれ以外の場合、 **要素**します。 **グループ化** が適用されます。 結果の数字のシーケンスを表します整数の下位 **要素**します。 `frac_digits` 小数点以下桁数、小数点の右側と見なされます。  
  
 任意の空白文字が一致すると、要素と等しい **money_base::space** 形式パターンの末尾に表示される以外の場合は、書式パターンに表示されます。 それ以外の場合、内部の空白文字は一致しませんでした。 要素 *ch* 場合に、空白文字と見なされますが [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [ctype](../standard-library/ctype-class.md)\< **CharType**>> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。 [](../standard-library/ctype-class.md#ctype__is "ctype Class")( **ctype_base::space**, 、*ch*) は **true**します。  
  
### <a name="example"></a>例  
  例を参照してください [取得](#money_get__get), 、どの呼び出し `do_get`します。  
  
##  <a name="a-namemoneygetgeta-moneygetget"></a><a name="money_get__get"></a>  money_get::get  
 通貨値を表す文字シーケンスから数値を抽出します。  
  
```
iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `first`  
 変換するシーケンスの先頭を示す反復子を入力します。  
  
 `last`  
 変換するシーケンスの末尾を示す入力反復子。  
  
 `_Intl`  
 シーケンスで期待される通貨記号の種類を示すブール値: **true** 場合は、国際的な **false** 国内場合。  
  
 `_Iosbase`  
 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要  
  
 `_State`  
 操作が成功したかどうかに従ってストリームの状態の適切なビットマスクの要素を設定します。  
  
 `val`  
 変換後のシーケンスを格納する文字列。  
  
### <a name="return-value"></a>戻り値  
 通貨入力フィールドの最初の要素を示す入力反復子。  
  
### <a name="remarks"></a>コメント  
 両方のメンバー関数が返す [do_get](#money_get__do_get)( `first``,` `last``,` `_Intl`, 、`_Iosbase`, 、`_State`, 、`val`)。  
  
### <a name="example"></a>例  
  
```  
// money_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream< char > psz;  
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";  
   basic_stringstream< char > psz2;  
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();  
  
   ios_base::iostate st = 0;  
   long double fVal;  
  
   psz.flags( psz.flags( )|ios_base::showbase );   
   // Which forced the READING the currency symbol  
   psz.imbue(loc);  
   use_facet < money_get < char > >( loc ).  
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),     
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"  
           << endl;  
   else  
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "   
           << fVal/100.0 << endl;  
  
   use_facet < money_get < char > >( loc ).  
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),     
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"   
           << endl;  
   else  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "   
           << fVal/100.0 << endl;  
};  
```  
  
##  <a name="a-namemoneygetitertypea-moneygetitertype"></a><a name="money_get__iter_type"></a>  money_get::iter_type  
 入力反復子を表す型。  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **InputIterator**します。  
  
##  <a name="a-namemoneygetmoneygeta-moneygetmoneyget"></a><a name="money_get__money_get"></a>  money_get::money_get  
 通貨値を表すシーケンスから数値を抽出するために使用される `money_get` 型のオブジェクトのコンストラクター。  
  
```
explicit money_get(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理の種類を指定するために使用する整数値です。  
  
### <a name="remarks"></a>コメント  
 ような値、 `_Refs` パラメーターとその重要性は。  
  
-   0: オブジェクトの有効期間はそれを含むロケールで管理します。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \> 0: これらの値が定義されていません。  
  
 直接例することはできません、デストラクターが保護されているためです。  
  
 コンス トラクターは、そのベース オブジェクトと **ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)( **_***Refs*)。  
  
##  <a name="a-namemoneygetstringtypea-moneygetstringtype"></a><a name="money_get__string_type"></a>  money_get::string_type  
 型の文字を含む文字列を表す型 **CharType**します。  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート クラスの特殊化を表します。 [basic_string](../standard-library/basic-string-class.md)します。  
  
## <a name="see-also"></a>関連項目  
 [\< ロケール>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



