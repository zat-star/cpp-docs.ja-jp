---
title: "codecvt クラス | Microsoft Docs"
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
  - "codecvt"
  - "std::codecvt"
  - "std.codecvt"
  - "xlocale/std::codecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt クラス"
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# codecvt クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ロケールのファセットとして使用できるオブジェクトを表すテンプレート クラス。 プログラム内で文字をエンコードするために使用される値のシーケンスと、プログラム外で文字をエンコードするために使用される値のシーケンスとの変換を制御できます。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
 `Byte`  
 文字をエンコードするためにプログラム外で使用される型。  
  
 `StateType`  
 文字表現の内部型と外部型との変換の中間状態を表すために使用できる型。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスとして使用できるオブジェクトを表します、 [ロケールのファセット](../standard-library/locale-class.md#facet_class), 型の値のシーケンスの間の変換を制御する `CharType` と型の値のシーケンス `Byte`します。 `StateType` クラスは変換を特徴付けます。また、`StateType` クラスのオブジェクトは変換中に必要な状態情報を格納します。  
  
 内部エンコードでは、1 文字あたりのバイト数が固定された表現、通常 `char` 型または `wchar_t` 型を使用します。  
  
 すべてのロケールのファセットと同様、静的オブジェクト `id` に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 `id`します。  
  
 テンプレートのバージョンの [do_in](#codecvt__do_in) と [do_out](#codecvt__do_out) いつでも `codecvt_base::noconv`します。  
  
 標準 C++ ライブラリは複数の明示的な特殊化を定義します。  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 これは、`wchar_t` シーケンスと `char` シーケンスとの変換を実行します。  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 これは、UTF-16 としてエンコードされる `char16_t` シーケンスと UTF-8 としてエンコードされる `char` シーケンスとの変換を実行します。  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 これは、UTF-32 (UCS-4) としてエンコードされる `char32_t` シーケンスと UTF-8 としてエンコードされる `char` シーケンスとの変換を実行します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[codecvt](#codecvt__codecvt)|変換を処理するためにロケールのファセットとして機能する `codecvt` クラスのオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedef  
  
|||  
|-|-|  
|[extern_type](#codecvt__extern_type)|外部表現に使用される文字型。|  
|[intern_type](#codecvt__intern_type)|内部表現に使用される文字型。|  
|[state_type](#codecvt__state_type)|内部表現と外部表現との変換時の中間状態を表すために使用される文字型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[always_noconv](#codecvt__always_noconv)|変換を実行する必要がないかどうかをテストします。|  
|[do_always_noconv](#codecvt__do_always_noconv)|変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。|  
|[do_encoding](#codecvt__do_encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定する仮想関数。|  
|[do_in](#codecvt__do_in)|内部の `Byte` のシーケンスを外部の `CharType` のシーケンスに変換するために呼び出される仮想関数。|  
|[do_length](#codecvt__do_length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返す仮想関数。|  
|[do_max_length](#codecvt__do_max_length)|1 つの内部 `CharType` を生成するために必要な最大外部 Byte 数を返す仮想関数。|  
|[do_out](#codecvt__do_out)|内部の `CharType` のシーケンスを外部の Byte のシーケンスに変換するために呼び出される仮想関数。|  
|[do_unshift](#codecvt__do_unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な `Byte` を提供するために呼び出される仮想関数。|  
|[エンコーディング](#codecvt__encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定します。|  
|[で](#codecvt__in)|`Byte` のシーケンスの外部表現を、`CharType` のシーケンスの内部表現に変換します。|  
|[長さ](#codecvt__length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返します。|  
|[max_length](#codecvt__max_length)|1 つの内部 `Byte` を生成するために必要な最大外部 `CharType` 数を返します。|  
|[アウト](#codecvt__out)|内部の `CharType` のシーケンスを外部の `Byte` のシーケンスに変換します。|  
|[unshift](#codecvt__unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な外部の `Byte` を提供します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \< ロケール>  
  
 **名前空間:** std  
  
##  <a name="a-namecodecvtalwaysnoconva-codecvtalwaysnoconv"></a><a name="codecvt__always_noconv"></a>  codecvt::always_noconv  
 変換を実行する必要がないかどうかをテストします。  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 ブール値 **true** 場合、変換を実行する必要はありません **。false** 、少なくとも 1 つ実行する必要があります。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_always_noconv](#codecvt__do_always_noconv)します。  
  
### <a name="example"></a>例  
  
```  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="a-namecodecvtcodecvta-codecvtcodecvt"></a><a name="codecvt__codecvt"></a>  codecvt::codecvt  
 変換を処理するためにロケール ファセットとして機能するクラス codecvt のオブジェクトのコンス トラクターです。  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理の種類を指定するために使用する整数値です。  
  
### <a name="remarks"></a>コメント  
 ような値、 `_Refs` パラメーターとその重要性は。  
  
-   0: オブジェクトの有効期間はそれを含むロケールで管理します。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \> 0: これらの値が定義されていません。  
  
 コンス トラクターは、その `locale::facet` ベース オブジェクトと **ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)( `_Refs`) *します。*  
  
##  <a name="a-namecodecvtdoalwaysnoconva-codecvtdoalwaysnoconv"></a><a name="codecvt__do_always_noconv"></a>  codecvt::do_always_noconv  
 変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロテクト仮想メンバー関数を返します **true** 場合にのみ、すべての呼び出しに [do_in](#codecvt__do_in) または [do_out](#codecvt__do_out) を返します **noconv**します。  
  
 テンプレートのバージョンを常に返します **true**します。  
  
### <a name="example"></a>例  
  例を参照してください [always_noconv](#codecvt__always_noconv), 、どの呼び出し `do_always_noconv`します。  
  
##  <a name="a-namecodecvtdoencodinga-codecvtdoencoding"></a><a name="codecvt__do_encoding"></a>  codecvt::do_encoding  
 仮想関数をテストのエンコード、 **バイト** ストリームは、状態に依存するをするかどうかがの比率、 **バイト**使用されると、 **CharType**生成されるは定数であり、必要な場合は、比率の値を決定します。  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 プロテクト仮想メンバー関数を返します。  
  
-   – 1, 場合型のシーケンスのエンコード `extern_type` は状態が依存しています。  
  
-   エンコードのさまざまな長さのシーケンスを含まれている場合は 0。  
  
- *N*, エンコーディングの長さの唯一のシーケンスを含まれている場合、 *N*  
  
### <a name="example"></a>例  
  例を参照してください [エンコーディング](#codecvt__encoding), 、どの呼び出し `do_encoding`します。  
  
##  <a name="a-namecodecvtdoina-codecvtdoin"></a><a name="codecvt__do_in"></a>  codecvt::do_in  
 外部のシーケンスに変換する呼び出される仮想関数 **バイト**の内部シーケンスに **CharType**秒です。  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 変換するシーケンスの先頭へのポインター。  
  
 ` last1`  
 変換するシーケンスの末尾へのポインター。  
  
 ` next1`  
 最初の未変換文字への変換されたシーケンスの末尾の次のポインター。  
  
 ` first2`  
 変換後のシーケンスの先頭へのポインター。  
  
 ` last2`  
 変換後のシーケンスの末尾へのポインター。  
  
 ` next2`  
 ポインター、 **CharType** 最後が変換された後は、 **CharType**, 、変換先のシーケンスの最初の変更されていない文字にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、部分的な成功した場合、または操作の失敗を示す戻り値。 関数を返します。  
  
- **codecvt_base::error** 場合、ソース シーケンスが病気が形成されます。  
  
- `codecvt_base::noconv` 場合は、関数には、変換は行われません。  
  
- **codecvt_base::ok** 変換が成功した場合。  
  
- **codecvt_base::partial** ソースが不十分な場合、またはコピー先のサイズが不十分、変換を成功させるためです。  
  
### <a name="remarks"></a>コメント  
 `_State` 新しいソース シーケンスの先頭にある初期の変換状態を表す必要があります。 関数は、変換に成功したは、現在の状態を反映するために必要に応じて、格納されている値を変更します。 格納されているその値は、それ以外の場合指定されません。  
  
### <a name="example"></a>例  
  例を参照してください [で](#codecvt__in), 、どの呼び出し `do_in`します。  
  
##  <a name="a-namecodecvtdolengtha-codecvtdolength"></a><a name="codecvt__do_length"></a>  codecvt::do_length  
 仮想関数を決定する数 **バイト**外部の指定されたシーケンスから **バイト**生成内部の指定された数よりも **CharType**s しその数を返します **バイト**秒です。  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 外部のシーケンスの先頭へのポインター。  
  
 ` last1`  
 外部のシーケンスの末尾へのポインター。  
  
 `_Len2`  
 最大数 **バイト**s メンバー関数によって返されることができます。  
  
### <a name="return-value"></a>戻り値  
 変換では、以下の最大数のカウントを表す整数 `_Len2`, に外部ソース シーケンスで定義されている [ ` first1`, 、` last1`)。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数が効果的に呼び出し `do_in`( `_State`, 、` first1`, 、` last1`, 、` next1`, 、`_Buf`, 、`_Buf` + `_Len2`, 、` next2`) の `_State` (状態のコピー)、一部のバッファー `_Buf`, 、およびポインター ` next1`と ` next2`です。  
  
 これは、後、返します ` next2` – **buf**します。 したがって、変換では、以下の最大数をカウント `_Len2`, でソース シーケンスで定義されている [ ` first1`, 、` last1`)。  
  
 テンプレートのバージョンを常に返しますの小さい方の ` last1` – ` first1` と `_Len2`です。  
  
### <a name="example"></a>例  
  例を参照してください [長さ](#codecvt__length), 、どの呼び出し **do_length**します。  
  
##  <a name="a-namecodecvtdomaxlengtha-codecvtdomaxlength"></a><a name="codecvt__do_max_length"></a>  codecvt::do_max_length  
 外部の最大数を返す仮想関数 **バイト**を 1 つの内部を生成するために必要な s **CharType**します。  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 最大数 **バイト**いずれかの生成に必要な s **CharType**します。  
  
### <a name="remarks"></a>コメント  
 プロテクト仮想メンバー関数によって返される最大許容値を返す [do_length](#codecvt__do_length)( ` first1`, 、` last1`, 1) の任意の有効な値について ` first1` と ` last1`です。  
  
### <a name="example"></a>例  
  例を参照してください [max_length](#codecvt__max_length), 、どの呼び出し `do_max_length`します。  
  
##  <a name="a-namecodecvtdoouta-codecvtdoout"></a><a name="codecvt__do_out"></a>  codecvt::do_out  
 内部のシーケンスに変換する呼び出される仮想関数 **CharType**外部のシーケンスに **バイト**秒です。  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 変換するシーケンスの先頭へのポインター。  
  
 ` last1`  
 変換するシーケンスの末尾へのポインター。  
  
 ` next1`  
 最初へのポインターへの参照に変換しない **CharType**, 、最後に **CharType** 変換します。  
  
 ` first2`  
 変換後のシーケンスの先頭へのポインター。  
  
 ` last2`  
 変換後のシーケンスの末尾へのポインター。  
  
 ` next2`  
 最初へのポインターへの参照に変換しない **バイト**, 、最後に **バイト** 変換します。  
  
### <a name="return-value"></a>戻り値  
 関数を返します。  
  
- **codecvt_base::error** 場合、ソース シーケンスが病気が形成されます。  
  
- `codecvt_base::noconv` 場合は、関数には、変換は行われません。  
  
- **codecvt_base::ok** 変換が成功した場合。  
  
- **codecvt_base::partial** ソースが不十分な場合、または変換先が変換を成功させるのに十分な大きさがない場合。  
  
### <a name="remarks"></a>コメント  
 `_State` 新しいソース シーケンスの先頭にある初期の変換状態を表す必要があります。 関数は、変換に成功したは、現在の状態を反映するために必要に応じて、格納されている値を変更します。 格納されているその値は、それ以外の場合指定されません。  
  
### <a name="example"></a>例  
  例を参照してください [アウト](#codecvt__out), 、どの呼び出し `do_out`します。  
  
##  <a name="a-namecodecvtdounshifta-codecvtdounshift"></a><a name="codecvt__do_unshift"></a>  codecvt::do_unshift  
 提供する呼び出される仮想関数、 **バイト**状態に依存する変換でのシーケンスの最後の文字を完了するために必要な s **バイト**秒です。  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first2`  
 ターゲット範囲内の最初の位置を指すポインター。  
  
 ` last2`  
 ターゲット範囲の最後の位置を指すポインター。  
  
 ` next2`  
 移行先のシーケンスの最初の変更されていない要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数を返します。  
  
- **codecvt_base::error** 場合 _ *状態* 無効な状態を表します  
  
- `codecvt_base::noconv` 関数が変換を実行しない場合  
  
- **codecvt_base::ok** 変換が成功した場合  
  
- **codecvt_base::partial** 、変換先が変換を成功させるのに十分な大きさがない場合  
  
### <a name="remarks"></a>コメント  
 このプロテクト仮想メンバー関数が、ソース要素を変換しようとしています。 **CharType**(0) 内で格納している移行先のシーケンスに [ ` first2`, 、` last2`)、終端の要素を除く **バイト**(0)。 常に格納 ` next2` 対象シーケンスの最初の変更されていない要素へのポインター。  
  
 _ *状態* 新しいソース シーケンスの先頭にある初期の変換状態を表す必要があります。 関数は、変換に成功したは、現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素に変換する **CharType**(0) を初期の変換状態の現在の状態のままです。  
  
### <a name="example"></a>例  
  例を参照してください [unshift](#codecvt__unshift), 、どの呼び出し `do_unshift`します。  
  
##  <a name="a-namecodecvtencodinga-codecvtencoding"></a><a name="codecvt__encoding"></a>  codecvt::encoding  
 かどうかのエンコード、 **バイト** ストリームでは状態に依存する、かどうかの比率、 **バイト**使用されると、 **CharType**生成される定数、および、必要な場合は、決定比率の値。  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値が正の値、その値が一定数の **バイト** 生成に必要な文字、 **CharType** 文字です。  
  
 プロテクト仮想メンバー関数を返します。  
  
-   – 1, 場合型のシーケンスのエンコード `extern_type` は状態が依存しています。  
  
-   エンコードのさまざまな長さのシーケンスを含まれている場合は 0。  
  
- *N*, エンコーディングの長さの唯一のシーケンスを含まれている場合、 *n ください。*  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_encoding](#codecvt__do_encoding)します。  
  
### <a name="example"></a>例  
  
```  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="a-namecodecvtexterntypea-codecvtexterntype"></a><a name="codecvt__extern_type"></a>  codecvt::extern_type  
 外部表現に使用される文字型。  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **バイト**します。  
  
##  <a name="a-namecodecvtina-codecvtin"></a><a name="codecvt__in"></a>  codecvt::in  
 一連の外部の形式に変換 **バイト**の一連の内部表現に **CharType**秒です。  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 変換するシーケンスの先頭へのポインター。  
  
 ` last1`  
 変換するシーケンスの末尾へのポインター。  
  
 ` next1`  
 最初の未変換文字の変換後のシーケンスの末尾の次のポインター。  
  
 ` first2`  
 変換後のシーケンスの先頭へのポインター。  
  
 ` last2`  
 変換後のシーケンスの末尾へのポインター。  
  
 ` next2`  
 ポインター、 **CharType** 最後が変換された後は、 **Chartype** 対象シーケンスの最初の変更されていない文字にします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、部分的な成功または操作の失敗を示す戻り値。 関数を返します。  
  
- **codecvt_base::error** 場合、ソース シーケンスが病気が形成されます。  
  
- `codecvt_base::noconv` 場合は、関数には、変換は行われません。  
  
- **codecvt_base::ok** 変換が成功した場合。  
  
- **codecvt_base::partial** ソースが不十分な場合、または変換先が変換を成功させるのに十分な大きさがない場合。  
  
### <a name="remarks"></a>コメント  
 `_State` 新しいソース シーケンスの先頭にある初期の変換状態を表す必要があります。 関数は、変換に成功したは、現在の状態を反映するように、必要に応じて、格納されている値を変更します。 一部の変換後 `_State` を新しい文字が到着したときに再開する変換を許可するために設定する必要があります。  
  
 メンバー関数を返します [do_in](#codecvt__do_in)( `_State`, 、_ *First1、last1、next1、First2、_Llast2、next2*)。  
  
### <a name="example"></a>例  
  
```  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="a-namecodecvtinterntypea-codecvtinterntype"></a><a name="codecvt__intern_type"></a>  codecvt::intern_type  
 内部表現に使用される文字型。  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **CharType**します。  
  
##  <a name="a-namecodecvtlengtha-codecvtlength"></a><a name="codecvt__length"></a>  codecvt::length  
 指定数 **バイト**外部の指定されたシーケンスから **バイト**生成内部の指定された数よりも **CharType**s しその数を返します **バイト**s です。  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 外部のシーケンスの先頭へのポインター。  
  
 ` last1`  
 外部のシーケンスの末尾へのポインター。  
  
 `_Len2`  
 メンバー関数によって返されるバイトの最大数。  
  
### <a name="return-value"></a>戻り値  
 変換では、以下の最大数のカウントを表す整数 `_Len2`, に外部ソース シーケンスで定義されている [ ` first1`, 、` last1`)。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_length](#codecvt__do_length)( *_State first1*, 、` last1`, 、`_Len2`)。  
  
### <a name="example"></a>例  
  
```  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="a-namecodecvtmaxlengtha-codecvtmaxlength"></a><a name="codecvt__max_length"></a>  codecvt::max_length  
 外部の最大数を返します **バイト**を 1 つの内部を生成するために必要な s **CharType**します。  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 最大数 **バイト**いずれかの生成に必要な s **CharType**します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数を返します [do_max_length](#codecvt__do_max_length)します。  
  
### <a name="example"></a>例  
  
```  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="a-namecodecvtouta-codecvtout"></a><a name="codecvt__out"></a>  codecvt::out  
 内部シーケンスを変換 **CharType**外部のシーケンスに **バイト**秒です。  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first1`  
 変換するシーケンスの先頭へのポインター。  
  
 ` last1`  
 変換するシーケンスの末尾へのポインター。  
  
 ` next1`  
 最初へのポインターへの参照に変換しない **CharType** 最後後 **CharType** 変換します。  
  
 ` first2`  
 変換後のシーケンスの先頭へのポインター。  
  
 ` last2`  
 変換後のシーケンスの末尾へのポインター。  
  
 ` next2`  
 最初へのポインターへの参照に変換しない **バイト** 最後の変換後 **バイト**します。  
  
### <a name="return-value"></a>戻り値  
 メンバー関数を返します [do_out](#codecvt__do_out)( `_State`, 、` first1`, 、` last1`, 、` next1`, 、` first2`, 、` last2`, 、` next2`)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [codecvt::do_out](#codecvt__do_out)します。  
  
### <a name="example"></a>例  
  
```  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="a-namecodecvtstatetypea-codecvtstatetype"></a><a name="codecvt__state_type"></a>  codecvt::state_type  
 内部表現と外部表現との変換時の中間状態を表すために使用される文字型。  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>コメント  
 型は、テンプレート パラメーターのシノニム **StateType**します。  
  
##  <a name="a-namecodecvtunshifta-codecvtunshift"></a><a name="codecvt__unshift"></a>  codecvt::unshift  
 提供、 **バイト**状態に依存する変換でのシーケンスの最後の文字を完了するために必要な s **バイト**秒です。  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数への呼び出しの間で維持されますが、変換状態です。  
  
 ` first2`  
 ターゲット範囲内の最初の位置を指すポインター。  
  
 ` last2`  
 ターゲット範囲の最後の位置を指すポインター。  
  
 ` next2`  
 移行先のシーケンスの最初の変更されていない要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数を返します。  
  
- **codecvt_base::error** 状態が無効な状態を表す場合。  
  
- `codecvt_base::noconv` 場合は、関数には、変換は行われません。  
  
- **codecvt_base::ok** 変換が成功した場合。  
  
- **codecvt_base::partial** 、変換先が変換を成功させるのに十分な大きさがない場合。  
  
### <a name="remarks"></a>コメント  
 このプロテクト仮想メンバー関数が、ソース要素を変換しようとしています。 **CharType**(0) 内で格納している移行先のシーケンスに [ ` first2`, 、` last2`)、終端の要素を除く **バイト**(0)。 常に格納 ` next2` 対象シーケンスの最初の変更されていない要素へのポインター。  
  
 `_State` 新しいソース シーケンスの先頭にある初期の変換状態を表す必要があります。 関数は、変換に成功したは、現在の状態を反映するように、必要に応じて、格納されている値を変更します。 通常、ソース要素に変換する **CharType**(0) を初期の変換状態の現在の状態のままです。  
  
 メンバー関数を返します [do_unshift](#codecvt__do_unshift)( `_State`, 、` first2`, 、` last2`, 、` next2` )。  
  
## <a name="see-also"></a>関連項目  
 [\< ロケール>](../standard-library/locale.md)   
 [コード ページ](../c-runtime-library/code-pages.md)   
 [ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

