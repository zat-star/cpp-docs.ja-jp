---
title: "CSimpleMapEqualHelper クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ddb793889748446b9613c91ce6fcefe28da32eb3
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper クラス
このクラスは、ヘルパーを[CSimpleMap](../../atl/reference/csimplemap-class.md)クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>パラメーター  
 `TKey`  
 主な要素です。  
  
 `TVal`  
 値の要素。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(静的)2 つのキーが等しいかどうかをテストします。|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(静的)2 つの値が等しいかどうかをテストします。|  
  
## <a name="remarks"></a>コメント  
 この特徴 (traits) クラスを補足するため、`CSimpleMap`クラスです。 2 つを比較するためのメソッドを提供`CSimpleMap`等しいかどうかの要素 (具体的には、キーと値コンポーネント) のオブジェクトします。 既定では、キーと値が比較`operator==()`、値が必要な追加機能を提供するこのクラスをオーバーライドできますが、マップに、独自の等値演算子に関連付けられていない複合データ型が含まれている場合。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpcoll.h  
  
##  <a name="a-nameisequalkeya--csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
 2 つのキーが等しいかどうかをテストします。  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>パラメーター  
 `k1`  
 最初のキー。  
  
 `k2`  
 2 番目のキー。  
  
### <a name="return-value"></a>戻り値  
 キーが等しい場合、false の場合それ以外の場合は true を返します。  
  
##  <a name="a-nameisequalvaluea--csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 2 つの値が等しいかどうかをテストします。  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>パラメーター  
 *v1*  
 最初の値。  
  
 *v2*  
 2 番目の値。  
  
### <a name="return-value"></a>戻り値  
 値が false でそれ以外の場合、等しい場合は true を返します。  
  
## <a name="see-also"></a>関連項目  
 [CSimpleMapEqualHelperFalse クラス](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

