---
title: "allocator_unbounded クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::allocator_unbounded
- allocators/stdext::allocators::allocator_unbounded
dev_langs:
- C++
helpviewer_keywords:
- allocator_unbounded class
ms.assetid: facbaea1-b320-4d99-96da-039b2642f352
caps.latest.revision: 17
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d749c57924764d8a099f9fce6115c3bd4b0cd879
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="allocatorunbounded-class"></a>allocator_unbounded クラス
[cache_freelist](../standard-library/cache-freelist-class.md) 型のキャッシュと [max_unbounded](../standard-library/max-unbounded-class.md) で管理されている長さを使用して、型 `Type` のオブジェクトに対し、ストレージの割り当てと解放を管理するオブジェクトを記述します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type>  
class allocator_unbounded;
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
  
## <a name="remarks"></a>コメント  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) マクロは、このクラスを次のステートメント内の `name` パラメーターとして渡します: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_unbounded), SYNC_DEFAULT, allocator_unbounded);`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




