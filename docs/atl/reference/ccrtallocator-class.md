---
title: "CCRTAllocator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCRTAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTAllocator クラス"
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CCRTAllocator クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、CRT メモリ ルーチンを使用するメモリ管理用のメソッドが用意されています。  
  
## 構文  
  
```  
  
class ATL::CCRTAllocator  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCRTAllocator::Allocate](../Topic/CCRTAllocator::Allocate.md)|\(静的\) メモリを割り当てるには、このメソッドを呼び出します。|  
|[CCRTAllocator::Free](../Topic/CCRTAllocator::Free.md)|\(静的\) メモリを解放するためにこのメソッドを呼び出します。|  
|[CCRTAllocator::Reallocate](../Topic/CCRTAllocator::Reallocate.md)|\(静的\) メモリ再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) して、このクラスは CRT のメモリ割り当てルーチンを提供するために使用されます。  COM は同じルーチンを使用して、[CComAllocator](../../atl/reference/ccomallocator-class.md)示され、同じメソッドを並べ替えます。  
  
## 必要条件  
 **ヘッダー :** atlcore.h  
  
## 参照  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)