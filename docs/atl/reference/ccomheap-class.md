---
title: "CComHeap クラス | Microsoft Docs"
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
  - "CComHeap"
  - "ATL.CComHeap"
  - "ATL::CComHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeap クラス"
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComHeap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、COM メモリ割り当て関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CComHeap : public IAtlMemMgr  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComHeap::Allocate](../Topic/CComHeap::Allocate.md)|メモリ ブロックを割り当てるためにこのメソッドを呼び出します。|  
|[CComHeap::Free](../Topic/CComHeap::Free.md)|このメモリ マネージャーが割り当てたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CComHeap::GetSize](../Topic/CComHeap::GetSize.md)|このメモリ マネージャーが割り当てたメモリ ブロックの割り当てられているサイズを取得するときにこのメソッドを呼び出します。|  
|[CComHeap::Reallocate](../Topic/CComHeap::Reallocate.md)|このメモリ マネージャーが割り当てるメモリの再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 `CComHeap` は [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727)、[CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722)、[IMalloc::GetSize](http://msdn.microsoft.com/library/windows/desktop/ms691226)と [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280)を含む COM の割り当て関数を使用してメモリ割り当て関数を実装します。  割り当てることができるメモリの最大量は **INT\_MAX** \(2147483647 バイト\) のと同じです。  
  
## 使用例  
 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。  
  
## 継承階層  
 `IAtlMemMgr`  
  
 `CComHeap`  
  
## 必要条件  
 **Header:** ATLComMem.h  
  
## 参照  
 [DynamicConsumer サンプル](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)