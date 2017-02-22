---
title: "CLocalHeap クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CLocalHeap"
  - "ATL::CLocalHeap"
  - "CLocalHeap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLocalHeap クラス"
ms.assetid: 1ffa87a5-5fc8-4f8d-8809-58e87e963bd2
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CLocalHeap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、Win32 ローカル ヒープ関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CLocalHeap : public IAtlMemMgr  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CLocalHeap::Allocate](../Topic/CLocalHeap::Allocate.md)|メモリ ブロックを割り当てるためにこのメソッドを呼び出します。|  
|[CLocalHeap::Free](../Topic/CLocalHeap::Free.md)|このメモリ マネージャーが割り当てたメモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[CLocalHeap::GetSize](../Topic/CLocalHeap::GetSize.md)|このメモリ マネージャーが割り当てたメモリ ブロックの割り当てられているサイズを取得するときにこのメソッドを呼び出します。|  
|[CLocalHeap::Reallocate](../Topic/CLocalHeap::Reallocate.md)|このメモリ マネージャーが割り当てるメモリの再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 `CLocalHeap` は、Win32 ローカル ヒープ関数を使用してメモリ割り当て関数を実行します。  
  
> [!NOTE]
>  ローカル ヒープ関数は、他のメモリ管理関数より低速であり、できるだけ多くの機能はありません。  したがって、新しいアプリケーションでは [heap functions](http://msdn.microsoft.com/library/windows/desktop/aa366711)を使用する必要があります。  これらのクラスは [CWin32Heap](../../atl/reference/cwin32heap-class.md) で使用できます。  
  
## 使用例  
 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。  
  
## 継承階層  
 `IAtlMemMgr`  
  
 `CLocalHeap`  
  
## 必要条件  
 **Header:** atlmem.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap クラス](../../atl/reference/cwin32heap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)