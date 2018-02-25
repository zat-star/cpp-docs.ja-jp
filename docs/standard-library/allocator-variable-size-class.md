---
title: "allocator_variable_size クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ecc149acc6a4c1b7d24a58cdf3e5f1d9c16872d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size クラス
[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_variable_size](../standard-library/max-variable-size-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type>  
class allocator_variable_size;
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
  
## <a name="remarks"></a>コメント  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) マクロは、このクラスを次のステートメント内の `name` パラメーターとして渡します: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>参照  
 [\<allocators>](../standard-library/allocators-header.md)



