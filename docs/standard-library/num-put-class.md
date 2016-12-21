---
title: "num_put クラス | Microsoft Docs"
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
  - "std::num_put"
  - "xlocnum/std::num_put"
  - "num_put"
  - "std.num_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_put クラス"
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# num_put クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

数値から `CharType` 型のシーケンスへの変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class num_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
 `OutputIterator`  
 数値 put 関数が出力を書き込む反復子の型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 **id。**  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[num_put](#num_put__num_put)|`num_put` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[char_type](#num_put__char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[iter_type](#num_put__iter_type)|出力反復子を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[do_put](#num_put__do_put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換するために呼び出される仮想関数。|  
|[配置](#num_put__put)|数値を、特定のロケールで書式設定された数値を表す `CharType` のシーケンスに変換します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namenumputchartypea-numputchartype"></a><a name="num_put__char_type"></a>  num_put::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **CharType**します。  
  
##  <a name="a-namenumputdoputa-numputdoput"></a><a name="num_put__do_put"></a>  num_put::do_put  
 一連の数値に変換するために呼び出される仮想関数 **CharType**数を表す書式設定された特定のロケールのです。  
  
```  
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const unsigned long long val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` next`  
 挿入された文字列の最初の要素を示す反復子。  
  
 `_Iosbase`  
 ために、出力と出力を書式設定するためのフラグを punctuate numpunct ファセットとロケールを含むストリームを指定します。  
  
 `_Fill`  
 スペースのために使用される文字。  
  
 ` val`  
 出力するブール型または数。  
  
### <a name="return-value"></a>戻り値  
 出力反復子アドレスは、最後の要素より後の位置 1 つ生成します。  
  
### <a name="remarks"></a>コメント  
 1 つ目の仮想の保護されたメンバー関数から始まる連続した要素を生成する ` next` の値から整数型の出力フィールドを生成する ` val`です。 関数は、生成される整数の出力フィールドを超える要素を挿入する次の場所を指定する反復子を返します。  
  
 整数型の出力フィールドがの系列を生成するために、印刷機能で使用される同じルールによって生成された `char` ファイル要素です。 このような各 char 要素が型の同等の要素にマップすると想定 **CharType** シンプルで一対一のマッピングでします。 印刷機能が、スペースや数字の 0 のいずれかのフィールドを埋める、 `do_put` 代わりに使用して **塗りつぶし**します。 対応する印刷変換仕様は次に従って特定します。  
  
-   場合 **iosbase**します。 [フラグ](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[oct](../Topic/%3Cios%3E%20functions.md#oct), 、変換仕様は **lo**します。  
  
-   場合 **iosbase.flags** & **ios_base::basefield** == `ios_base::`[16 進](../Topic/%3Cios%3E%20functions.md#hex), 、変換仕様は **lx**します。  
  
-   変換仕様は、それ以外の場合、 **%ld**します。  
  
 場合 **iosbase**します。 [幅](../standard-library/ios-base-class.md#ios_base__width) は 0 以外、この値のフィールドの幅が付加されます。 この関数を呼び出します **iosbase**します。 **幅**フィールドの幅をゼロにリセットするには、(0)。  
  
 場合にのみ、余白が発生する要素の最小数 *N* 出力フィールドを指定するために必要な未満 **iosbase**します。 [幅](../standard-library/ios-base-class.md#ios_base__width)します。 一連は、このような埋め込み *N* – **幅** のコピーを **塗りつぶし**します。 次のように実行し、padding:  
  
-   場合 **iosbase**します。 **フラグ** & `ios_base::adjustfield` == `ios_base::`[左](../Topic/%3Cios%3E%20functions.md#left), 、フラグ **–** が付加されています。 (余白は、生成されたテキストの後に発生します)。  
  
-   場合 **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[内部](../Topic/%3Cios%3E%20functions.md#internal), 、フラグ **0** が付加されています。 (数値の出力フィールドの埋め込みは行わ印刷機能が 0 で埋め込む場所)。  
  
-   それ以外の場合、追加のフラグが付加されていません。 (余白は、生成されたシーケンスの前に発生します)。  
  
 最後にします。  
  
-   場合 **iosbase**します。 **フラグ** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) 0 以外の場合、フラグ **+** 変換仕様に付加されています。  
  
-   場合 **iosbase**します。 **フラグ** & **ios_base::**[showbase](../Topic/%3Cios%3E%20functions.md#showbase) 0 以外の場合、フラグ **#** 変換仕様に付加されています。  
  
 整数値の形式の出力フィールドによって決定、 [ロケールのファセット](../standard-library/locale-class.md#facet_class)**要素** 呼び出しによって返される [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。 具体的には、次のように使用します。  
  
- **要素**します。 [グループ化](../standard-library/numpunct-class.md#numpunct__grouping) 数字が小数点の左側にグループ化方法を決定します。  
  
- **要素**します。 [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) 、小数点の左側にある数字のグループを区切るシーケンスを決定  
  
 グループ化の制約が課せられなかった場合 **要素**します。 **グループ化** (先頭の要素値がある、CHAR_MAX) のインスタンス、 **要素**します。 `thousands_sep` [出力フィールドが生成されます。 それ以外の場合、印刷の変換が発生した後、区切り記号が挿入されます。  
  
 2 番目の仮想の保護されたメンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    unsigned long val) const;
```  
  
 同様、最初の変換指定を置換する点を除いて **%ld** と **lu**します。  
  
 3 番目の仮想の保護されたメンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    double val) const;
```  
  
 値から浮動小数点の出力フィールドを作成する点を除いて、最初と同様に動作 **val**します。 **要素**します。 [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) を小数点以下桁数の整数部の桁数を区切るシーケンスを決定します。 対応する印刷変換仕様は次に従って特定します。  
  
-   場合 **iosbase**します。 **フラグ** & `ios_base::floatfield` == `ios_base::`[固定](../Topic/%3Cios%3E%20functions.md#fixed), 、変換仕様は **lf**します。  
  
-   場合 **iosbase**します。 **フラグ** & **ios_base::floatfield** == `ios_base::`[科学](../Topic/%3Cios%3E%20functions.md#scientific), 、変換仕様は `le`です。 場合 **iosbase**します。 **フラグ** & `ios_base::`[大文字](../Topic/%3Cios%3E%20functions.md#uppercase) がゼロ以外、 **e** で置き換えた **E**します。  
  
-   変換仕様は、それ以外の場合、 **lg**します。 場合 **iosbase**します。 **フラグ** & **ios_base::uppercase** がゼロ以外、 **g** で置き換えた **G**します。  
  
 場合 **iosbase**します。 **フラグ** & **ios_base::fixed** が 0 でない場合、または **iosbase**します。 [有効桁数](../standard-library/ios-base-class.md#ios_base__precision) が 0 の場合、値を持つ有効桁数より大きい **iosbase**します。 **有効桁数** 変換仕様に付加されています。 埋め込みは整数型の出力フィールドの場合と同様に動作します。 埋め込み文字が **塗りつぶし**します。 最後にします。  
  
-   場合 **iosbase**します。 **フラグ** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) 0 以外の場合、フラグ **+** 変換仕様に付加されています。  
  
-   場合 **iosbase**します。 **フラグ** & `ios_base::`[showpoint](../Topic/%3Cios%3E%20functions.md#showpoint) 0 以外の場合、フラグ **#** 変換仕様に付加されています。  
  
 4 番目のバーチャルはプロテクト メンバー関数です。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    long double val) const;
```  
  
 3 番目の点を除いては、動作は、同じ修飾子 **l** 変換では、仕様に置き換えられます **L**します。  
  
 5 番目の仮想のプロテクト メンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    const void* val) const;
```  
  
 変換指定がある点がの動作は、1 つ目は、同じ `p`**,、** パディングを指定するために必要なすべての修飾子とします。  
  
 6 番目の仮想のプロテクト メンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    bool val) const;
```  
  
 ブール型の出力フィールドを生成する点を除いて、最初と同様に動作 ` val`します。  
  
 ブール型の出力フィールドは、2 つの形式のいずれかになります。 場合 **iosbase**します。 **フラグ** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) は **false**, 、メンバー関数を返します `do_put`(_ *次*, 、\_ *Iosbase*, 、\_ *塗りつぶし*, 、( **長い**) ` val`)、通常 0 の生成されたシーケンスが生成されます (の **false**) または 1 (の **true**)。 それ以外の場合、生成されたシーケンスであるか、 **要素**します。 [falsename](../standard-library/numpunct-class.md#numpunct__falsename)`)` (の **false**)、または **要素**します。 [truename](../standard-library/numpunct-class.md#numpunct__truename) (の **true**)。  
  
 7 番目の仮想のプロテクト メンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    long long val) const;
```  
  
 同様、最初の変換指定を置換する点を除いて **%ld** と **lld**します。  
  
 8 番目の仮想のプロテクト メンバー関数。  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    unsigned long long val) const;
```  
  
 同様、最初の変換指定を置換する点を除いて `ld` と `llu`です。  
  
### <a name="example"></a>例  
  例を参照してください [配置](#num_put__put), 、どの呼び出し `do_put`します。  
  
##  <a name="a-namenumputitertypea-numputitertype"></a><a name="num_put__iter_type"></a>  num_put::iter_type  
 出力反復子を表す型。  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **OutputIterator します。**  
  
##  <a name="a-namenumputnumputa-numputnumput"></a><a name="num_put__num_put"></a>  num_put::num_put  
 `num_put` 型のオブジェクトのコンストラクター。  
  
```  
explicit num_put(size_t _Refs = 0);
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
  
 コンス トラクターは、そのベース オブジェクトと **ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)(_ *Refs*)。  
  
##  <a name="a-namenumputputa-numputput"></a><a name="num_put__put"></a>  num_put::put  
 一連の数値を変換 **CharType**数を表す書式設定された特定のロケールのです。  
  
```  
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Long long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Unsigned long long val) const;

 
 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 ` dest`  
 挿入された文字列の最初の要素を示す反復子。  
  
 `_Iosbase`  
 ロケールには、出力と出力を書式設定するためのフラグを punctuate に使用される numpunct ファセットが含まれているストリームを指定します。  
  
 `_Fill`  
 スペースのために使用される文字。  
  
 ` val`  
 出力するブール型または数。  
  
### <a name="return-value"></a>戻り値  
 出力反復子アドレスは、最後の要素より後の位置 1 つ生成します。  
  
### <a name="remarks"></a>コメント  
 すべてのメンバー関数が返す [do_put](#num_put__do_put)( ` next`, 、`_Iosbase`, 、`_Fill`, 、` val`)。  
  
### <a name="example"></a>例  
  
```  
// num_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
   basic_stringstream<char> psz2;  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << "The thousands separator is: "   
        << use_facet < numpunct <char> >(loc).thousands_sep( )   
        << endl;  
  
   psz2.imbue( loc );  
   use_facet < num_put < char > >  
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),  
                    psz2, ' ', fVal=1000.67);  
  
   if ( st & ios_base::failbit )  
      cout << "num_put( ) FAILED" << endl;  
   else  
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;  
}  
```  
  
```Output  
The thousands separator is: .  
num_put( ) = 1.000,67  
```  
  
## <a name="see-also"></a>関連項目  
 [\< ロケール>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

