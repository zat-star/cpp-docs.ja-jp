---
title: "CStringRefElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 3709a5d4aac02651e5b6fafd441499fea1f8eabc
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits クラス
このクラスは、コレクション クラスのオブジェクトに格納された文字列に関連する静的関数を提供します。 文字列オブジェクトは参照として処理されます。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|2 つの文字列要素が等しいかどうかを比較するこの静的関数を呼び出します。|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|2 つの文字列要素の比較にこの静的関数を呼び出します。|  
|[CStringRefElementTraits::Hash](#hash)|指定した文字列の要素のハッシュ値を計算するこの静的関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、文字列を比較し、ハッシュ値を作成するために、静的関数を提供します。 これらの関数は、コレクション クラスを使用して、文字列ベースのデータを格納する場合に便利です。 異なり[CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)と[CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)、`CStringRefElementTraits`により、`CString`として渡される引数**const CString >/documents/report1.rdl」の**参照します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 2 つの文字列要素が等しいかどうかを比較するこの静的関数を呼び出します。  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 最初の要素を文字列します。  
  
 `element2`  
 2 番目の文字列要素。  
  
### <a name="return-value"></a>戻り値  
 要素が false でそれ以外の場合、等しい場合は true を返します。  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 2 つの文字列要素の比較にこの静的関数を呼び出します。  
  
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
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 指定した文字列の要素のハッシュ値を計算するこの静的関数を呼び出します。  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `str`  
 文字列の要素。  
  
### <a name="return-value"></a>戻り値  
 文字列の内容を使用して計算されたハッシュ値を返します。  
  
## <a name="see-also"></a>関連項目  
 [CElementTraitsBase クラス](../../atl/reference/celementtraitsbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

