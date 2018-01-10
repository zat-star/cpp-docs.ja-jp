---
title: "CCRTAllocator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs: C++
helpviewer_keywords: CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84c8f800e0b68e23fe33ca0a7e1c1d977bcc344e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ccrtallocator-class"></a>CCRTAllocator クラス
このクラスは、CRT メモリ ルーチンを使用しているメモリを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Ccrtallocator::allocate](#allocate)|(静的)メモリを割り当てるには、このメソッドを呼び出します。|  
|[Ccrtallocator::free](#free)|(静的)このメソッドを呼び出してメモリを解放します。|  
|[Ccrtallocator::reallocate](#reallocate)|(静的)このメソッドを呼び出してメモリを再割り当てください。|  
  
## <a name="remarks"></a>コメント  
 このクラスによって使用[CHeapPtr](../../atl/reference/cheapptr-class.md) CRT メモリ割り当てルーチンを提供します。 対応するクラス[CComAllocator](../../atl/reference/ccomallocator-class.md)、COM ルーチンを使用する場合と同じ方法を提供します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcore.h  
  
##  <a name="allocate"></a>Ccrtallocator::allocate  
 メモリを割り当てる場合は、この静的関数を呼び出します。  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 割り当てるバイト数。  
  
### <a name="return-value"></a>戻り値  
 メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。  
  
### <a name="remarks"></a>コメント  
 メモリを割り当てます。 参照してください[malloc](../../c-runtime-library/reference/malloc.md)詳細についてはします。  
  
##  <a name="free"></a>Ccrtallocator::free  
 メモリを解放する、この静的関数を呼び出します。  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリを解放します。 参照してください[空き](../../c-runtime-library/reference/free.md)詳細についてはします。  
  
##  <a name="reallocate"></a>Ccrtallocator::reallocate  
 メモリを再割り当てする場合は、この静的関数を呼び出します。  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
 `nBytes`  
 再割り当てするバイト数。  
  
### <a name="return-value"></a>戻り値  
 メモリが不足している場合、割り当てられた領域に void ポインターを返すか、NULL を返します。  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリの量を変更します。 参照してください[realloc](../../c-runtime-library/reference/realloc.md)詳細についてはします。  
  
## <a name="see-also"></a>参照  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
