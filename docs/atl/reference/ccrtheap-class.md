---
title: "CCRTHeap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCRTHeap
- ATLMEM/ATL::CCRTHeap
- ATLMEM/ATL::CCRTHeap::Allocate
- ATLMEM/ATL::CCRTHeap::Free
- ATLMEM/ATL::CCRTHeap::GetSize
- ATLMEM/ATL::CCRTHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTHeap class
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1b4df6949794981867051437835d043196613afa
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtheap-class"></a>CCRTHeap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) CRT ヒープ関数を使用します。  
  
## <a name="syntax"></a>構文  
  
```
class CCRTHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCRTHeap::Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|  
|[CCRTHeap::Free](#free)|メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CCRTHeap::GetSize](#getsize)|メモリ マネージャーによって割り当てられたメモリ ブロックの割り当てのサイズを取得するには、このメソッドを呼び出します。|  
|[CCRTHeap::Reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|  
  
## <a name="remarks"></a>コメント  
 `CCRTHeap`メモリ割り当て関数が CRT を使用するヒープなど、機能を実装する[malloc](../../c-runtime-library/reference/malloc.md)、[無料](../../c-runtime-library/reference/free.md)、 [realloc](../../c-runtime-library/reference/realloc.md)、および[_msize](../../c-runtime-library/reference/msize.md)します。  
  
## <a name="example"></a>例  
 例を参照してください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlmem.h  
  
##  <a name="allocate"></a>CCRTHeap::Allocate  
 メモリ ブロックを割り当てるには、このメソッドを呼び出します。  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[CCRTHeap::Free](#free)または[CCRTHeap::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[malloc](../../c-runtime-library/reference/malloc.md)します。  
  
##  <a name="free"></a>CCRTHeap::Free  
 メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行われません。  
  
### <a name="remarks"></a>コメント  
 使用して実装[無料](../../c-runtime-library/reference/free.md)します。  
  
##  <a name="getsize"></a>CCRTHeap::GetSize  
 メモリ マネージャーによって割り当てられたメモリ ブロックの割り当てのサイズを取得するには、このメソッドを呼び出します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのサイズをバイト単位で返します。  
  
### <a name="remarks"></a>コメント  
 使用して実装[_msize](../../c-runtime-library/reference/msize.md)します。  
  
##  <a name="reallocate"></a>CCRTHeap::Reallocate  
 このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[CCRTHeap::Free](#free)このメソッドによって割り当てられたメモリを解放します。 使用して実装[realloc](../../c-runtime-library/reference/realloc.md)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [クラス](../../atl/reference/iatlmemmgr-class.md)

