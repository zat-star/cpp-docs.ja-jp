---
title: "CCRTHeap クラス | Microsoft Docs"
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
  - "ATL::CCRTHeap"
  - "ATL.CCRTHeap"
  - "CCRTHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCRTHeap クラス"
ms.assetid: 321bd6c5-1856-4ff7-8590-95044a1209f7
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCRTHeap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、CRT ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。  
  
## 構文  
  
```  
  
class CCRTHeap : public IAtlMemMgr  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CCRTHeap::Allocate](../Topic/CCRTHeap::Allocate.md)|メモリ ブロックを割り当てるためにこのメソッドを呼び出します。|  
|[CCRTHeap::Free](../Topic/CCRTHeap::Free.md)|このメモリ マネージャーが割り当てたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CCRTHeap::GetSize](../Topic/CCRTHeap::GetSize.md)|このメモリ マネージャーが割り当てたメモリ ブロックの割り当てられているサイズを取得するときにこのメソッドを呼び出します。|  
|[CCRTHeap::Reallocate](../Topic/CCRTHeap::Reallocate.md)|このメモリ マネージャーが割り当てるメモリの再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 `CCRTHeap` は [malloc](../../c-runtime-library/reference/malloc.md)、[可用性](../../c-runtime-library/reference/free.md)、[realloc](../../c-runtime-library/reference/realloc.md)と [\_msize](../Topic/_msize.md)を含む CRT ヒープ関数を使用してメモリ割り当て関数を実装します。  
  
## 使用例  
 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。  
  
## 継承階層  
 `IAtlMemMgr`  
  
 `CCRTHeap`  
  
## 必要条件  
 **Header:** atlmem.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)