---
title: "atomic_flag 構造体 |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_flag
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d51596a70b0b79d39fee3095fc2b28fdd7c697f3
ms.lasthandoff: 02/24/2017

---
# <a name="atomicflag-structure"></a>atomic_flag 構造体
`bool` フラグをアトミックに設定およびクリアするオブジェクトについて記述します。 アトミック フラグの操作は常にロック制御不要です。  
  
## <a name="syntax"></a>構文  
  
```
struct atomic_flag;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[atomic_flag::clear メソッド](#atomic_flag__clear_method)|格納されたフラグを `false` に設定します。|  
|[atomic_flag::test_and_set メソッド](#atomic_flag__test_and_set_method)|格納されたフラグを `true` に設定し、フラグの初期値を返します。|  
  
## <a name="remarks"></a>コメント  
 `atomic_flag` オブジェクトは、[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear_function)、[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit_function)、[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set_function)、および [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit_function) の非メンバー関数に渡すことができます。 これらは、`ATOMIC_FLAG_INIT` の値を使用して初期化できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atomic  
  
 **名前空間:** std  
  
##  <a name="a-nameatomicflagclearmethoda--atomicflagclear-method"></a><a name="atomic_flag__clear_method"></a>  atomic_flag::clear メソッド  
 指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、`*this` に格納されている `bool` フラグを `false` に設定します。  
  
```
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Order`  
 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)。  
  
##  <a name="a-nameatomicflagtestandsetmethoda--atomicflagtestandset-method"></a><a name="atomic_flag__test_and_set_method"></a>  atomic_flag::test_and_set メソッド  
 指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、`*this` に格納されている `bool` フラグを `true` に設定します。  
  
```
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Order`  
 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)。  
  
### <a name="return-value"></a>戻り値  
 `*this` に格納されているフラグの初期値。  
  
## <a name="see-also"></a>関連項目  
 [\<atomic>](../standard-library/atomic.md)




