---
title: "rts_alloc クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::rts_alloc
- allocators/stdext::rts_alloc
- rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
dev_langs:
- C++
helpviewer_keywords:
- rts_alloc class
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: fe127f896fa902f4a8cdb44454cf6e4c5f449e79
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="rtsalloc-class"></a>rts_alloc クラス
rts_alloc テンプレート クラスは、キャッシュ インスタンスの配列を保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別する[フィルター](../standard-library/allocators-header.md)を記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Cache>  
class rts_alloc
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Cache`|配列に含まれているキャッシュ インスタンスの型。 これは、[cache_chunklist クラス](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、複数のブロック アロケーター インスタンスを保持し、コンパイル時ではなく、実行時に割り当てと割り当て解除に使用するインスタンスを判別します。 再バインドをコンパイルできないコンパイラと一緒に使用します。  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocate](#allocate)|メモリのブロックを割り当てます。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocate"></a>  rts_alloc::allocate  
 メモリのブロックを割り当てます。  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`count`|割り当てられる配列内の要素の数。|  
  
### <a name="return-value"></a>戻り値  
 割り当てられたオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、要求されたブロック サイズ `count` によってインデックス `_IDX` が定義される `caches[_IDX].allocate(count)` を返します。また `count` が大きすぎる場合は `operator new(count)` を返します。 キャッシュ オブジェクトを表す `cache`。  
  
##  <a name="deallocate"></a>  rts_alloc::deallocate  
 指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|記憶域から割り当てを解除される最初のオブジェクトへのポインター。|  
|`count`|記憶域から割り当てを解除されるオブジェクトの数。|  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、要求されたブロック サイズ `count` によってインデックス `_IDX` が定義される `caches[_IDX].deallocate(ptr, count)` を呼び出します。また `count` が大きすぎる場合は `operator delete(ptr)` を返します。  
  
##  <a name="equals"></a>  rts_alloc::equals  
 2 つのキャッシュが等しいかどうかを比較します。  
  
```
bool equals(const sync<_Cache>& _Other) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Cache`|フィルターに関連付けられているキャッシュ オブジェクト。|  
|`_Other`|等しいかどうかを比較するキャッシュ オブジェクト。|  
  
### <a name="remarks"></a>コメント  
 `caches[0].equals(other.caches[0])` の結果の場合は `true`、それ以外の場合は `false` です。 `caches` はキャッシュ オブジェクトの配列を表します。  
  
## <a name="see-also"></a>関連項目  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)   
 [\<allocators>](../standard-library/allocators-header.md)




