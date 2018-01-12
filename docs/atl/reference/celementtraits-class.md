---
title: "CElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs: C++
helpviewer_keywords: CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ebe629a08170ce011b22595c8b821b278e16faa7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="celementtraits-class"></a>CElementTraits クラス
このクラスは、移動、コピーとを比較する、ハッシュ演算メソッドおよび関数を提供するコレクション クラスによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## <a name="remarks"></a>コメント  
 このクラスは、移動、コピー、比較、およびコレクション クラスのオブジェクトに格納されているハッシュ要素の既定の静的な関数とメソッドを提供します。 `CElementTraits`コレクション クラスでこれらの操作の既定のプロバイダーとして指定された[CAtlArray](../../atl/reference/catlarray-class.md)、 [CAtlList](../../atl/reference/catllist-class.md)、 [CRBMap](../../atl/reference/crbmap-class.md)、 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)、および[CRBTree](../../atl/reference/crbtree-class.md)です。  
  
 単純なデータ型の既定の実装で十分ですが、ユーザー指定の実装で関数やメソッドをオーバーライドする必要がありますより複雑なオブジェクトを格納するコレクション クラスを使用する場合。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcoll.h  
  
## <a name="see-also"></a>参照  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
