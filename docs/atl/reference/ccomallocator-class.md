---
title: "CComAllocator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs: C++
helpviewer_keywords: CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1ba2b12110e4c312b84b2a24831687e782cc339
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ccomallocator-class"></a>CComAllocator クラス
このクラスは、COM メモリ ルーチンを使用しているメモリを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|メモリの割り当てにこの静的メソッドを呼び出します。|  
|[CComAllocator::Free](#free)|この静的メソッドを呼び出して割り当てられたメモリを解放します。|  
|[CComAllocator::Reallocate](#reallocate)|この静的メソッドを呼び出してメモリを再割り当てください。|  
  
## <a name="remarks"></a>コメント  
 このクラスによって使用[CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM メモリ割り当てルーチンを提供します。 対応するクラス[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)、CRT ルーチンを使用する場合と同じ方法を提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="allocate"></a>CComAllocator::Allocate  
 メモリを割り当てる場合は、この静的関数を呼び出します。  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 割り当てるバイト数。  
  
### <a name="return-value"></a>戻り値  
 メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。  
  
### <a name="remarks"></a>コメント  
 メモリを割り当てます。 参照してください[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)詳細についてはします。  
  
##  <a name="free"></a>CComAllocator::Free  
 割り当てられたメモリを解放する、この静的関数を呼び出します。  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリを解放します。 参照してください[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)詳細についてはします。  
  
##  <a name="reallocate"></a>CComAllocator::Reallocate  
 メモリを再割り当てする場合は、この静的関数を呼び出します。  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
 `nBytes`  
 再割り当てするバイト数。  
  
### <a name="return-value"></a>戻り値  
 十分なメモリがある場合、割り当てられた領域に void ポインターを返します  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリの量を変更します。 参照してください[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)詳細についてはします。  
  
## <a name="see-also"></a>関連項目  
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
