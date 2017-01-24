---
title: "CWin32Heap クラス | Microsoft Docs"
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
  - "ATL::CWin32Heap"
  - "ATL.CWin32Heap"
  - "CWin32Heap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWin32Heap クラス"
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWin32Heap クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、Win32 ヒープ割り当て関数を使用して、[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) を実装します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CWin32Heap : public IAtlMemMgr  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md)|コンストラクターです。|  
|[CWin32Heap::~CWin32Heap](../Topic/CWin32Heap::~CWin32Heap.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWin32Heap::Allocate](../Topic/CWin32Heap::Allocate.md)|オブジェクトのヒープからメモリ ブロックを割り当てます。|  
|[CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md)|既存のヒープにヒープのオブジェクトをアタッチします。|  
|[CWin32Heap::Detach](../Topic/CWin32Heap::Detach.md)|既存のヒープからヒープのオブジェクトをデタッチします。|  
|[CWin32Heap::Free](../Topic/CWin32Heap::Free.md)|前に割り当てるヒープからメモリを解放します。|  
|[CWin32Heap::GetSize](../Topic/CWin32Heap::GetSize.md)|ヒープのオブジェクトから割り当てられたメモリ ブロックのサイズを返します。|  
|[CWin32Heap::Reallocate](../Topic/CWin32Heap::Reallocate.md)|オブジェクトのヒープからメモリ ブロックを再割り当てします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CWin32Heap::m\_bOwnHeap](../Topic/CWin32Heap::m_bOwnHeap.md)|ヒープのハンドルの現在の所有権を決定するために使用するフラグ。|  
|[CWin32Heap::m\_hHeap](../Topic/CWin32Heap::m_hHeap.md)|ヒープ内のオブジェクトへのハンドル。|  
  
## 解説  
 Win32 を使用して`CWin32Heap` の実装のメモリ割り当てメソッドは、[HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) と [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701)を含む、割り当て関数をコンパイルします。  他のヒープのクラスとは異なり、`CWin32Heap` は、メモリを割り当てる前に有効なヒープのハンドルを提供することを要求しています: 他のクラスは、プロセス ヒープの使用になります。  ハンドルはコンストラクターまたは [CWin32Heap::Attach](../Topic/CWin32Heap::Attach.md) のメソッドに指定できます。  メソッドを [CWin32Heap::CWin32Heap](../Topic/CWin32Heap::CWin32Heap.md) の詳細については、" "を参照してください。  
  
## 使用例  
 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)の例を参照してください。  
  
## 継承階層  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## 必要条件  
 **Header:** atlmem.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [IAtlMemMgr クラス](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)