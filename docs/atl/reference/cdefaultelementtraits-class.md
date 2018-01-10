---
title: "CDefaultElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
dev_langs: C++
helpviewer_keywords: CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bb6731913d10402016f2148e1ae7705a73e98944
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits クラス
このクラスは、コレクション クラスの既定のメソッドおよび関数を提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>  
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="remarks"></a>コメント  
 このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュ要素の既定の静的な関数とメソッドを提供します。 このクラスは、その関数やメソッドから派生している[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)、および[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)、によって使用されて、 [CElementTraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)、および[CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)です。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
## <a name="see-also"></a>参照  
 [クラスの概要](../../atl/atl-class-overview.md)
