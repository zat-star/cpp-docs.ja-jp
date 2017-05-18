---
title: "CStringElementTraitsI クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 995c4798f92db3b3f065bf2176ab52ff53d282b0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI クラス
このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 に似ていますが[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)が小文字を区別しない比較を実行します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|2 つの文字列要素の場合の相違を無視して等しいかどうかを比較するこの静的関数を呼び出します。|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|場合の相違を無視して、2 つの文字列要素を比較するこの静的関数を呼び出します。|  
|[CStringElementTraitsI::Hash](#hash)|指定した文字列の要素のハッシュ値を計算するこの静的関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、文字列を比較し、ハッシュ値を作成するために、静的関数を提供します。 これらの関数は、コレクション クラスを使用して、文字列ベースのデータを格納する場合に便利です。 使用[CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)文字列オブジェクトに対処する参照として処理されます。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringElementTraitsI::CompareElements  
 2 つの文字列要素の場合の相違を無視して等しいかどうかを比較するこの静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が false でそれ以外の場合、等しい場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 比較で大文字小文字を区別されます。  
  
##  <a name="compareelementsordered"></a>CStringElementTraitsI::CompareElementsOrdered  
 場合の相違を無視して、2 つの文字列要素を比較するこの静的関数を呼び出します。  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str1`  
 最初の要素を文字列します。  
  
 `str2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 文字列が同じですが、 < 0="" if=""> `str1`がより小さい`str2`、または > 0 場合`str1`よりも大きい`str2`します。 [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)メソッドは、比較を実行するために使用します。  

  
### <a name="remarks"></a>コメント  
 比較で大文字小文字を区別されます。  
  
##  <a name="hash"></a>CStringElementTraitsI::Hash  
 指定した文字列の要素のハッシュ値を計算するこの静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
##  <a name="inargtype"></a>CStringElementTraitsI::INARGTYPE  
 コレクション クラスのオブジェクトに要素を追加するために使用するデータ型。  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE  
 コレクション クラスのオブジェクトから要素を取得するために使用するデータ型。  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CStringElementTraits クラス](../../atl/reference/cstringelementtraits-class.md)

