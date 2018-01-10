---
title: "atomic_flag 構造体 |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs: C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d45d1cd6b0b0e4d12ee9a5567ee172cb7e772c3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
|[clear](#clear)|格納されたフラグを `false` に設定します。|  
|[test_and_set](#test_and_set)|格納されたフラグを `true` に設定し、フラグの初期値を返します。|  
  
## <a name="remarks"></a>コメント  
 `atomic_flag` オブジェクトは、[atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear)、[atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit)、[atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set)、および [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) の非メンバー関数に渡すことができます。 これらは、`ATOMIC_FLAG_INIT` の値を使用して初期化できます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<アトミック >  
  
 **名前空間:** std  
  
##  <a name="clear"></a>atomic_flag::clear
 指定された [memory_order](../standard-library/atomic-enums.md#memory_order_enum) の制約内で、`*this` に格納されている `bool` フラグを `false` に設定します。  
  
```
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```  
  
### <a name="parameters"></a>パラメーター  
 `Order`  
 [memory_order](../standard-library/atomic-enums.md#memory_order_enum)。  
  
##  <a name="test_and_set"></a>atomic_flag::test_and_set
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
  
## <a name="see-also"></a>参照  
 [\<atomic>](../standard-library/atomic.md)



