---
title: "CDefaultCompareTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDefaultCompareTraits<T>
- ATL::CDefaultCompareTraits
- ATL.CDefaultCompareTraits
- ATL::CDefaultCompareTraits<T>
- CDefaultCompareTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
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
ms.openlocfilehash: 1d1253b7a7d69024465627cc9fb37fcd2afba693
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits クラス
このクラスは、既定の要素の比較関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(静的)2 つの要素が等しいかどうかを比較するには、この関数を呼び出します。|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(静的)この関数では、大小の要素を特定します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、コレクション クラスのオブジェクトに格納されている要素を比較するための&2; つの静的関数が含まれています。 このクラスは、によって使用されて、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="a-namecompareelementsa--cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 2 つの要素が等しいかどうかを比較するには、この関数を呼び出します。  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 1 番目の要素。  
  
 `element2`  
 2 番目の要素。  
  
### <a name="return-value"></a>戻り値  
 要素が false でそれ以外の場合、等しい場合は true を返します。  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装は、等しいかどうか ( `==`) 演算子。 単純なデータ型以外のオブジェクトをこの関数は、オーバーライドする必要があります。  
  
##  <a name="a-namecompareelementsordereda--cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 この関数では、大小の要素を特定します。  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>パラメーター  
 `element1`  
 1 番目の要素。  
  
 `element2`  
 2 番目の要素。  
  
### <a name="return-value"></a>戻り値  
 次の表に基づく整数が返されます。  
  
|条件|戻り値|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>コメント  
 この関数の既定の実装を使用して、 `==`、 ** \< **、および** > **演算子。 単純なデータ型以外のオブジェクトをこの関数は、オーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

