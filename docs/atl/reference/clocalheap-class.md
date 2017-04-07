---
title: "CLocalHeap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLocalHeap
- ATLMEM/ATL::CLocalHeap
- ATLMEM/ATL::CLocalHeap::Allocate
- ATLMEM/ATL::CLocalHeap::Free
- ATLMEM/ATL::CLocalHeap::GetSize
- ATLMEM/ATL::CLocalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CLocalHeap class
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
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
ms.openlocfilehash: 6a5caaa360970578aee4432fd40af9aa0e391d90
ms.lasthandoff: 02/24/2017

---
# <a name="clocalheap-class"></a>CLocalHeap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)ローカル ヒープの Win32 関数を使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CLocalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLocalHeap::Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|  
|[CLocalHeap::Free](#free)|メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CLocalHeap::GetSize](#getsize)|メモリ マネージャーによって割り当てられたメモリ ブロックの割り当てのサイズを取得するには、このメソッドを呼び出します。|  
|[CLocalHeap::Reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|  
  
## <a name="remarks"></a>コメント  
 `CLocalHeap`ローカル ヒープの Win32 関数を使用してメモリ割り当て関数を実装します。  
  
> [!NOTE]
>  ローカル ヒープ関数では、他のメモリ管理関数よりも低速で、多くの機能を提供しません。 したがって、新しいアプリケーションを使用する必要があります、[ヒープ関数](http://msdn.microsoft.com/library/windows/desktop/aa366711)します。 これらで使用できる、 [CWin32Heap](../../atl/reference/cwin32heap-class.md)クラスです。  
  
## <a name="example"></a>例  
 例を参照してください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlmem.h  
  
##  <a name="allocate"></a>CLocalHeap::Allocate  
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
 呼び出す[CLocalHeap::Free](#free)または[CLocalHeap::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723)のフラグ パラメーターを持つ**LMEM_FIXED**します。  
  
##  <a name="free"></a>CLocalHeap::Free  
 メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行われません。  
  
### <a name="remarks"></a>コメント  
 使用して実装[LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730)します。  
  
##  <a name="getsize"></a>CLocalHeap::GetSize  
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
 使用して実装[LocalSize](http://msdn.microsoft.com/library/windows/desktop/aa366745)します。  
  
##  <a name="reallocate"></a>CLocalHeap::Reallocate  
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
 呼び出す[CLocalHeap::Free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[LocalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366742)します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [クラス](../../atl/reference/iatlmemmgr-class.md)

