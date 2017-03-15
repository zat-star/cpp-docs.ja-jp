---
title: "CStringElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CStringElementTraits<T>
- ATL::CStringElementTraits<T>
- CStringElementTraits
- ATL.CStringElementTraits
- ATL::CStringElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f46ff072bcd0f772dac1bba52b114d82ee433112
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraits-class"></a>CStringElementTraits クラス
このクラスに格納するコレクション クラスで使用する静的関数が用意されています`CString`オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(静的)2 つの文字列要素が等しいかどうかを比較するには、この関数を呼び出します。|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(静的)この関数では、2 つの文字列要素を比較します。|  
|[CStringElementTraits::CopyElements](#copyelements)|(静的)コピーするには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素。|  
|[CStringElementTraits::Hash](#hash)|(静的)この関数では、指定された文字列の要素のハッシュ値を計算します。|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(静的)再配置するには、この関数を呼び出す`CString`コレクション クラスのオブジェクトに格納されている要素。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、コピー、移動、および文字列を比較して、ハッシュ値を作成するための静的関数を提供します。 これらの関数は、コレクション クラスを使用して、文字列ベースのデータを格納する場合に便利です。 使用[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)小文字を区別しない比較が必要とします。 使用[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)文字列オブジェクトの参照として処理するとき。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** cstringt.h  
  
##  <a name="a-namecompareelementsa--cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements  
 2 つの文字列要素が等しいかどうかを比較するこの静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が false でそれ以外の場合、等しい場合は true を返します。  
  
##  <a name="a-namecompareelementsordereda--cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 2 つの文字列要素の比較にこの静的関数を呼び出します。  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 文字列が同じですが、 < 0="" if=""> `str1`がより小さい`str2`、または > 0 場合`str1`よりも大きい`str2`します。 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)メソッドは、比較を実行するために使用します。  

  
##  <a name="a-namecopyelementsa--cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements  
 この静的関数をコピーする`CString`コレクション クラスのオブジェクトに格納されている要素。  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 コピー元のデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 コピーする最初の要素へのポインター。  
  
 `nElements`  
 コピーする要素の数。  
  
### <a name="remarks"></a>コメント  
 ソースおよびデスティネーションの要素は重複できません。  
  
##  <a name="a-namehasha--cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Hash  
 指定した文字列の要素のハッシュ値を計算するこの静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
##  <a name="a-nameinargtypea--cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="a-namerelocateelementsa--cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 この静的関数を再配置する`CString`コレクション クラスのオブジェクトに格納されている要素。  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>パラメーター  
 `pDest`  
 再配置されたデータを受信する最初の要素へのポインター。  
  
 `pSrc`  
 配置する場合に最初の要素へのポインター。  
  
 `nElements`  
 再配置する要素の数。  
  
### <a name="remarks"></a>コメント  
 この静的関数は[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)、これは、ほとんどのデータ型。 オブジェクトの移動中に、独自のメンバーへのポインターが含まれている場合は、この静的関数をオーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI クラス](../../atl/reference/cstringelementtraitsi-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

