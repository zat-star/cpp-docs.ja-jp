---
title: "CComAllocator クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
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
ms.openlocfilehash: d395d347e81b24462a41de5ae3b9d8791d7f82fd
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ccomallocator-class"></a>CComAllocator クラス
このクラスは、COM メモリ ルーチンを使用してメモリを管理するためのメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComAllocator
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|メモリの割り当てにこの静的メソッドを呼び出します。|  
|[CComAllocator::Free](#free)|割り当てられたメモリを解放するこの静的メソッドを呼び出します。|  
|[CComAllocator::Reallocate](#reallocate)|この静的メソッドを呼び出してメモリを再割り当てください。|  
  
## <a name="remarks"></a>コメント  
 このクラスは使用[CComHeapPtr](../../atl/reference/ccomheapptr-class.md) COM メモリ割り当てルーチンを提供します。 対応するクラス[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)、CRT ルーチンを使用するのと同じメソッドを提供します。  
  
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
 メモリを割り当てます。 参照してください[CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)詳細です。  
  
##  <a name="free"></a>CComAllocator::Free  
 割り当てられたメモリを解放するための静的なこの関数を呼び出します。  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリを解放します。 参照してください[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)詳細です。  
  
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
 メモリが不足している場合、割り当てられた領域に void ポインターを返します  
  
### <a name="remarks"></a>コメント  
 割り当てられたメモリの量を変更します。 参照してください[CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)詳細です。  
  
## <a name="see-also"></a>関連項目  
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

