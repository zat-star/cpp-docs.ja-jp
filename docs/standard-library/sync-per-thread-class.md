---
title: "sync_per_thread クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::sync_per_thread
- sync_per_thread
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_thread class
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
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
ms.openlocfilehash: 71d2dd481c2c14303c71ec461ddcb5c041859531
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="syncperthread-class"></a>sync_per_thread クラス
スレッドごとに個別のキャッシュ オブジェクトを提供する[同期フィルター](../standard-library/allocators-header.md)を記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Cache>  
class sync_per_thread
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Cache`|同期フィルターに関連付けられているキャッシュの型。 これは、[cache_chunklist](../standard-library/cache-chunklist-class.md)、[cache_freelist](../standard-library/cache-freelist-class.md)、[cache_suballoc](../standard-library/cache-suballoc-class.md) のいずれかです。|  
  
## <a name="remarks"></a>コメント  
 `sync_per_thread` を使用するアロケーターは、1 つのスレッドに割り当てられたブロックの割り当てを別のスレッドから解除できなくても、比較したときに等しい結果になりえます。 これらのアロケーターのいずれかを使用するときに、1 つのスレッドに割り当てられているメモリー ブロックが他のスレッドから参照できないようにする必要があります。 つまり、これらアロケーターのいずれかを使用するコンテナーは 1 つのスレッドによってのみアクセスする必要があります。  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocate](#allocate)|メモリのブロックを割り当てます。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
|[equals](#equals)|2 つのキャッシュが等しいかどうかを比較します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocate"></a>  sync_per_thread::allocate  
 メモリのブロックを割り当てます。  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`count`|割り当てられる配列内の要素の数。|  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、呼び出しの結果を、現在のスレッドに属しているキャッシュ オブジェクトの `cache::allocate(count)` に返します。 現在のスレッドにキャッシュ オブジェクトが割り当てられていない場合は、最初にキャッシュ オブジェクトを割り当ててください。  
  
##  <a name="deallocate"></a>  sync_per_thread::deallocate  
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
 メンバー関数は、現在のスレッドに属しているキャッシュ オブジェクトの `deallocate` を呼び出します。 現在のスレッドにキャッシュ オブジェクトが割り当てられていない場合は、最初にキャッシュ オブジェクトを割り当ててください。  
  
##  <a name="equals"></a>  sync_per_thread::equals  
 2 つのキャッシュが等しいかどうかを比較します。  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Cache`|同期フィルターのキャッシュ オブジェクト。|  
|`Other`|等しいかどうかを比較するキャッシュ オブジェクト。|  
  
### <a name="return-value"></a>戻り値  
 このオブジェクトまたは現在のスレッドの `Other` にキャッシュ オブジェクトが割り当てられていない場合は `false` です。 そうでない場合は、`operator==` を 2 つのキャッシュ オブジェクトに割り当てた結果を返します。  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




