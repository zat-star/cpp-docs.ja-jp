---
title: "num_get クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- num_get
- std::num_get
- std.num_get
- xlocnum/std::num_get
dev_langs:
- C++
helpviewer_keywords:
- num_get class
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
caps.latest.revision: 18
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 1669ee33324bacd1795b541f99cbef0531956867
ms.lasthandoff: 02/24/2017

---
# <a name="numget-class"></a>num_get クラス
`CharType` 型のシーケンスから数値への変換を制御するためにロケール ファセットとして使用できるオブジェクトを表すテンプレート クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class num_get : public locale::facet;
```  
  
#### <a name="parameters"></a>パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
 `InputIterator`  
 数値の get 関数が入力を読み取る反復子の型。  
  
## <a name="remarks"></a>コメント  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は&0; です。 格納されている値に初めてアクセスしようとすると、**id** に一意の正の値が格納されます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[num_get](#num_get__num_get)|シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_get__char_type)|ロケールによって使用される文字を表すために使用される型。|  
|[iter_type](#num_get__iter_type)|入力反復子を表す型。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[do_get](#num_get__do_get)|文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。|  
|[get](#num_get__get)|文字シーケンスから数値のまたはブール値を抽出します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<locale>  
  
 **名前空間:** std  
  
##  <a name="a-namenumgetchartypea--numgetchartype"></a><a name="num_get__char_type"></a>  num_get::char_type  
 ロケールによって使用される文字を表すために使用される型。  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **CharType** のシノニムです。  
  
##  <a name="a-namenumgetdogeta--numgetdoget"></a><a name="num_get__do_get"></a>  num_get::do_get  
 文字シーケンスから数値またはブール値を抽出するために呼び出される仮想関数。  
  
```
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `first`  
 数値を読み取る文字の範囲の開始位置。  
  
 `last`  
 数値を読み取る文字の範囲の終了位置。  
  
 `_Iosbase`  
 変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。  
  
 `_State`  
 失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照)。  
  
 `val`  
 読み取られた値。  
  
### <a name="return-value"></a>戻り値  
 値が読み取られた後の反復子。  
  
### <a name="remarks"></a>コメント  
 1 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long& val`  
  
 `) const;`  
  
 この関数は、シーケンス `[``first``,` `last``)` の `first` から始め、空でない完全な整数入力フィールドを認識するまで、連続した要素と一致します。 成功すると、このフィールドを `long``,` 型の同等の値に変換し、結果を `val` に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、この関数は `val` に何も格納しないで、`state` に `ios_base::failbit` を設定します。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 いずれの場合も、戻り値が `last` と等しい場合、関数は `state` に `ios_base::eofbit` を設定します。  
  
 整数入力フィールドは、スキャン機能がファイルから一連の `char` 要素と一致および変換する際に使用する規則と同じ規則で変換されます。 (このような `char` 要素は、単純な一対一のマッピングで `Elem` 型の同等の要素にマップされると想定されます。)同等のスキャン変換仕様は次のように決定されます。  
  
 `iosbase.`[ios_base::flags](../standard-library/ios-base-class.md#ios_base__flags)`() & ios_base::basefield == ios_base::`[oct](../standard-library/ios-functions.md#oct) の場合、変換仕様は `lo` です。  
  
 `iosbase.flags() & ios_base::basefield == ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は `lx` です。  
  
 `iosbase.flags() & ios_base::basefield == 0` の場合、変換仕様は `li` です。  
  
 それ以外の場合、変換仕様は `ld` です。  
  
 整数入力フィールドの形式は、さらに、[ロケール ファセット](../standard-library/locale-class.md#facet_class) `fac` で決定されます。これは、[use_facet](../standard-library/locale-functions.md#use_facet) `<`[numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base::getloc](../standard-library/ios-base-class.md#ios_base__getloc)`())` の呼び出しによって返されます。 具体的には、次のように使用します。  
  
 `fac.` [numpunct::grouping](../standard-library/numpunct-class.md#numpunct__grouping) `()` は、小数点の左側の数字をグループ化する方法を決定します。  
  
 `fac.` [numpunct::thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) `()` は、小数点の左側にある数字のグループを区切るシーケンスを決定します。  
  
 数値入力フィールドに `fac.thousands_sep()` のインスタンスがない場合、グループ化の制約は強制されません。 それ以外の場合は、`fac.grouping()` によって強制されたグループ化の制約が適用され、スキャンの変換が行われる前に区切り記号が削除されます。  
  
 4 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、`ld` の変換仕様を `lu` に置き換えている点が異なります。 成功すると、数値入力フィールドを `unsigned long` 型の値に変換し、その値を `val` に格納します。  
  
 5 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long long& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、`ld` の変換仕様を `lld` に置き換えている点が異なります。 成功すると、数値入力フィールドを `long long` 型の値に変換し、その値を `val` に格納します。  
  
 6 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long long& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、`ld` の変換仕様を `llu` に置き換えている点が異なります。 成功すると、数値入力フィールドを `unsigned long long` 型の値に変換し、その値を `val` に格納します。  
  
 7 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `float& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` は、整数桁と小数桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。  
  
 8 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `double& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 `fac.`[numpunct::decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` は、整数桁と小数桁を区切るシーケンスを決定します。 同等のスキャン変換指定子は `lf` です。  
  
 9 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long double& val`  
  
 `) const;`  
  
 この関数の動作は&8; 番目と同じですが、同等のスキャン変換指定子が `Lf` である点が異なります。  
  
 10 番目のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `void *& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、同等のスキャン変換指定子が `p` である点が異なります。  
  
 最後 (11 番目) のプロテクト仮想メンバー関数:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `bool& val`  
  
 `) const;`  
  
 この関数の動作は&1; 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功すると、ブール値入力フィールドを `bool` 型の値に変換し、その値を `val` に格納します。  
  
 ブール値入力フィールドは、次の&2; つの形式のいずれかになります。 `iosbase.flags() & ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha) が false の場合、これは整数入力フィールドと同じですが、変換後の値が 0 (false の場合) または 1 (true の場合) のいずれかである必要がある点が異なります。 それ以外の場合、シーケンスは `fac.`[numpunct::falsename](../standard-library/numpunct-class.md#numpunct__falsename)`()` (false の場合) または `fac.`[numpunct::truename](../standard-library/numpunct-class.md#numpunct__truename)`()` (true の場合) のいずれかに一致する必要があります。  
  
### <a name="example"></a>例  
  [get](#num_get__get) の例 (仮想メンバー関数が `do_get` で呼び出される) を参照してください。  
  
##  <a name="a-namenumgetgeta--numgetget"></a><a name="num_get__get"></a>  num_get::get  
 文字シーケンスから数値のまたはブール値を抽出します。  
  
```
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `first`  
 数値を読み取る文字の範囲の開始位置。  
  
 `last`  
 数値を読み取る文字の範囲の終了位置。  
  
 `_Iosbase`  
 変換で使用されるフラグが含まれる [Ios_base](../standard-library/ios-base-class.md)。  
  
 `_State`  
 失敗した場合に failbit が追加される状態 (「[ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate)」を参照)。  
  
 `val`  
 読み取られた値。  
  
### <a name="return-value"></a>戻り値  
 値が読み取られた後の反復子。  
  
### <a name="remarks"></a>コメント  
 すべてのメンバー関数が [do_get](#num_get__do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`) を返します。  
  
 1 番目のプロテクト仮想メンバー関数は、シーケンス [ `first`, `last`) の先頭から始め、空でない完全な整数入力フィールドを認識するまで、連続した要素との一致を試みます。 成功すると、このフィールドを **long** 型の同等の値に変換し、結果を `val` に格納します。 これは、数値入力フィールドを超える先頭の要素を指す反復子を返します。 それ以外の場合、この関数は `val` に何も格納しないで、_*State* に `ios_base::failbit` を設定します。 これは、有効な整数入力フィールドのプレフィックスを超える先頭の要素を指す反復子を返します。 いずれの場合も、戻り値が **last** と等しい場合、関数は `_State` に `ios_base::eofbit` を設定します。  
  
 整数入力フィールドは、スキャン機能がファイルから一連の `char` 要素と一致および変換する際に使用する規則と同じ規則で変換されます。 このような `char` 要素は、単純な一対一のマッピングで **CharType** 型の同等の要素にマップされると想定されます。 同等のスキャン変換仕様は次のように決定されます。  
  
-   場合**iosbase**します。 [フラグ](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[oct](../standard-library/ios-functions.md#oct)、変換仕様は**lo**します。  
  
-   **iosbase.flags** & **ios_base::basefield** == `ios_base::`[hex](../standard-library/ios-functions.md#hex) の場合、変換仕様は **lx** です。  
  
-   **iosbase.flags** & **ios_base::basefield** == 0 の場合、変換仕様は `li` です。  
  
-   それ以外の場合、変換仕様は **ld** です。  
  
 整数の入力フィールドの形式によって決定、[ロケールのファセット](../standard-library/locale-class.md#facet_class)**要素**呼び出しによって返される[use_facet](../standard-library/locale-functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md) \< **Elem**> ( **iosbase**します。 [getloc](../standard-library/ios-base-class.md#ios_base__getloc))。 具体的には、次のように使用します。  
  
- **fac**. [グループ化](../standard-library/numpunct-class.md#numpunct__grouping)数字が小数点の左側にグループ化方法を決定します。  
  
- **fac**. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep)小数点の左側にある数字のグループを区切るシーケンスを決定します。  
  
 インスタンスがない場合**要素**します。 `thousands_sep`グループ化の制約は適用されず、数字の入力フィールドで発生します。 によって、グループ化の制約が課されるそれ以外の場合、**要素**します。 **グループ化**が適用されると、スキャンの変換が行われる前に、区切り記号は削除されます。  
  
 2 番目のプロテクト仮想メンバー関数:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```  
  
 この関数の動作は&1; 番目と同じですが、**ld** の変換仕様を **lu** に置き換えている点が異なります。 成功すると、数値入力フィールドを `unsigned long` 型の値に変換し、その値を `val` に格納します。  
  
 3 番目のプロテクト仮想メンバー関数：  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```  
  
 この関数の動作は&1; 番目と同じですが、空でない完全な浮動小数点入力フィールドとの一致を試みる点が異なります。 **fac**. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)を小数点以下桁数の整数部の桁数を区切るシーケンスを決定します。 同等のスキャン変換指定子は **lf** です。  
  
 4 番目のプロテクト仮想メンバー関数:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```  
  
 この関数の動作は&3; 番目と同じですが、同等のスキャン変換指定子が **Lf** である点が異なります。  
  
 5 番目のプロテクト仮想メンバー関数:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
 この関数の動作は&1; 番目と同じですが、同等のスキャン変換指定子が **p** である点が異なります。  
  
 6 番目のプロテクト仮想メンバー関数:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
 この関数の動作は&1; 番目と同じですが、空でない完全なブール値入力フィールドとの一致を試みる点が異なります。 成功すると、ブール値入力フィールドを `bool` 型の値に変換し、その値を `val` に格納します。  
  
 ブール値入力フィールドは、次の&2; つの形式のいずれかになります。 場合**iosbase**します。 **フラグ** & `ios_base::`[boolalpha](../standard-library/ios-functions.md#boolalpha)は**false**、これは、整数の入力フィールドと同じ点が変換された値が 0 にする必要があります (の**false**) または 1 (の**true**)。 それ以外の場合、シーケンスに一致する必要がありますか**要素**します。 [falsename](../standard-library/numpunct-class.md#numpunct__falsename) (の**false**)、または**要素**します。 [truename](../standard-library/numpunct-class.md#numpunct__truename) (の**true**)。  
  
### <a name="example"></a>例  
  
```cpp  
// num_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream<char> psz, psz2;  
   psz << "-1000,56";  
  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;  
  
   psz.imbue( loc );  
   use_facet <num_get <char> >  
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),  
           basic_istream<char>::_Iter(0), psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get( ) FAILED" << endl;  
   else  
      cout << "money_get( ) = " << fVal << endl;  
}  
```  
  
##  <a name="a-namenumgetitertypea--numgetitertype"></a><a name="num_get__iter_type"></a>  num_get::iter_type  
 入力反復子を表す型。  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター **InputIterator** のシノニムです。  
  
##  <a name="a-namenumgetnumgeta--numgetnumget"></a><a name="num_get__num_get"></a>  num_get::num_get  
 シーケンスから数値を抽出するために使用される `num_get` 型のオブジェクトのコンストラクター。  
  
```
explicit num_get(size_t _Refs = 0);
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
  
 コンストラクターは、**locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`) を使用して、その基本オブジェクトを初期化します。  
  
## <a name="see-also"></a>関連項目  
 [\<locale>](../standard-library/locale.md)   
 [facet クラス](../standard-library/locale-class.md#facet_class)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)




