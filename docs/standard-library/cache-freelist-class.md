---
title: "cache_freelist クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_freelist
- stdext::cache_freelist
- cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- cache_freelist class
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 7d15c40a0116e8d6de2346a7da74045c2a7ee795
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="cachefreelist-class"></a>cache_freelist クラス
1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <std::size_t Sz, class Max>  
class cache_freelist
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Sz`|割り当てられる配列内の要素の数。|  
|`Max`|フリー リストの最大サイズを表す max クラスです。 [max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。|  
  
## <a name="remarks"></a>コメント  
 cache_freelist テンプレート クラスは、サイズが `Sz` であるフリー リストを保持します。 フリー リストがいっぱいになると、`operator delete` を使用してメモリ ブロックの割り当てを解除します。 フリー リストが空になると、`operator new` を使用して新しいメモリ ブロックを割り当てます。 フリー リストの最大サイズは、max クラスで `Max` パラメーターに渡されたクラスによって決定されます。  
  
 各メモリ ブロックは、`Sz` バイトの使用可能なメモリと、`operator new` および `operator delete` に必要なデータを保持します。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[cache_freelist](#cache_freelist)|`cache_freelist` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocate](#allocate)|メモリのブロックを割り当てます。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocate"></a>  cache_freelist::allocate  
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
  
##  <a name="cache_freelist"></a>  cache_freelist::cache_freelist  
 `cache_freelist` 型のオブジェクトを構築します。  
  
```
cache_freelist();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="deallocate"></a>  cache_freelist::deallocate  
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
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




