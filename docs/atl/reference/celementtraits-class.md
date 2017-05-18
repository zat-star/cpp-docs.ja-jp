---
title: "CElementTraits クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
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
ms.sourcegitcommit: 6664a73967d3bdf9859556f21744737718018e74
ms.openlocfilehash: 8b7b91bd9e027a3946160d95da1199c24af3502d
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

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
  
 単純なデータ型の既定の実装で十分ですより複雑なオブジェクトを格納するコレクション クラスを使用する場合、関数とメソッドを上書きして、ユーザー指定の実装でします。  
  
 詳細については、次を参照してください。 [ATL コレクション クラス](../../atl/atl-collection-classes.md)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcoll.h  
  
## <a name="see-also"></a>関連項目  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

