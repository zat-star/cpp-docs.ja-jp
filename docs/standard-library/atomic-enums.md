---
title: "&lt;atomic&gt; 列挙型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd3a81c5-a19e-448f-952a-c34c717f21a9
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 94167b5068e3fb1370528d42c80d338a486cd68e
ms.lasthandoff: 02/24/2017

---
# <a name="ltatomicgt-enums"></a>&lt;atomic&gt; 列挙型
  
##  <a name="a-namememoryorderenuma--memoryorder-enum"></a><a name="memory_order_enum"></a>  memory_order 列挙型  
 メモリ位置に対する同期操作のシンボル名を提供します。 これらの操作は、1 つのスレッドの割り当てが別のスレッドにおいて表示される方法に影響します。  
  
```
typedef enum memory_order {
    memory_order_relaxed,
    memory_order_consume,
    memory_order_acquire,
    memory_order_release,
    memory_order_acq_rel,
    memory_order_seq_cst,
} memory_order;
```  
  
### <a name="remarks"></a>コメント  
  
|||  
|-|-|  
|`memory_order_relaxed`|順序付けは必要ありません。|  
|`memory_order_consume`|読み込み操作は、メモリ位置に対する消費操作として機能します。|  
|`memory_order_acquire`|読み込み操作は、メモリ位置に対する取得操作として機能します。|  
|`memory_order_release`|格納操作は、メモリ位置に対する開放操作として機能します。|  
|`memory_order_acq_rel`|`memory_order_acquire` と `memory_order_release` を組み合わせます。|  
|`memory_order_seq_cst`|`memory_order_acquire` と `memory_order_release` を組み合わせます。 `memory_order_seq_cst` としてマークされたメモリ アクセスには、順番に一貫性がある必要があります。|  
  
## <a name="see-also"></a>関連項目  
 [\<atomic>](../standard-library/atomic.md)




