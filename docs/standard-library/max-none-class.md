---
title: "max_none クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7db35adf828d66ecf9b6474e45960d22466b444
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="maxnone-class"></a>max_none クラス
[freelist](../standard-library/freelist-class.md) オブジェクトを最長値ゼロまでに制限する[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Max`|`freelist` に格納する要素の最大数を決定する、最大クラス。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|  
|[deallocated](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|  
|[full](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|  
|[released](#released)|フリー リスト上のメモリ ブロックの数を減らします。|  
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocated"></a>  max_none::allocated  
 割り当てられたメモリ ブロックの数を増やします。  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 `cache_freelist::allocate` による演算子 `new` への呼び出しが成功するたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `new` によって割り当てられたチャンク内のメモリ ブロックの数です。  
  
##  <a name="deallocated"></a>  max_none::deallocated  
 割り当てられたメモリ ブロックの数を減らします。  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 このメンバー関数は、`cache_freelist::deallocate` による演算子 `delete` への呼び出しがあるたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `delete` によって割り当て解除されたチャンク内のメモリ ブロックの数です。  
  
##  <a name="full"></a>  max_none::full  
 フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。  
  
```
bool full();
```  
  
### <a name="return-value"></a>戻り値  
 このメンバー関数は常に `true` を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しが `true` を返すと、`deallocate` はメモリ ブロックをフリー リストに置きます。false を返す場合は、`deallocate` は演算子 `delete` を呼び出してブロックの割り当てを解除します。  
  
##  <a name="released"></a>  max_none::released  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void released();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。  
  
##  <a name="saved"></a>  max_none::saved  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void saved();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は何も処理を行いません。 `cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。  
  
## <a name="see-also"></a>参照  
 [\<allocators>](../standard-library/allocators-header.md)



