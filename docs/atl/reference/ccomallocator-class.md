---
title: "CComAllocator クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAllocator"
  - "ATL::CComAllocator"
  - "CComAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAllocator クラス"
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAllocator クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、COM メモリ ルーチンを使用したメモリ管理用のメソッドが用意されています。  
  
## 構文  
  
```  
  
class CComAllocator  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComAllocator::Allocate](../Topic/CComAllocator::Allocate.md)|メモリを割り当てるため、この静的メソッドを呼び出します。|  
|[CComAllocator::Free](../Topic/CComAllocator::Free.md)|割り当てたメモリを解放するためにこの静的メソッドを呼び出します。|  
|[CComAllocator::Reallocate](../Topic/CComAllocator::Reallocate.md)|メモリの再割り当てするには、この静的メソッドを呼び出します。|  
  
## 解説  
 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) によってこのクラスは、COM メモリ割り当てルーチンを提供するために使用されます。  同等には、CRT ルーチンを使用して、[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)示され、同じメソッドを並べ替えます。  
  
## 必要条件  
 atlbase.h**Header:**  
  
## 参照  
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)