---
title: "money_put クラス | Microsoft Docs"
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
  - "std::money_put"
  - "xlocmon/std::money_put"
  - "money_put"
  - "std.money_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_put クラス"
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# money_put クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、通貨値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
 `OutputIterator`  
 通貨の put 関数が出力を書き込む反復子の型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 **id。**  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[money_put](#money_put__money_put)|`money_put` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[char_type](#money_put__char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[iter_type](#money_put__iter_type)|出力反復子を表す型。|  
|[string_type](#money_put__string_type)|`CharType` 型の文字を格納する文字列を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[do_put](#money_put__do_put)|通貨値を表す文字シーケンスから数値または文字列を抽出するために呼び出される仮想関数。|  
|[配置](#money_put__put)|数値または文字列を通貨値を表す文字シーケンスに変換します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namemoneyputchartypea-moneyputchartype"></a><a name="money_put__char_type"></a>  money_put::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **CharType**します。  
  
##  <a name="a-namemoneyputdoputa-moneyputdoput"></a><a name="money_put__do_put"></a>  money_put::do_put  
 通貨値を表す文字シーケンスから数値または文字列を抽出するために呼び出される仮想関数。  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` next`  
 挿入された文字列の最初の要素を示す反復子。  
  
 `_Intl`  
 シーケンスで期待される通貨記号の種類を示すブール値: **true** 場合は、国際的な **false** 国内場合。  
  
 `_Iosbase`  
 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要  
  
 `_Fill`  
 スペースのために使用される文字。  
  
 ` val`  
 変換する文字列オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 出力反復子アドレスは、最後の要素より後の位置 1 つ生成します。  
  
### <a name="remarks"></a>コメント  
 1 つ目の仮想の保護されたメンバー関数から始まる連続した要素を生成する ` next` から通貨出力フィールドを生成する、 [string_type](#money_put__string_type) オブジェクト ` val`します。 によって制御されるシーケンス ` val` 1 つまたは複数 10 進数の数字で、必要に応じて容量を表す負符号 (-) に続くを開始する必要があります。 関数は、生成された通貨出力フィールドを超える最初の要素を指定する反復子を返します。  
  
 2 番目の仮想の保護されたメンバー関数の動作を最初と同じことを除く効果的に最初に変換 ` val` マイナス記号に続く 10 進数字のシーケンスに変換上とその順序。  
  
 通貨出力フィールドの形式がによって決まりますが、 [ロケールのファセット](../standard-library/locale-class.md#facet_class) (有効) の呼び出しで返される要素 [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../Topic/moneypunct%20Class.md)\< **CharType**, 、**intl**>> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。  
  
 具体的には、次のように使用します。  
  
- **要素**します。 [pos_format](../Topic/moneypunct%20Class.md#moneypunct__pos_format) 負でない値のフィールドのコンポーネントを生成する順序を決定します。  
  
- **要素**します。 [neg_format](../Topic/moneypunct%20Class.md#moneypunct__neg_format) 負の値のフィールドのコンポーネントを生成する順序を決定します。  
  
- **要素**します。 [curr_symbol](../Topic/moneypunct%20Class.md#moneypunct__curr_symbol) 通貨記号を生成する要素のシーケンスを決定します。  
  
- **要素**します。 [positive_sign](../Topic/moneypunct%20Class.md#moneypunct__positive_sign) 正の符号を生成する要素のシーケンスを決定します。  
  
- **要素**します。 [negative_sign](../Topic/moneypunct%20Class.md#moneypunct__negative_sign) 負の符号を生成する要素のシーケンスを決定します。  
  
- **要素**します。 [グループ化](../Topic/moneypunct%20Class.md#moneypunct__grouping) 数字が小数点の左側にグループ化方法を決定します。  
  
- **要素**します。 [thousands_sep](../Topic/moneypunct%20Class.md#moneypunct__thousands_sep) 、小数点の左側にある数字のグループを区切る要素を調べます。  
  
- **要素**します。 [decimal_point](../Topic/moneypunct%20Class.md#moneypunct__decimal_point) 整数部の小数部を区切る要素を調べます。  
  
- **要素**します。 [frac_digits](../Topic/moneypunct%20Class.md#moneypunct__frac_digits) 、小数点の右側にある重要な部分数字の数を決定します。  
  
 場合、記号の文字列 ( **要素**します。 `negative_sign` または **要素**します。 `positive_sign`) が 1 つ以上の要素である最初の要素のみが生成される場所と等しい要素 **money_base::sign** フォーマット パターンが表示されます ( **要素**します。 `neg_format` または **要素**します。 `pos_format`) 通貨出力フィールドの末尾には、残りの要素が生成されます。  
  
 場合 **iosbase**します。 [フラグ](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) 0 以外の場合、文字列 **要素**します。 `curr_symbol` ここで生成される要素と等しい **money_base::symbol** フォーマット パターンが表示されます。 それ以外の場合、通貨記号は生成されません。  
  
 グループ化の制約が課せられなかった場合 **要素**します。 **グループ化** (先頭の要素値がある、CHAR_MAX) のインスタンス、 **要素**します。 `thousands_sep` 通貨出力フィールドの値の部分で生成されます (ここで要素と等しい **money_base::value** フォーマット パターンが表示されます)。 場合 **要素**します。 `frac_digits` インスタンスがされません **要素**します。 `decimal_point` 10 進数字の後に生成されます。 それ以外の場合、結果として得られる通貨出力フィールドに配置、下位 **要素**します。 `frac_digits` 小数点の右側に 10 進数字。  
  
 余白が似ているが、任意の数値の出力フィールドですが発生した **iosbase**します。 **フラグ** & **iosbase**します。 [内部](../Topic/%3Cios%3E%20functions.md#internal) 0 でないすべての内部の余白は、ここでは生成と等しい要素 **money_base::space** 表示する場合は、書式パターンに表示されます。 それ以外の場合、内部の余白は、生成されたシーケンスの前に発生します。 埋め込み文字が **塗りつぶし**します。  
  
 関数呼び出し **iosbase**します。 **幅**フィールドの幅をゼロにリセットするには、(0)。  
  
### <a name="example"></a>例  
  例を参照してください [配置](#money_put__put), が仮想メンバー関数ある場合、 **配置**します。  
  
##  <a name="a-namemoneyputitertypea-moneyputitertype"></a><a name="money_put__iter_type"></a>  money_put::iter_type  
 出力反復子を表す型。  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **OutputIterator します。**  
  
##  <a name="a-namemoneyputmoneyputa-moneyputmoneyput"></a><a name="money_put__money_put"></a>  money_put::money_put  
 `money_put` 型のオブジェクトのコンストラクター。  
  
```  
explicit money_put(size_t _Refs = 0);
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
  
 コンス トラクターは、そのベース オブジェクトと **ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)( `_Refs`)。  
  
##  <a name="a-namemoneyputputa-moneyputput"></a><a name="money_put__put"></a>  money_put::put  
 数値または文字列を通貨値を表す文字シーケンスに変換します。  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` next`  
 挿入された文字列の最初の要素を示す反復子。  
  
 `_Intl`  
 シーケンスで期待される通貨記号の種類を示すブール値: **true** 場合は、国際的な **false** 国内場合。  
  
 `_Iosbase`  
 形式にフラグを設定すると、セットは、通貨記号が省略可能ですであることを示します。それ以外の場合、これが必要  
  
 `_Fill`  
 スペースのために使用される文字。  
  
 ` val`  
 変換する文字列オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 出力反復子アドレスは、最後の要素より後の位置 1 つ生成します。  
  
### <a name="remarks"></a>コメント  
 両方のメンバー関数が返す [do_put](#money_put__do_put)( ` next`, 、`_Intl`, 、`_Iosbase`, 、`_Fill`, 、` val`)。  
  
### <a name="example"></a>例  
  
```  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="a-namemoneyputstringtypea-moneyputstringtype"></a><a name="money_put__string_type"></a>  money_put::string_type  
 型の文字を含む文字列を表す型 **CharType**します。  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート クラスの特殊化を表します。 [basic_string](../standard-library/basic-string-class.md) オブジェクトがソース シーケンスの要素のシーケンスを格納できます。  
  
## <a name="see-also"></a>関連項目  
 [\< ロケール>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

