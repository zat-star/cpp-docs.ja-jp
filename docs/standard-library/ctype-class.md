---
title: "ctype クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ctype
- std::ctype
- std.ctype
- CType
- xlocale/std::ctype
dev_langs:
- C++
helpviewer_keywords:
- ctype class
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: 19
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
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 08c792c0ab211a5ea8e83d026790322242decb81
ms.lasthandoff: 02/24/2017

---
# <a name="ctype-class"></a>ctype クラス
文字の分類、大文字と小文字の変換、およびネイティブ文字セットとロケールで使用される文字セットとの変換に使用されるふぁセットを提供するクラス。  
  
## <a name="syntax"></a>構文  
  
```  
template <class CharType>  
class ctype : public ctype_base;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 文字をエンコードするためにプログラム内で使用される型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は&0; です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。 分類の条件は、基底クラス ctype_base の入れ子になったビットマスク型で提供されます。  
  
 C++ 標準ライブラリは、このテンプレート クラスの&2; つの明示的な特殊化を定義します。  
  
- [ctype](../standard-library/ctype-char-class.md)< `char`>。違いが別個に記述される明示的な特殊化です。  
  
- **ctype**< `wchar_t`>。要素をワイド文字として扱います。  
  
 テンプレート クラス **ctype**\< **CharType**> のその他の特殊化。  
  
-   式 ( `char`) **ch** を使用して、**CharType** 型の値 ***ch*** を、`char` 型の値に変換します。  
  
-   式 **CharType** ( **byte**) を使用して、`char` 型の値 ***byte*** を、**CharType** 型の値に変換します。  
  
 他の操作はすべて明示的な特殊化 **ctype**< `char`> の場合と同様に `char` 値に対して実行されます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[ctype](#ctype__ctype)|文字のロケール ファセットとして機能する `ctype` クラスのオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#ctype__char_type)|ロケールによって使用される文字を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[do_is](#ctype__do_is)|1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。|  
|[do_narrow](#ctype__do_narrow)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの `char` 型の対応する文字に変換するために呼び出される仮想関数。|  
|[do_scan_is](#ctype__do_scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。|  
|[do_scan_not](#ctype__do_scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。|  
|[do_tolower](#ctype__do_tolower)|文字または文字の範囲を小文字に変換するために呼び出される仮想関数。|  
|[do_toupper](#ctype__do_toupper)|文字または文字の範囲を大文字に変換するために呼び出される仮想関数。|  
|[do_widen](#ctype__do_widen)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換するために呼び出される仮想関数。|  
|[is](#ctype__is)|1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。|  
|[narrow](#ctype__narrow)|ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの char 型の対応する文字に変換します。|  
|[scan_is](#ctype__scan_is)|指定されたマスクに一致する範囲内の最初の文字を検索します。|  
|[scan_not](#ctype__scan_not)|指定されたマスクに一致しない範囲内の最初の文字を検索します。|  
|[tolower](#ctype__tolower)|文字または文字の範囲を小文字に変換します。|  
|[toupper](#ctype__toupper)|文字または文字の範囲を大文字に変換します。|  
|[widen](#ctype__widen)|ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
##  <a name="a-namectypechartypea--ctypechartype"></a><a name="ctype__char_type"></a>  ctype::char_type  
 ロケールによって使用される文字を表す型。  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **CharType** のシノニムです。  
  
### <a name="example"></a>例  
  戻り値として `char_type` を使用する例については、メンバー関数 [widen](#ctype__widen) をご覧ください。  
  
##  <a name="a-namectypectypea--ctypectype"></a><a name="ctype__ctype"></a>  ctype::ctype  
 文字のロケール ファセットとして機能する ctype クラスのオブジェクトのコンストラクター。  
  
```  
explicit ctype(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Refs`  
 オブジェクトのメモリ管理のタイプを指定するために使用する整数値。  
  
### <a name="remarks"></a>コメント  
 `_Refs` パラメーターの可能な値とその重要性は次のとおりです。  
  
-   0: オブジェクトの有効期間はそれが含まれるロケールによって管理されます。  
  
-   1: オブジェクトの有効期間を手動で管理する必要があります。  
  
-   \> 0: これらの値は定義されていません。  
  
 デストラクターが保護されているため、利用できる直接的な例はありません。  
  
 コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その `locale::facet` 基本オブジェクトを初期化します。  
  
##  <a name="a-namectypedoisa--ctypedois"></a><a name="ctype__do_is"></a>  ctype::do_is  
 1 つの文字が特定の属性を持つかどうかをテストしたり、範囲内の各文字の属性を分類して配列に格納したりするために呼び出される仮想関数。  
  
```  
virtual bool do_is(
    mask maskVal,   
    CharType ch) const;

 
virtual const CharType *do_is(
    const CharType* first,   
    const CharType* last,  
    mask* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字をテストするマスク値。  
  
 `ch`  
 属性をテストする文字。  
  
 `first`  
 属性を分類する範囲の最初の文字を示すポインター。  
  
 `last`  
 属性を分類する範囲の最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 各文字の属性の特徴になるマスク値を格納する配列の先頭を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、テストされた文字にマスク値により表される属性が含まれる場合、ブール値 **true** を返します。そのような属性が含まれない場合、**false** を返します。  
  
 2 番目のメンバー関数は、範囲内の各文字の属性を特徴付けるマスク値を含む配列を返します。  
  
### <a name="remarks"></a>コメント  
 文字の属性を分類するマスク値は、ctype の派生元である、クラス [ctype_base](../standard-library/ctype-base-class.md) により提供されます。 最初のメンバー関数は、ビットマスクと呼ばれ、ビット単位の論理演算子 (&#124;、&、^、~) によりマスク値の組み合わせから形成されるその最初のパラメーターの式を受け取ります。  
  
### <a name="example"></a>例  
  [is](#ctype__is) の例 (`do_is` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedonarrowa--ctypedonarrow"></a><a name="ctype__do_narrow"></a>  ctype::do_narrow  
 ロケールで使用される `CharType` 型の文字を、ネイティブ文字セットの `char` 型の対応する文字に変換するために呼び出される仮想関数。  
  
```  
virtual char do_narrow(
    CharType ch,   
    char default = '\0') const;

 
virtual const CharType* do_narrow(
    const CharType* first,   
    const CharType* last,  
    char default,   
    char* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 変換されるロケールにより使用される型 `Chartype` の文字。  
  
 `default`  
 型 `CharType` の文字に対となる型 `char` の文字がない場合にメンバー関数が割り当てる既定値。  
  
 `first`  
 変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 変換後の文字範囲を格納する宛先範囲のうち、型 `char` の最初の文字を示す const ポインター。  
  
### <a name="return-value"></a>戻り値  
 保護されている最初のメンバー関数は、対になる片方が定義されていない場合、型 `CharType` または `default` のパラメーター文字に対応する型 char のネイティブ文字を返します。  
  
 保護されている&2; 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。  
  
### <a name="remarks"></a>コメント  
 保護されている&2; 番目のメンバー テンプレート関数は、値 `do_narrow`( `first` [ `I`], `default`) を `dest`[ `I`] に格納します。`I` の間隔は [0, `last` – `first`) です。  
  
### <a name="example"></a>例  
  [narrow](#ctype__narrow) の例 (`do_narrow` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedoscanisa--ctypedoscanis"></a><a name="ctype__do_scan_is"></a>  ctype::do_scan_is  
 指定されたマスクに一致する範囲内の最初の文字を検索するために呼び出される仮想関数。  
  
```  
virtual const CharType *do_scan_is(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字により照合されるマスク値。  
  
 `first`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたマスクに一致する範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last.` を返します。  
  
### <a name="remarks"></a>コメント  
 保護されているメンバー関数は、[do_is](#ctype__do_is)( `maskVal`, * `ptr`) が true となっている範囲 [ `first`, `last`) 内の最小ポインター `ptr` を返します。  
  
### <a name="example"></a>例  
  [scan_is](#ctype__scan_is) の例 (`do_scan_is` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedoscannota--ctypedoscannot"></a><a name="ctype__do_scan_not"></a>  ctype::do_scan_not  
 指定されたマスクに一致しない範囲内の最初の文字を検索するために呼び出される仮想関数。  
  
```  
virtual const CharType *do_scan_not(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字により照合されないマスク値。  
  
 `first`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 保護されているメンバー関数は、[do_is](#ctype__do_is)( `maskVal`, * `ptr`) が false となっている範囲 [ `first`, `last`) 内の最小ポインター `ptr` を返します。  
  
### <a name="example"></a>例  
  [scan_not](#ctype__scan_not) の例 (`do_scan_not` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedotolowera--ctypedotolower"></a><a name="ctype__do_tolower"></a>  ctype::do_tolower  
 文字または文字の範囲を小文字に変換するために呼び出される仮想関数。  
  
```  
virtual CharType do_tolower(CharType ch) const;

 
virtual const CharType *do_tolower(
    CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 小文字に変換される文字。  
  
 `first`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 保護されている最初のメンバー関数は、パラメーター `ch` を小文字で返します。 小文字の形態が存在しない場合、`ch` を返します。 保護されている&2; 番目のメンバー関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 保護されている&2; 番目のメンバー テンプレート関数は、各要素 `first` [ `I`] を `do_tolower`( `first` [ `I`]) で置換します。`I` の間隔は [0, `last` – `first`) です。  
  
### <a name="example"></a>例  
  [tolower](#ctype__tolower) の例 (`do_tolower` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedotouppera--ctypedotoupper"></a><a name="ctype__do_toupper"></a>  ctype::do_toupper  
 文字または文字の範囲を大文字に変換するために呼び出される仮想関数。  
  
```  
virtual CharType do_toupper(CharType ch) const;

 
virtual const CharType *do_toupper(
    CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 大文字に変換される文字。  
  
 `first`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 保護されている最初のメンバー関数は、パラメーター `ch` を大文字で返します。 大文字の形態が存在しない場合、`ch` を返します。 保護されている&2; 番目のメンバー関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 保護されている&2; 番目のメンバー テンプレート関数は、各要素 `first` [ `I`] を `do_toupper`( `first` [ `I`]) で置換します。`I` の間隔は [0, `last` – `first`) です。  
  
### <a name="example"></a>例  
  [toupper](#ctype__toupper) の例 (`do_toupper` を呼び出す) を参照してください。  
  
##  <a name="a-namectypedowidena--ctypedowiden"></a><a name="ctype__do_widen"></a>  ctype::do_widen  
 ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換するために呼び出される仮想関数。  
  
```  
virtual CharType do_widen(char byte) const;

 
virtual const char *do_widen(
    const char* first,   
    const char* last,   
    CharType* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `byte`  
 変換するネイティブ文字セットのうち、型 `char` の文字。  
  
 `first`  
 変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 変換後の文字範囲を格納する宛先範囲のうち、型 `CharType` の最初の文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 保護されている最初のメンバー関数は、ネイティブ型 `char` のパラメーター文字に対応する型 `CharType` の文字を返します。  
  
 保護されている&2; 番目のメンバー関数は、型 `char` のネイティブ文字から変換されたロケールで使用される型 `CharType` の文字の宛先範囲を示すポインターを返します。  
  
### <a name="remarks"></a>コメント  
 保護されている&2; 番目のメンバー テンプレート関数は、値 `do_widen`( `first`[ `I`]) を `dest`[ `I`] に格納します。`I` の間隔は [0, `last` - `first`) です。  
  
### <a name="example"></a>例  
  [widen](#ctype__widen) の例 (`do_widen` を呼び出す) を参照してください。  
  
##  <a name="a-namectypeisa--ctypeis"></a><a name="ctype__is"></a>  ctype::is  
 1 つの文字が特定の属性を持つかどうかをテストするか、範囲内の各文字の属性を分類して配列に格納します。  
  
```  
bool is(mask maskVal, CharType ch) const;

 
const CharType *is(
    const CharType* first,   
    const CharType* last,  
    mask* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字をテストするマスク値。  
  
 `ch`  
 属性をテストする文字。  
  
 `first`  
 属性を分類する範囲の最初の文字を示すポインター。  
  
 `last`  
 属性を分類する範囲の最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 各文字の属性の特徴になるマスク値を格納する配列の先頭を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、テストされた文字にマスク値により表される属性が含まれる場合、`true` を返します。そのような属性が含まれない場合、`false` を返します。  
  
 2 番目のメンバー関数は、属性を分類する範囲の最後の文字を示すポインターを返します。  
  
### <a name="remarks"></a>コメント  
 文字の属性を分類するマスク値は、ctype の派生元である、クラス [ctype_base クラス](../standard-library/ctype-base-class.md)により提供されます。 最初のメンバー関数は、ビットマスクと呼ばれ、ビット単位の論理演算子 (&#124;、&、^、~) によりマスク値の組み合わせから形成されるその最初のパラメーターの式を受け取ります。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_is.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main() {  
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );  
  
   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))  
      cout << "The character 'a' in locale loc1 is alphabetic."   
           << endl;  
   else  
      cout << "The character 'a' in locale loc1 is not alphabetic."   
           << endl;  
  
   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))  
      cout << "The character '!' in locale loc2 is alphabetic."   
           << endl;  
   else  
      cout << "The character '!' in locale loc2 is not alphabetic."   
           << endl;  
  
   char *string = "Hello, my name is John!";  
   ctype<char>::mask maskarray[30];  
   use_facet<ctype<char> > ( loc2 ).is(  
      string, string + strlen(string), maskarray );  
   for (unsigned int i = 0; i < strlen(string); i++) {  
      cout << string[i] << ": "  
           << (maskarray[i] & ctype_base::alpha  "alpha"  
                                                : "not alpha")  
           << endl;;  
   };  
}  
```  
  
##  <a name="a-namectypenarrowa--ctypenarrow"></a><a name="ctype__narrow"></a>  ctype::narrow  
 ロケールにより使用される型 `CharType` の文字を、ネイティブ文字セットの型 `char` の該当文字に変換します。  
  
```  
char narrow(CharType ch, char default = '\0') const;

 
const CharType* narrow(
    const CharType* first,   
    const CharType* last,  
    char default,   
    char* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 変換されるロケールにより使用される型 `Chartype` の文字。  
  
 `default`  
 型 `CharType` の文字に対となる型 `char` の文字がない場合にメンバー関数が割り当てる既定値。  
  
 `first`  
 変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 変換後の文字範囲を格納する宛先範囲のうち、型 `char` の最初の文字を示す const ポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、対になる片方が定義されていない場合、型 `CharType``default` のパラメーター文字に対応する型 `char` のネイティブ文字を返します。  
  
 2 番目のメンバー関数は、型 `CharType` の文字から変換されたネイティブ文字の宛先範囲を示すポインターを返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、[do_narrow](#ctype__do_narrow)( `ch`, `default`) を返します。 2 番目のメンバー関数は、[do_narrow](#ctype__do_narrow) ( `first`, `last`, `default`, `dest`) を返します。 基本ソース文字にのみ、`narrow` の下で一意の逆像 `CharType` が与えられることが約束されます。 これの基本ソース文字については、`narrow` ( [widen](#ctype__widen) ( **c** ), 0 ) == **c** という不変式が適用されます。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_narrow.cpp  
// compile with: /EHsc /W3  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "english" );  
   wchar_t *str1 = L"\x0392fhello everyone";  
   char str2 [16];  
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow  
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996  
   str2[wcslen(str1)] = '\0';  
   wcout << str1 << endl;  
   cout << &str2[0] << endl;  
}  
```  
  
```Output  
Xhello everyone  
```  
  
##  <a name="a-namectypescanisa--ctypescanis"></a><a name="ctype__scan_is"></a>  ctype::scan_is  
 指定されたマスクに一致する範囲内の最初の文字を検索します。  
  
```  
const CharType *scan_is(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字により照合されるマスク値。  
  
 `first`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたマスクに一致する範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last.` を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[do_scan_is](#ctype__do_scan_is)( `maskVal`, `first`, `last`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_scan_is.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char *string = "Hello, my name is John!";  
  
   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is  
      ( ctype_base::punct, string, string + strlen(string) );  
   cout << "The first punctuation is \"" << *i << "\" at position: "   
      << i - string << endl;  
}  
```  
  
```Output  
The first punctuation is "," at position: 5  
```  
  
##  <a name="a-namectypescannota--ctypescannot"></a><a name="ctype__scan_not"></a>  ctype::scan_not  
 指定されたマスクに一致しない範囲内の最初の文字を検索します。  
  
```  
const CharType *scan_not(
    mask maskVal,   
    const CharType* first,   
    const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `maskVal`  
 文字により照合されないマスク値。  
  
 `first`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 スキャンの対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 指定されたマスクに一致しない範囲内の最初の文字を示すポインター。 そのような値が存在しない場合、この関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、[do_scan_not](#ctype__do_scan_not)( `maskVal`, `first`, `last`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_scan_not.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char *string = "Hello, my name is John!";  
  
   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not  
      ( ctype_base::alpha, string, string + strlen(string) );  
   cout << "First nonalpha character is \"" << *i << "\" at position: "   
      << i - string << endl;  
}  
```  
  
```Output  
First nonalpha character is "," at position: 5  
```  
  
##  <a name="a-namectypetolowera--ctypetolower"></a><a name="ctype__tolower"></a>  ctype::tolower  
 文字または文字の範囲を小文字に変換します。  
  
```  
CharType tolower(CharType ch) const;

 
const CharType *tolower(CharType* first, const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 小文字に変換される文字。  
  
 `first`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、パラメーター `ch` を小文字で返します。 小文字の形態が存在しない場合、`ch` を返します。  
  
 2 番目のメンバー関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、[do_tolower](#ctype__do_tolower)( `ch`) を返します。 2 番目のメンバー関数は、[do_tolower](#ctype__do_tolower)( `first`, `last`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_tolower.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "German_Germany" );  
  
   char string[] = "HELLO, MY NAME IS JOHN";  
  
   use_facet<ctype<char> > ( loc1 ).tolower  
      ( string, string + strlen(string) );  
   cout << "The lowercase string is: " << string << endl;  
}  
```  
  
```Output  
The lowercase string is: hello, my name is john  
```  
  
##  <a name="a-namectypetouppera--ctypetoupper"></a><a name="ctype__toupper"></a>  ctype::toupper  
 文字または文字の範囲を大文字に変換します。  
  
```  
CharType toupper(CharType ch) const; 
const CharType *toupper(CharType* first, const CharType* last) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `ch`  
 大文字に変換される文字。  
  
 `first`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 大文字/小文字を変換する一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、パラメーター `ch` を大文字で返します。 大文字の形態が存在しない場合、`ch` を返します。  
  
 2 番目のメンバー関数は `last` を返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、[do_toupper](#ctype__do_toupper)( `ch`) を返します。 2 番目のメンバー関数は、[do_toupper](#ctype__do_toupper)( `first`, `last`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_toupper.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" );  
  
   char string[] = "Hello, my name is John";  
  
   use_facet<ctype<char> > ( loc1 ).toupper  
      ( string, string + strlen(string) );  
   cout << "The uppercase string is: " << string << endl;  
}  
```  
  
```Output  
The uppercase string is: HELLO, MY NAME IS JOHN  
```  
  
##  <a name="a-namectypewidena--ctypewiden"></a><a name="ctype__widen"></a>  ctype::widen  
 ネイティブ文字セットの `char` 型の文字を、ロケールで使用される `CharType` 型の対応する文字に変換します。  
  
```  
CharType widen(char byte) const; 
const char *widen(const char* first, const char* last, CharType* dest) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `byte`  
 変換するネイティブ文字セットのうち、型 char の文字。  
  
 `first`  
 変換の対象となる一定範囲の文字のうち、最初の文字を示すポインター。  
  
 `last`  
 変換の対象となる一定範囲の文字のうち、最初の文字の直後に続く文字を示すポインター。  
  
 `dest`  
 変換後の文字範囲を格納する宛先範囲のうち、型 `CharType` の最初の文字を示すポインター。  
  
### <a name="return-value"></a>戻り値  
 最初のメンバー関数は、ネイティブ型 `char` のパラメーター文字に対応する型 `CharType` の文字を返します。  
  
 2 番目のメンバー関数は、型 `char` のネイティブ文字から変換されたロケールで使用される型 `CharType` の文字の宛先範囲を示すポインターを返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、[do_widen](#ctype__do_widen)( `byte`) を返します。 2 番目のメンバー関数は、[do_widen](#ctype__do_widen)( `first`, `last`, `dest`) を返します。  
  
### <a name="example"></a>例  
  
```cpp  
// ctype_widen.cpp  
// compile with: /EHsc /W3  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc1 ( "English" );  
   char *str1 = "Hello everyone!";  
   wchar_t str2 [16];  
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen  
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996  
   str2[strlen(str1)] = '\0';  
   cout << str1 << endl;  
   wcout << &str2[0] << endl;  
  
   ctype<wchar_t>::char_type charT;  
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );  
}  
```  
  
```Output  
Hello everyone!  
Hello everyone!  
```  
  
## <a name="see-also"></a>関連項目  
 [\<locale>](../standard-library/locale.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


