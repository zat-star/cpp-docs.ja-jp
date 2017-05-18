---
title: "allocator_newdel クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators::allocator_newdel
- allocators/stdext::allocators::allocator_newdel
- allocators/stdext::allocator_newdel
- allocator_newdel
- stdext::allocators::allocator_newdel
dev_langs:
- C++
helpviewer_keywords:
- allocator_newdel class
ms.assetid: 62666cd2-3afe-49f7-9dd1-9bbbb154da98
caps.latest.revision: 18
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 45a80316ddd36cccbe5e5aab6757163d45bc2f07
ms.contentlocale: ja-jp
ms.lasthandoff: 04/19/2017

---
# <a name="allocatornewdel-class"></a>allocator_newdel クラス
`operator delete` を使用してメモリ ブロックの割り当てを解除し、`operator new` を使用してメモリ ブロックを割り当てるアロケーターを実装します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Type>  
class allocator_newdel;
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Type`|アロケーターによって割り当てられた要素の型。|  
  
## <a name="remarks"></a>コメント  
 [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) マクロは、このクラスを次のステートメント内の `name` パラメーターとして渡します: `ALLOCATOR_DECL(CACHE_FREELIST stdext::allocators::max_none), SYNC_DEFAULT, allocator_newdel);`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




