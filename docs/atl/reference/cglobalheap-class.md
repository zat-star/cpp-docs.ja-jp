---
title: "CGlobalHeap クラス | Microsoft Docs"
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
  - "ATL.CGlobalHeap"
  - "ATL::CGlobalHeap"
  - "CGlobalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CGlobalHeap クラス"
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CGlobalHeap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、Win32 グローバル ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CGlobalHeap : public IAtlMemMgr  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CGlobalHeap::Allocate](../Topic/CGlobalHeap::Allocate.md)|メモリ ブロックを割り当てるためにこのメソッドを呼び出します。|  
|[CGlobalHeap::Free](../Topic/CGlobalHeap::Free.md)|このメモリ マネージャーが割り当てたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CGlobalHeap::GetSize](../Topic/CGlobalHeap::GetSize.md)|このメモリ マネージャーが割り当てたメモリ ブロックの割り当てられているサイズを取得するときにこのメソッドを呼び出します。|  
|[CGlobalHeap::Reallocate](../Topic/CGlobalHeap::Reallocate.md)|このメモリ マネージャーが割り当てるメモリの再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 `CGlobalHeap` は、Win32 グローバル ヒープ関数を使用してメモリ割り当て関数を実行します。  
  
> [!NOTE]
>  グローバル ヒープ関数は、他のメモリ管理関数より低速であり、できるだけ多くの機能はありません。  したがって、新しいアプリケーションでは [ヒープ関数](http://msdn.microsoft.com/library/windows/desktop/aa366711)を使用する必要があります。  これらのクラスは [CWin32Heap](../../atl/reference/cwin32heap-class.md) で使用できます。  グローバル関数は、またはとクリップボード関数が使用されます。  
  
## 使用例  
 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。  
  
## 継承階層  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## 必要条件  
 **Header:** atlmem.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)