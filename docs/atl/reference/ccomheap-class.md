---
title: "CComHeap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
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
ms.openlocfilehash: 323ad1aed4bae706ecbf66de769e33873f20c149
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomheap-class"></a>CComHeap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) COM メモリの割り当て関数を使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CComHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComHeap::Allocate](#allocate)|メモリ ブロックを割り当てるには、このメソッドを呼び出します。|  
|[CComHeap::Free](#free)|メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CComHeap::GetSize](#getsize)|メモリ マネージャーによって割り当てられたメモリ ブロックの割り当てのサイズを取得するには、このメソッドを呼び出します。|  
|[CComHeap::Reallocate](#reallocate)|このメソッドを呼び出し、このメモリ マネージャーによって割り当てられたメモリの再割り当てを行います。|  
  
## <a name="remarks"></a>コメント  
 `CComHeap`COM 割り当て関数を使用してメモリ割り当て関数を実装する[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)、 [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)、 [IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)、および[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)します。 最大割り当て可能なメモリ量に等しい**INT_MAX** (2,147,&483;,647) バイトです。  
  
## <a name="example"></a>例  
 例を参照してください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ATLComMem.h  
  
##  <a name="allocate"></a>CComHeap::Allocate  
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
 呼び出す[CComHeap::Free](#free)または[CComHeap::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)します。  
  
##  <a name="free"></a>CComHeap::Free  
 メモリ マネージャーによって割り当てられたメモリ ブロックを解放するには、このメソッドを呼び出します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 このメモリ マネージャーによって以前に割り当てられたメモリへのポインター。 NULL は有効な値であり、何も行われません。  
  
### <a name="remarks"></a>コメント  
 使用して実装[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)します。  
  
##  <a name="getsize"></a>CComHeap::GetSize  
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
 使用して実装[IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)します。  
  
##  <a name="reallocate"></a>CComHeap::Reallocate  
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
 呼び出す[CComHeap::Free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)します。  
  
## <a name="see-also"></a>関連項目  
 [DynamicConsumer サンプル](../../visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [クラス](../../atl/reference/iatlmemmgr-class.md)

