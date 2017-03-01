---
title: "index クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::index
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
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
ms.openlocfilehash: 55a44499ca9bbd5149a4528a31c1417b60ba7fa3
ms.lasthandoff: 02/24/2017

---
# <a name="index-class"></a>index クラス
定義、 *N*の次元のインデックス pographics cpp amp.md します。  
  
## <a name="syntax"></a>構文  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Rank`  
 ランク (次元数)。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[インデックスのコンス トラクター](#ctor)|`index` クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[演算子--演算子](#operator--)|`index` オブジェクトの各要素をデクリメントします。|  
|[operator(mod) = 演算子](#operator_mod_eq)|その要素がある数で除算された場合、`index` オブジェクトの各要素の剰余を計算します。|  
|[演算子 * = 演算子](#operator_star_eq)|`index` オブジェクトの各要素をある数で乗算します。|  
|[演算子/= 演算子](#operator_div_eq)|`index` オブジェクトの各要素をある数で除算します。|  
|[index::operator\[\]](#operator_at)|指定したインデックス位置にある要素を返します。|  
|[operator++ 演算子](#operator_add_add)|`index` オブジェクトの各要素をインクリメントします。|  
|[演算子 + = 演算子](#operator_add_eq)|指定した数を `index` オブジェクトの各要素に加算します。|  
|[operator = 演算子](#operator_eq)|指定された `index` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator-= 演算子](#operator_-_eq)|指定した数を `index` オブジェクトの各要素から減算します。|  

  
### <a name="public-constants"></a>パブリック定数  
  
|名前|説明|  
|----------|-----------------|  
|[rank 定数](#rank)|`index` オブジェクトのランクを格納します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `index`  
  
## <a name="remarks"></a>コメント  
 `index`構造体の座標ベクターを表します*N*一意の場所を指定する整数、 *N*-次元空間です。 ベクターの値は最上位から最下位へ順に並べ替えられます。 使用してコンポーネントの値を取得する[演算子演算子 =](#operator_eq)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amp.h  
  
 **名前空間:** Concurrency  


## <a name="a-nameindexctora-index-constructor"></a><a name="index_ctor"></a>インデックスのコンス トラクター
Index クラスの新しいインスタンスを初期化します。

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>パラメーター

_Array  
ランク値を持つ&1; 次元配列。  
_I  
1 次元インデックスのインデックス位置。  
_I0  
最上位の次元の長さ。  
_I1  
最上位の次の次元の長さ。  
_I2  
最下位の次元の長さ。  
_Other  
新しいインデックス オブジェクトの基になるインデックス オブジェクトです。  

## <a name="a-nameoperator--a--operator--"></a><a name="operator--"></a>-演算子
デクリメント インデックス オブジェクトの各要素。  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="a-nameoperatormodeqa--operatormod"></a><a name="operator_mod_eq"></a>operator(mod) =   
その要素が指定された数で除算したときに、インデックス オブジェクトの各要素の剰余 (余り) を計算します。

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>パラメーター
_Rhs、剰余を検索するで除算する数値。
Index オブジェクトの値を返します。

## <a name="a-nameoperatorstareqa--operator"></a><a name="operator_star_eq"></a>演算子 * =   
指定したインデックス オブジェクト内の各要素を乗算します。
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Rhs に乗算する数値。

## <a name="a-nameoperatordiveqa--operator"></a><a name="operator_div_eq"></a>演算子/= 
Index オブジェクト内の各要素を指定した数で除算します。

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs で除算する数値。

## <a name="a-nameoperatorata--operator"></a><a name="operator_at"></a>  operator\[\]  
指定した位置にあるインデックスのコンポーネントを返します。

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>パラメーター
_Index 0 からランク-1 までの整数。

### <a name="return-value"></a>戻り値
指定したインデックス位置にある要素。

### <a name="remarks"></a>コメント
次の例では、インデックスのコンポーネント値を表示します。
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="a-nameoperatoraddadda--operator"></a><a name="operator_add_add"></a>+ + 演算子   
Index オブジェクトの各要素をインクリメントします。
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>戻り値
前置演算子のインデックス オブジェクト (* この)。 後置演算子は、新しいインデックス オブジェクトです。

## <a name="a-nameoperatoraddeqa--operator"></a><a name="operator_add_eq"></a>operator + =   
Index オブジェクトの各要素に指定された数を追加します。
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Rhs 加算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。

## <a name="a-nameoperatoreqa--operator"></a><a name="operator_eq"></a>  operator=   
これには、指定したインデックス オブジェクトの内容をコピーします。
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>パラメーター
_Other からコピー先のインデックス オブジェクトです。

### <a name="return-value"></a>戻り値
このインデックス オブジェクトへの参照。

## <a name="a-nameoperator-eqa--operator-"></a><a name="operator_-_eq"></a>-= 演算子
Index オブジェクトの各要素から指定した数を減算します。
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>パラメーター
_Rhs 減算する数。

### <a name="return-value"></a>戻り値
インデックス オブジェクトです。   

## <a name="a-nameranka--rank"></a><a name="rank"></a>ランク  
  Index オブジェクトのランクを取得します。
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

