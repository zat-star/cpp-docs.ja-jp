---
title: "extent クラス (C++ AMP) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::extent
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 8aa89b882ed075a8cdf0166d43fde1a5bfe7683d
ms.lasthandoff: 02/24/2017

---
# <a name="extent-class-c-amp"></a>extent クラス (C++ AMP)
ベクターを表します*N*の境界を指定する整数値、 *N*-0 の原点が次元空間です。 ベクターの値は最上位から最下位へ順に並べ替えられます。  
  
### <a name="syntax"></a>構文  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rank`  
 `extent` オブジェクトのランク。  

 ## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[エクステントのコンス トラクター](#ctor)|`extent` クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[メソッドが含まれています](#contains)|指定された `extent` オブジェクトには指定されたランクがあることを確認します。|  
|[サイズ メソッド](#size)|範囲の全体の線形サイズを返します (要素単位)。|  
|[タイル メソッド](#tile)|指定された次元によるタイルの範囲の `tiled_extent` オブジェクトを生成します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator-演算子](#operator_min)|対応する `extent` 要素から `index` 要素を減算することによって作成された新しい `extent` オブジェクトを返します。|  
|[演算子--演算子](#operator_min_min)|`extent` オブジェクトの各要素をデクリメントします。|  
|[operator % = 演算子](#operator_mod_eq)|その要素がある数で除算された場合、`extent` オブジェクトの各要素の剰余を計算します。|  
|[演算子 * = 演算子](#operator_star_eq)|`extent` オブジェクトの各要素をある数で乗算します。|  
|[演算子/= 演算子](#operator_min_eq)|`extent` オブジェクトの各要素をある数で除算します。|  
|[extent:\[\]](#operator_at)|指定したインデックス位置にある要素を返します。|  
|[operator + 演算子](#operator_add)|対応する `extent` 要素および `index` 要素を追加することによって作成された新しい `extent` オブジェクトを返します。|  
|[operator++ 演算子](#operator_add_add)|`extent` オブジェクトの各要素をインクリメントします。|  
|[演算子 + = 演算子](#operator_add_eq)|指定した数を `extent` オブジェクトの各要素に加算します。|  
|[operator = 演算子](#operator_eq)|別の `extent` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator-= 演算子](#operator_min_eq)|指定した数を `extent` オブジェクトの各要素から減算します。|  

  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[rank 定数](#rank)|`extent` オブジェクトのランクを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `extent`  


## <a name="a-namecontainsa-contains"></a><a name="contains"></a>含まれています 

示すかどうか、指定した[インデックス](index-class.md)'範囲' オブジェクト内で値が含まれます。  
  
### <a name="syntax"></a>構文  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 テストする `index` 値。  
  
### <a name="return-value"></a>戻り値  
 指定した `true` 値が `index` オブジェクトに含まれている場合は `extent`。それ以外の場合は `false`。  
  
##  <a name="a-namectora-extent"></a><a name="ctor"></a>エクステント 

'範囲' クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Array`  
 新しい `_Rank` オブジェクトを作成するために使用される `extent` 整数の配列。  
  
 `_I`  
 範囲の長さ。  
  
 `_I0`  
 最上位の次元の長さ。  
  
 `_I1`  
 最上位の次の次元の長さ。  
  
 `_I2`  
 最下位の次元の長さ。  
  
 `_Other`  
 新しい `extent` オブジェクトが基づく `extent` オブジェクト。  
  
## <a name="remarks"></a>コメント  
 パラメーターなしのコンストラクターが、3 のランクを持つ `extent` オブジェクトを初期化します。  
  
 `extent` オブジェクトを構築するために配列が使用された場合、その配列の長さは `extent` オブジェクトのランクと一致する必要があります。  
  
##  <a name="a-nameoperatormodeqa-operator"></a><a name="operator_mod_eq"></a>operator % = 

その要素がある数で除算された場合は、'範囲' 内の各要素の剰余 (余り) を計算します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 5/3 の余りを数。  
  
### <a name="return-value"></a>戻り値  
 `extent` オブジェクト。  
  
##  <a name="a-nameoperatorstareqa-operator"></a><a name="operator_star_eq"></a>演算子 * = 

指定した数で '範囲' オブジェクト内の各要素を乗算します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 乗算対象の数です。  
  
### <a name="return-value"></a>戻り値  
 `extent` オブジェクト。  
  
## <a name="a-nameoperatoradda-operator"></a><a name="operator_add"></a>operator + 

対応する `extent` 要素および `index` 要素を追加することによって作成された新しい `extent` オブジェクトを返します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 追加する要素を含む `index` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 新しい `extent` オブジェクト。  
  
##  <a name="a-nameoperatoraddadda-operator"></a><a name="operator_add_add"></a>+ + 演算子 

'範囲' オブジェクトの各要素をインクリメントします。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>戻り値  
 前置演算子の場合は、`extent` オブジェクト (`*this`) です。 後置演算子の場合は、新しい `extent` オブジェクトです。  
  
##  <a name="a-nameoperatoraddeqa-operator"></a><a name="operator_add_eq"></a>operator + = 

'範囲' オブジェクトの各要素に指定された数を追加します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 追加する数、インデックス、または範囲。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる `extent` オブジェクト。  
  
##  <a name="a-nameoperatormina-operator-"></a><a name="operator_min"></a>演算子の 

この `extent` オブジェクトの対応する要素から指定された `index` オブジェクトの各要素を減算して、新しい `extent` オブジェクトを作成します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 減算する要素を含む `index` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 新しい `extent` オブジェクト。  
  
##  <a name="a-nameoperatorminmina-operator--"></a><a name="operator_min_min"></a>-演算子 

デクリメント '範囲' オブジェクト内の各要素。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>戻り値  
 前置演算子の場合は、`extent` オブジェクト (`*this`) です。 後置演算子の場合は、新しい `extent` オブジェクトです。  
  
##  <a name="a-nameoperatordiveqa-operator"></a><a name="operator_div_eq"></a>演算子/= 

'範囲' オブジェクト内の各要素を指定した数で除算します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 除数。  
  
### <a name="return-value"></a>戻り値  
 `extent` オブジェクト。  
  
##  <a name="a-nameoperatormineqa-operator-"></a><a name="operator_min_eq"></a>-= 演算子 

'範囲' オブジェクトの各要素から指定した数を減算します。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
 減算する数。  
  
### <a name="return-value"></a>戻り値  
 結果として得られる `extent` オブジェクト。  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>演算子 = 

これには、別の '範囲' オブジェクトの内容をコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `extent` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `extent` オブジェクトへの参照。  
  
##  <a name="a-nameoperatorata-extentoperator-"></a><a name="operator_at"></a>extent:\[\] 
指定したインデックス位置にある要素を返します。  
  
### <a name="syntax"></a>構文  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 0 からランク - 1 までの整数。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にある要素。  
  
##  <a name="a-namerankconstanta-rank"></a><a name="rank_constant"></a>ランク 

'範囲' オブジェクトのランクを格納します。  
  
### <a name="syntax"></a>構文  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>サイズ 

全体の線形サイズを返す、 `extent` (要素単位) のオブジェクト。  
  
### <a name="syntax"></a>構文  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="a-nametilea-tile"></a><a name="tile"></a>並べて表示します。 

指定されたタイルの次元を持つ tiled_extent オブジェクトを生成します。

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>パラメーター
`_Dim0`タイル化された範囲の最上位のコンポーネントです。
`_Dim1`タイル化された範囲の次に、最上位のコンポーネント。
`_Dim2`タイル化された範囲の最下位のコンポーネントです。


  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

