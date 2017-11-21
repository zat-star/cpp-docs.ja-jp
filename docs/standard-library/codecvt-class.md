---
title: "codecvt クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocale/std::codecvt
- xlocale/std::codecvt::extern_type
- xlocale/std::codecvt::intern_type
- xlocale/std::codecvt::state_type
- xlocale/std::codecvt::always_noconv
- xlocale/std::codecvt::do_always_noconv
- xlocale/std::codecvt::do_encoding
- xlocale/std::codecvt::do_in
- xlocale/std::codecvt::do_length
- xlocale/std::codecvt::do_max_length
- xlocale/std::codecvt::do_out
- xlocale/std::codecvt::do_unshift
- xlocale/std::codecvt::encoding
- xlocale/std::codecvt::in
- xlocale/std::codecvt::length
- xlocale/std::codecvt::max_length
- xlocale/std::codecvt::out
- xlocale/std::codecvt::unshift
dev_langs: C++
helpviewer_keywords:
- std::codecvt [C++]
- std::codecvt [C++], extern_type
- std::codecvt [C++], intern_type
- std::codecvt [C++], state_type
- std::codecvt [C++], always_noconv
- std::codecvt [C++], do_always_noconv
- std::codecvt [C++], do_encoding
- std::codecvt [C++], do_in
- std::codecvt [C++], do_length
- std::codecvt [C++], do_max_length
- std::codecvt [C++], do_out
- std::codecvt [C++], do_unshift
- std::codecvt [C++], encoding
- std::codecvt [C++], in
- std::codecvt [C++], length
- std::codecvt [C++], max_length
- std::codecvt [C++], out
- std::codecvt [C++], unshift
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 290b48c5417aa5511b34f2e4ec2e0d4b7358b026
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="codecvt-class"></a>codecvt クラス
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
 テンプレート クラスは、`CharType` 型の値のシーケンスと `Byte` 型の値のシーケンスとの変換を制御するために、[ロケール ファセット](../standard-library/locale-class.md#facet_class)として使用できるオブジェクトを表します。 `StateType` クラスは変換を特徴付けます。また、`StateType` クラスのオブジェクトは変換中に必要な状態情報を格納します。  
  
 内部エンコードでは、1 文字あたりのバイト数が固定された表現、通常 `char` 型または `wchar_t` 型を使用します。  
  
 すべてのロケールのファセットと同様、静的オブジェクト `id` に最初に格納されている値は 0 です。 格納されている値に初めてアクセスしようとすると、`id` に一意の正の値が格納されます。  
  
 [do_in](#do_in) と [do_out](#do_out) のテンプレート バージョンでは、常に `codecvt_base::noconv` が返されます。  
  
 C++ 標準ライブラリは複数の明示的な特殊化を定義します。  
  
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
|[codecvt](#codecvt)|変換を処理するためにロケールのファセットとして機能する `codecvt` クラスのオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[extern_type](#extern_type)|外部表現に使用される文字型。|  
|[intern_type](#intern_type)|内部表現に使用される文字型。|  
|[state_type](#state_type)|内部表現と外部表現との変換時の中間状態を表すために使用される文字型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[always_noconv](#always_noconv)|変換を実行する必要がないかどうかをテストします。|  
|[do_always_noconv](#do_always_noconv)|変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。|  
|[do_encoding](#do_encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定する仮想関数。|  
|[do_in](#do_in)|内部の `Byte` のシーケンスを外部の `CharType` のシーケンスに変換するために呼び出される仮想関数。|  
|[do_length](#do_length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返す仮想関数。|  
|[do_max_length](#do_max_length)|1 つの内部 `CharType` を生成するために必要な最大外部 Byte 数を返す仮想関数。|  
|[do_out](#do_out)|内部の `CharType` のシーケンスを外部の Byte のシーケンスに変換するために呼び出される仮想関数。|  
|[do_unshift](#do_unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な `Byte` を提供するために呼び出される仮想関数。|  
|[encoding](#encoding)|`Byte` ストリームのエンコードが状態に依存する場合に、使用される `Byte` と生成される `CharType` との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定します。|  
|[in](#in)|`Byte` のシーケンスの外部表現を、`CharType` のシーケンスの内部表現に変換します。|  
|[length](#length)|特定の外部 `Byte` シーケンスから生成された内部 `Byte` が特定の数を超えずに最大となる `CharType` 数を特定し、その `Byte` 数を返します。|  
|[max_length](#max_length)|1 つの内部 `Byte` を生成するために必要な最大外部 `CharType` 数を返します。|  
|[out](#out)|内部の `CharType` のシーケンスを外部の `Byte` のシーケンスに変換します。|  
|[unshift](#unshift)|状態に依存する変換で、`Byte` のシーケンスの最後の文字を完了するために必要な外部の `Byte` を提供します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
##  <a name="always_noconv"></a>  codecvt::always_noconv  
 変換を実行する必要がないかどうかをテストします。  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 変換する必要がない場合は **true**、少なくとも 1 回は変換する必要がある場合は **false** のブール値。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_always_noconv](#do_always_noconv) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="codecvt"></a>  codecvt::codecvt  
 変換を処理するためにロケール ファセットとして機能する codecvt クラスのオブジェクトのコンストラクター。  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理のタイプを指定するために使用する整数値。  
  
### <a name="remarks"></a>コメント  
 `_Refs` パラメーターの可能な値とその重要性は次のとおりです。  
  
-   0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \>1: これらの値が定義されていません。  
  
 コンス トラクターは、その`locale::facet`とベース オブジェクト**ロケール::**[ファセット](../standard-library/locale-class.md#facet_class)(`_Refs`)。  
  
##  <a name="do_always_noconv"></a>  codecvt::do_always_noconv  
 変換を実行する必要がないかどうかをテストするために呼び出される仮想関数。  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 protected 仮想メンバー関数は、[do_in](#do_in) または [do_out](#do_out) のすべての呼び出しで **noconv** が返された場合にのみ、**true** を返します。  
  
 テンプレート バージョンでは常に **true** が返されます。  
  
### <a name="example"></a>例  
  [always_noconv](#always_noconv) の例 (`do_always_noconv` を呼び出す) を参照してください。  
  
##  <a name="do_encoding"></a>  codecvt::do_encoding  
 **Byte** ストリームのエンコードが状態に依存する場合に、使用される **Byte** と生成される **CharType** との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定する仮想関数。  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 protected 仮想メンバー関数は次の値を返します。  
  
-   -1 場合の型のシーケンスのエンコーディング`extern_type`状態は、依存します。  
  
-   エンコードがさまざまな長さのシーケンスに関係する場合は、0。  
  
- エンコードが長さ *N* のシーケンスのみに関係する場合は、*N*。  
  
### <a name="example"></a>例  
  [encoding](#encoding) の例 (`do_encoding` を呼び出す) を参照してください。  
  
##  <a name="do_in"></a>  codecvt::do_in  
 外部の **Byte** のシーケンスを内部の **CharType** のシーケンスに変換するために呼び出される仮想関数。  
  
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
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 変換されるシーケンスの先頭へのポインター。  
  
 `last1`  
 変換されるシーケンスの末尾へのポインター。  
  
 `next1`  
 変換されたシーケンスの末尾の後の、最初の非変換文字へのポインター。  
  
 `first2`  
 変換されたシーケンスの先頭へのポインター。  
  
 `last2`  
 変換されたシーケンスの末尾へのポインター。  
  
 `next2`  
 変換された最後の **CharType** の後の **CharType** (対象シーケンスの変更されていない最初の文字) へのポインター。  
  
### <a name="return-value"></a>戻り値  
 操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。  
  
- ソース シーケンスが無効な形式である場合は、**codecvt_base::error**。  
  
- 関数で変換が行われない場合は、`codecvt_base::noconv`。  
  
- 変換に成功した場合は、**codecvt_base::ok**。  
  
- 変換を正常に行うのに、ソースが十分でないか、変換先が十分な大きさでない場合は、**codecvt_base::partial**。  
  
### <a name="remarks"></a>コメント  
 `_State` は、新しいソース シーケンスの先頭で初期の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。  
  
### <a name="example"></a>例  
  [in](#in) の例 (`do_in` を呼び出す) を参照してください。  
  
##  <a name="do_length"></a>  codecvt::do_length  
 特定の外部 **Byte** シーケンスから生成された内部 **CharType** が特定の数を超えずに最大となる **Byte** 数を特定し、その **Byte** 数を返す仮想関数。  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 外部シーケンスの先頭へのポインター。  
  
 `last1`  
 外部シーケンスの末尾へのポインター。  
  
 `_Len2`  
 メンバー関数で返すことができる **Byte** の最大数。  
  
### <a name="return-value"></a>戻り値  
 [ `first1`, `last1`) で外部ソース シーケンスによって定義されている `_Len2` 以下の、最大変換数を表す整数。  
  
### <a name="remarks"></a>コメント  
 protected 仮想メンバー関数は、`_State` (状態のコピー)、一部のバッファー `_Buf`、およびポインター `next1` と `next2` について、`do_in` (`_State`、`first1`、`last1`、`next1`、`_Buf`、`_Buf` + `_Len2`、`next2`) を呼び出します。  
  
 これは、後、返します`next2`  -  **buf**です。 したがって、[ `first1`, `last1`) で外部ソース シーケンスによって定義されている `_Len2` 以下の、最大変換数がカウントされます。  
  
 テンプレートのバージョンが常の小さい方を返します`last1`  -  `first1`と`_Len2`です。  
  
### <a name="example"></a>例  
  [length](#length) の例 (**do_length** を呼び出す) を参照してください。  
  
##  <a name="do_max_length"></a>  codecvt::do_max_length  
 1 つの内部 **CharType** を生成するために必要な最大外部 **Byte** 数を返す仮想関数。  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 1 つの **CharType** を生成するために必要な最大 **Byte** 数。  
  
### <a name="remarks"></a>コメント  
 protected 仮想メンバー関数は、`first1` と `last1` の任意の有効な値の [do_length](#do_length)( `first1`, `last1`, 1) で返すことができる最大許容値を返します。  
  
### <a name="example"></a>例  
  [max_length](#max_length) の例 (`do_max_length` を呼び出す) を参照してください。  
  
##  <a name="do_out"></a>  codecvt::do_out  
 内部の **CharType** のシーケンスを外部の **Byte** のシーケンスに変換するために呼び出される仮想関数。  
  
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
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 変換されるシーケンスの先頭へのポインター。  
  
 `last1`  
 変換されるシーケンスの末尾へのポインター。  
  
 `next1`  
 変換された最後の **CharType** の後の、最初の未変換 **CharType** へのポインターの参照。  
  
 `first2`  
 変換されたシーケンスの先頭へのポインター。  
  
 `last2`  
 変換されたシーケンスの末尾へのポインター。  
  
 `next2`  
 変換された最後の **Byte** の後の、最初の未変換 **Byte** へのポインターの参照。  
  
### <a name="return-value"></a>戻り値  
 この関数では次の値が返されます。  
  
- ソース シーケンスが無効な形式である場合は、**codecvt_base::error**。  
  
- 関数で変換が行われない場合は、`codecvt_base::noconv`。  
  
- 変換に成功した場合は、**codecvt_base::ok**。  
  
- 変換を正常に行うのに、ソースが十分でないか、変換先が十分な大きさでない場合は、**codecvt_base::partial**。  
  
### <a name="remarks"></a>コメント  
 `_State` は、新しいソース シーケンスの先頭で初期の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 それ以外の場合、格納されている値は指定されません。  
  
### <a name="example"></a>例  
  [out](#out) の例 (`do_out` を呼び出す) を参照してください。  
  
##  <a name="do_unshift"></a>  codecvt::do_unshift  
 状態に依存する変換で、**Byte** のシーケンスの最後の文字を完了するために必要な **Byte** を提供するために呼び出される仮想関数。  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first2`  
 対象範囲内の最初の位置へのポインター。  
  
 `last2`  
 対象範囲内の最後の位置へのポインター。  
  
 `next2`  
 対象シーケンス内の変更されていない最初の要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 この関数では次の値が返されます。  
  
- _ *State* が無効な状態を表す場合は、**codecvt_base::error**。  
  
- 関数で変換が行われない場合は、`codecvt_base::noconv`。  
  
- 変換に成功した場合は、**codecvt_base::ok**。  
  
- 変換先が、変換を正常に行うのに十分な大きさでない場合は、**codecvt_base::partial**。  
  
### <a name="remarks"></a>コメント  
 protected 仮想メンバー関数は、ソース要素 **CharType**(0) を、終了要素 **Byte**(0) 以外の、[ `first2`, `last2`) 内に格納されている対象シーケンスに変換しようとします。 対象シーケンス内の変更されていない最初の要素へのポインター `next2` に常に格納します。  
  
 _ *State* は、新しいソース シーケンスの先頭で最初の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素 **CharType**(0) を変換した場合、現在の状態は初期の変換状態のままになります。  
  
### <a name="example"></a>例  
  [unshift](#unshift) の例 (`do_unshift` を呼び出す) を参照してください。  
  
##  <a name="encoding"></a>  codecvt::encoding  
 **Byte** ストリームのエンコードが状態に依存する場合に、使用される **Byte** と生成される **CharType** との比率が一定であるかどうかをテストし、一定である場合は、その比率の値を特定します。  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 戻り値が正の値の場合、その値は、**CharType** 文字の生成に必要な **Byte** 文字の定数になります。  
  
 protected 仮想メンバー関数は次の値を返します。  
  
-   -1 場合の型のシーケンスのエンコーディング`extern_type`状態は、依存します。  
  
-   エンコードがさまざまな長さのシーケンスに関係する場合は、0。  
  
- エンコードが長さ *N* のシーケンスのみに関係する場合は、*N*。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_encoding](#do_encoding) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="extern_type"></a>  codecvt::extern_type  
 外部表現に使用される文字型。  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **Byte** のシノニムです。  
  
##  <a name="in"></a>  codecvt::in  
 **Byte** のシーケンスの外部表現を、**CharType** のシーケンスの内部表現に変換します。  
  
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
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 変換されるシーケンスの先頭へのポインター。  
  
 `last1`  
 変換されるシーケンスの末尾へのポインター。  
  
 `next1`  
 変換されたシーケンスの末尾の後の、最初の未変換文字へのポインター。  
  
 `first2`  
 変換されたシーケンスの先頭へのポインター。  
  
 `last2`  
 変換されたシーケンスの末尾へのポインター。  
  
 `next2`  
 変換された最後の **CharType** の後の **CharType** (対象シーケンスの変更されていない最初の文字) へのポインター。  
  
### <a name="return-value"></a>戻り値  
 操作の成功、一部成功、または失敗を示す戻り値。 この関数では次の値が返されます。  
  
- ソース シーケンスが無効な形式である場合は、**codecvt_base::error**。  
  
- 関数で変換が行われない場合は、`codecvt_base::noconv`。  
  
- 変換に成功した場合は、**codecvt_base::ok**。  
  
- 変換を正常に行うのに、ソースが十分でないか、変換先が十分な大きさでない場合は、**codecvt_base::partial**。  
  
### <a name="remarks"></a>コメント  
 `_State` は、新しいソース シーケンスの先頭で初期の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 部分変換後に、`_State` は、新しい文字の到着時に変換を再開できるように設定する必要があります。  
  
 メンバー関数は、[do_in](#do_in)( `_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="intern_type"></a>  codecvt::intern_type  
 内部表現に使用される文字型。  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **CharType** のシノニムです。  
  
##  <a name="length"></a>  codecvt::length  
 特定の外部 **Byte** シーケンスから生成された内部 **CharType** が特定の数を超えずに最大となる **Byte** 数を特定し、その **Byte** 数を返します。  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 外部シーケンスの先頭へのポインター。  
  
 `last1`  
 外部シーケンスの末尾へのポインター。  
  
 `_Len2`  
 メンバー関数で返すことができる Byte の最大数。  
  
### <a name="return-value"></a>戻り値  
 [ `first1`, `last1`) で外部ソース シーケンスによって定義されている `_Len2` 以下の、最大変換数を表す整数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_length](#do_length)( *_State,  first1*, `last1`, `_Len2`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="max_length"></a>  codecvt::max_length  
 1 つの内部 **CharType** を生成するために必要な最大外部 **Byte** 数を返します。  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 1 つの **CharType** を生成するために必要な最大 **Byte** 数。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、[do_max_length](#do_max_length) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="out"></a>  codecvt::out  
 内部の **CharType** のシーケンスを外部の **Byte** のシーケンスに変換します。  
  
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
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first1`  
 変換されるシーケンスの先頭へのポインター。  
  
 `last1`  
 変換されるシーケンスの末尾へのポインター。  
  
 `next1`  
 変換された最後の **CharType** の後の、最初の未変換 **CharType** へのポインターの参照。  
  
 `first2`  
 変換されたシーケンスの先頭へのポインター。  
  
 `last2`  
 変換されたシーケンスの末尾へのポインター。  
  
 `next2`  
 変換された最後の **Byte** の後の、最初の未変換 **Byte** へのポインターの参照。  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は、[do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`) を返します。  
  
### <a name="remarks"></a>コメント  
 詳細については、「[codecvt::do_out](#do_out)」を参照してください。  
  
### <a name="example"></a>例  
  
```cpp  
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
  
##  <a name="state_type"></a>  codecvt::state_type  
 内部表現と外部表現との変換時の中間状態を表すために使用される文字型。  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **StateType** のシノニムです。  
  
##  <a name="unshift"></a>  codecvt::unshift  
 状態に依存する変換で、**Byte** のシーケンスの最後の文字を完了するために必要な **Byte** を提供します。  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_State`  
 メンバー関数の呼び出し間で維持される変換の状態。  
  
 `first2`  
 対象範囲内の最初の位置へのポインター。  
  
 `last2`  
 対象範囲内の最後の位置へのポインター。  
  
 `next2`  
 対象シーケンス内の変更されていない最初の要素へのポインター。  
  
### <a name="return-value"></a>戻り値  
 この関数では次の値が返されます。  
  
- 無効な状態を表す場合は、**codecvt_base::error**。  
  
- 関数で変換が行われない場合は、`codecvt_base::noconv`。  
  
- 変換に成功した場合は、**codecvt_base::ok**。  
  
- 変換先が、変換を正常に行うのに十分な大きさでない場合は、**codecvt_base::partial**。  
  
### <a name="remarks"></a>コメント  
 protected 仮想メンバー関数は、ソース要素 **CharType**(0) を、終了要素 **Byte**(0) 以外の、[ `first2`, `last2`) 内に格納されている対象シーケンスに変換しようとします。 対象シーケンス内の変更されていない最初の要素へのポインター `next2` に常に格納します。  
  
 `_State` は、新しいソース シーケンスの先頭で初期の変換状態を表す必要があります。 関数は、変換に成功した現在の状態を反映するために必要に応じて、格納されている値を変更します。 通常、ソース要素 **CharType**(0) を変換した場合、現在の状態は初期の変換状態のままになります。  
  
 このメンバー関数は、[do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ) を返します。  
  
## <a name="see-also"></a>関連項目  
 [\<locale>](../standard-library/locale.md)   
 [コード ページ](../c-runtime-library/code-pages.md)   
 [ロケール名、言語、および国/地域識別文字列](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

