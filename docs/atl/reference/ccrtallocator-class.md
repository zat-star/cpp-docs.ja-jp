---
title: "CCRTAllocator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTAllocator
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
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
ms.openlocfilehash: 5154a095409705e96dee6f52c67d7c23b0e6691f
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtallocator-class"></a>CCRTAllocator クラス
このクラスは、CRT メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCRTAllocator::Allocate](#allocate)|(静的)メモリを割り当てるには、このメソッドを呼び出します。|  
|[CCRTAllocator::Free](#free)|(静的)メモリを解放するには、このメソッドを呼び出します。|  
|[CCRTAllocator::Reallocate](#reallocate)|(静的)メモリを再割り当てするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは使用[CHeapPtr](../../atl/reference/cheapptr-class.md) CRT メモリ割り当てルーチンを提供します。 対応するクラス[CComAllocator](../../atl/reference/ccomallocator-class.md)、COM ルーチンを使用するのと同じメソッドを提供します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlcore.h  
  
##  <a name="a-nameallocatea--ccrtallocatorallocate"></a><a name="allocate"></a>CCRTAllocator::Allocate  
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
 メモリを割り当てます。 参照してください[malloc](../../c-runtime-library/reference/malloc.md)詳細です。  
  
##  <a name="a-namefreea--ccrtallocatorfree"></a><a name="free"></a>CCRTAllocator::Free  
 この静的関数を呼び出してメモリを解放します。  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリを解放します。 参照してください[無料](../../c-runtime-library/reference/free.md)詳細です。  
  
##  <a name="a-namereallocatea--ccrtallocatorreallocate"></a><a name="reallocate"></a>CCRTAllocator::Reallocate  
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
 割り当てられたメモリの量を変更します。 参照してください[realloc](../../c-runtime-library/reference/realloc.md)詳細です。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

