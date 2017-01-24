---
title: "IAtlMemMgr クラス | Microsoft Docs"
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
  - "IAtlMemMgr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAtlMemMgr クラス"
  - "メモリ, 管理"
  - "メモリ, メモリ マネージャー"
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAtlMemMgr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、メモリ マネージャーへのインターフェイスを表します。  
  
## 構文  
  
```  
  
__interface __declspec( uuid( "654F7EF5-CFDF-4df9-A450-6C6A13C622C0" )) IAtlMemMgr  
  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[割り当てます。](../Topic/IAtlMemMgr::Allocate.md)|メモリ ブロックを割り当てるためにこのメソッドを呼び出します。|  
|[Free](../Topic/IAtlMemMgr::Free.md)|メモリ ブロックを解放するには、このメソッドを呼び出します。|  
|[GetSize](../Topic/IAtlMemMgr::GetSize.md)|割り当てられたメモリ ブロックのサイズを取得するときにこのメソッドを呼び出します。|  
|[再割り当てします。](../Topic/IAtlMemMgr::Reallocate.md)|メモリ ブロックを再割り当てするには、このメソッドを呼び出します。|  
  
## 解説  
 このインターフェイスは [CComHeap](../../atl/reference/ccomheap-class.md)、[CCRTHeap](../../atl/reference/ccrtheap-class.md)、[CLocalHeap](../../atl/reference/clocalheap-class.md)、[CGlobalHeap](../../atl/reference/cglobalheap-class.md)、または [CWin32Heap](../../atl/reference/cwin32heap-class.md)によって実装されます。  
  
> [!NOTE]
>  ローカルおよびグローバル ヒープ関数は、他のメモリ管理関数より低速であり、できるだけ多くの機能はありません。  したがって、新しいアプリケーションでは [heap functions](http://msdn.microsoft.com/library/windows/desktop/aa366711)を使用する必要があります。  これらのクラスは [CWin32Heap](../../atl/reference/cwin32heap-class.md) で使用できます。  
  
## 使用例  
 [!CODE [NVC_ATL_Utilities#94](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#94)]  
  
## 必要条件  
 **Header:** atlmem.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)