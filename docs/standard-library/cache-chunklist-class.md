---
title: "cache_chunklist クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 3d8047844a96cf80e64ab7aae5d1e7d9f4a85474
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="cachechunklist-class"></a>cache_chunklist クラス
1 つのサイズのメモリ ブロックを割り当ておよび割り当て解除する[ブロック アロケーター](../standard-library/allocators-header.md)を定義します。  
  
## <a name="syntax"></a>構文  
  
```
template <std::size_t Sz, std::size_t Nelts = 20>  
class cache_chunklist
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Sz`|割り当てられる配列内の要素の数。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは `operator new` を使用して生メモリ チャンクを割り当て、必要なときにブロックをサブ割り当てしてメモリ ブロック用の記憶域を割り当てます。また、割り当てが解除されたメモリ ブロックをチャンクごとの独立したフリー リストに格納し、どのメモリ ブロックも使用中でないときは `operator delete` を使用してチャンクの割り当てを解除します。  
  
 各メモリ ブロックは、`Sz` バイトの使用可能なメモリと、そのブロックが属しているチャンクへのポインターを保持します。 各チャンクには `Nelts` メモリ ブロック、3 つのポインター、int、`operator new` と `operator delete` に必要なデータが保持されます。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[cache_chunklist](#cache_chunklist)|`cache_chunklist` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocate](#allocate)|メモリのブロックを割り当てます。|  
|[deallocate](#deallocate)|指定した位置で始まるストレージから、指定された数のオブジェクトを解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocate"></a>  cache_chunklist::allocate  
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
  
##  <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist  
 `cache_chunklist` 型のオブジェクトを構築します。  
  
```
cache_chunklist();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="deallocate"></a>  cache_chunklist::deallocate  
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




