---
title: "CDefaultHashTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 5191327e5e60935829750c7d1e04ba89fcddc771
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits クラス
このクラスは、ハッシュ値を計算するための静的関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(静的)指定された要素のハッシュ値を計算するには、この関数を呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスには、指定された要素のハッシュ値を返す&1; つの静的関数が含まれています。 このクラスは、によって使用されて、 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)します。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 指定された要素のハッシュ値を計算するには、この関数を呼び出します。  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `element`  
 要素。  
  
### <a name="return-value"></a>戻り値  
 ハッシュ値を返します。  
  
### <a name="remarks"></a>コメント  
 既定のハッシュ アルゴリズムは非常に単純: 戻り値は、要素数。 複雑なアルゴリズムが必要な場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)

