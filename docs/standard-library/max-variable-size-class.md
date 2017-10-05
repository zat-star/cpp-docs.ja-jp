---
title: "max_variable_size クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: 18
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 957f7ce1d5156afeaca7e976678a3954755441d8
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="maxvariablesize-class"></a>max_variable_size クラス
割り当てたメモリ ブロックの数にほぼ比例した最長値までに [freelist](../standard-library/freelist-class.md) オブジェクトを制御する、[最大クラス](../standard-library/allocators-header.md) オブジェクトを記述します。  
  
## <a name="syntax"></a>構文  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|`max_variable_size` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[allocated](#allocated)|割り当てられたメモリ ブロックの数を増やします。|  
|[deallocated](#deallocated)|割り当てられたメモリ ブロックの数を減らします。|  
|[full](#full)|フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。|  
|[released](#released)|フリー リスト上のメモリ ブロックの数を減らします。|  
|[saved](#saved)|フリー リスト上のメモリ ブロックの数を減らします。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="allocated"></a>  max_variable_size::allocated  
 割り当てられたメモリ ブロックの数を増やします。  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、格納されている値 `_Nallocs` に `_Nx` を追加します。 このメンバー関数は、`cache_freelist::allocate` による演算子 `new` への呼び出しが成功するたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `new` によって割り当てられたチャンク内のメモリ ブロックの数です。  
  
##  <a name="deallocated"></a>  max_variable_size::deallocated  
 割り当てられたメモリ ブロックの数を減らします。  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`_Nx`|増分値。|  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、格納されている値 `_Nallocs` から `_Nx` を引きます。 このメンバー関数は、`cache_freelist::deallocate` による演算子 `delete` への呼び出しがあるたび、その後に呼び出されます。 引数 `_Nx` は、演算子 `delete` によって割り当て解除されたチャンク内のメモリ ブロックの数です。  
  
##  <a name="full"></a>  max_variable_size::full  
 フリー リストにメモリ ブロックを追加する必要があるかどうかを示す値を返します。  
  
```
bool full();
```  
  
### <a name="return-value"></a>戻り値  
 `true` if `_Nallocs / 16 + 16 <= _Nblocks`.  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は `cache_freelist::deallocate` によって呼び出されます。 呼び出しが `true` を返すと、`deallocate` はメモリ ブロックをフリー リストに置きます。false を返す場合は、`deallocate` は演算子 `delete` を呼び出してブロックの割り当てを解除します。  
  
##  <a name="max_variable_size"></a>  max_variable_size::max_variable_size  
 `max_variable_size` 型のオブジェクトを構築します。  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>コメント  
 このコンストラクターは、格納された値 `_Nblocks` および `_Nallocs` をゼロに初期化します。  
  
##  <a name="released"></a>  max_variable_size::released  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void released();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、格納された値 `_Nblocks` を減らします。 現在の最大クラスの `released` メンバー関数は、`cache_freelist::allocate` によって、フリー リストからメモリ ブロックが削除されるたびに、呼び出されます。  
  
##  <a name="saved"></a>  max_variable_size::saved  
 フリー リスト上のメモリ ブロックの数を減らします。  
  
```
void saved();
```  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、格納された値 `_Nblocks` を増やします。 このメンバー関数は、`cache_freelist::deallocate` によって、フリー リストにメモリ ブロックが置かれるたびに、呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




