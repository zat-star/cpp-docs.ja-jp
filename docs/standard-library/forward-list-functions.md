---
title: "&lt;forward_list&gt; 系関数 | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 11
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 6696f42d2ba7cb6daabb8f2ff38093911838c1ca
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 系関数
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 2 つの前方リストの要素を交換します。  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|`forward_list` 型のオブジェクト。|  
|`right`|`forward_list` 型のオブジェクト。|  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数は、`left.swap(right)` を実行します。  
  
## <a name="see-also"></a>関連項目  
 [<forward_list>](../standard-library/forward-list.md)




