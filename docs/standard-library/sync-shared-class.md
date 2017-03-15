---
title: "sync_shared クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sync_shared
- allocators/stdext::sync_shared
- stdext.sync_shared
- stdext::sync_shared
dev_langs:
- C++
helpviewer_keywords:
- sync_shared class
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b510fbe0b93f97222a093007300a3b3d054d1505
ms.lasthandoff: 02/24/2017

---
# <a name="syncshared-class"></a>sync_shared クラス
すべてのアロケーターによって共有されているキャッシュ オブジェクトへのアクセスを制御するためにミューテックスを使用する[同期フィルター](../standard-library/allocators-header.md)を表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Cache>  
class sync_shared
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Cache`|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocate](#sync_shared__allocate)|メモリのブロックを割り当てます。|  
|[deallocate](#sync_shared__deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[equals](#sync_shared__equals)|2 つのキャッシュが等しいかどうかを比較します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="a-namesyncsharedallocatea--syncsharedallocate"></a><a name="sync_shared__allocate"></a>  sync_shared::allocate  
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
 メンバー関数はミューテックスをロックし、`cache.allocate(count)` を呼び出し、ミューテックスをロック解除し、以前の `cache.allocate(count)` の呼び出しの結果を返します。 `cache` はキャッシュ オブジェクトを表します。  
  
##  <a name="a-namesyncshareddeallocatea--syncshareddeallocate"></a><a name="sync_shared__deallocate"></a>  sync_shared::deallocate  
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
 このメンバー関数は、ミューテックスをロックし、`cache.deallocate(ptr, count)` (`cache` はキャッシュ オブジェクトを表す) を呼び出し、その後ミューテックスをロック解除します。  
  
##  <a name="a-namesyncsharedequalsa--syncsharedequals"></a><a name="sync_shared__equals"></a>  sync_shared::equals  
 2 つのキャッシュが等しいかどうかを比較します。  
  
```
bool equals(const sync_shared<Cache>& Other) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Cache`|同期フィルターに関連付けられているキャッシュの型。|  
|`Other`|等しいかどうかを比較するキャッシュ。|  
  
### <a name="return-value"></a>戻り値  
 `cache.equals(Other.cache)` (`cache` はキャッシュ オブジェクトを表す) の結果が `true` の場合は `true`、それ以外の場合は `false`。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




