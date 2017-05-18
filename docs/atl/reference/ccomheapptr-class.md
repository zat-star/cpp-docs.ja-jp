---
title: "CComHeapPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs:
- C++
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
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
ms.openlocfilehash: 0e5196a98b8fd76b2e7e791fd2cd9549099a1cc9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheapptr-class"></a>CComHeapPtr クラス
ヒープのポインターを管理するためのスマート ポインター クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 `CComHeapPtr`派生した`CHeapPtr`を使用して、 [CComAllocator](../../atl/reference/ccomallocator-class.md) COM ルーチンを使用するメモリを割り当てられません。 参照してください[CHeapPtr](../../atl/reference/cheapptr-class.md)と[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)の利用可能なメソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 コンストラクターです。  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 既存の `CComHeapPtr` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 既存を使用してヒープのポインターを作成することができます必要に応じて`CComHeapPtr`オブジェクトです。 その場合、新しい`CComHeapPtr`オブジェクトには、新しいポインターとリソースを管理する責任が前提としています。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

