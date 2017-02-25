---
title: "CHeapPtrBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CHeapPtrBase"
  - "ATL::CHeapPtrBase"
  - "CHeapPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrBase クラス"
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtrBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、スマート ヒープ ポインター クラスの基本クラスとなります。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T,  
class Allocator= CCRTAllocator   
> class CHeapPtrBase  
```  
  
#### パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 使用するメモリ割り当てのクラス。  既定では、CRT ルーチンがメモリの割り当てと解放するために使用されます。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrBase::~CHeapPtrBase](../Topic/CHeapPtrBase::~CHeapPtrBase.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrBase::AllocateBytes](../Topic/CHeapPtrBase::AllocateBytes.md)|メモリを割り当てるには、このメソッドを呼び出します。|  
|[CHeapPtrBase::Attach](../Topic/CHeapPtrBase::Attach.md)|既存のポインターの所有権を持つようにこのメソッドを呼び出します。|  
|[CHeapPtrBase::Detach](../Topic/CHeapPtrBase::Detach.md)|ポインターの所有権を解放するためにこのメソッドを呼び出します。|  
|[CHeapPtrBase::Free](../Topic/CHeapPtrBase::Free.md)|指すにオブジェクトを `CHeapPtrBase`削除するには、このメソッドを呼び出します。|  
|[CHeapPtrBase::ReallocateBytes](../Topic/CHeapPtrBase::ReallocateBytes.md)|メモリの再割り当てするには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrBase::operator T\*](../Topic/CHeapPtrBase::operator%20T*.md)|キャスト演算子。|  
|[CHeapPtrBase::operator &](../Topic/CHeapPtrBase::operator%20&.md)|& 演算子。|  
|[CHeapPtrBase::operator \-\>](../Topic/CHeapPtrBase::operator%20-%3E.md)|ポインターメンバー演算子。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrBase::m\_pData](../Topic/CHeapPtrBase::m_pData.md)|ポインターのデータ メンバー変数。|  
  
## 解説  
 このクラスは、スマート ヒープ ポインター クラスの基本クラスとなります。  派生クラスは、たとえば、[CHeapPtr](../../atl/reference/cheapptr-class.md) と [CComHeapPtr](../../atl/reference/ccomheapptr-class.md)は、独自のコンストラクターと演算子を追加します。  実装の例については、これらのクラスを参照してください。  
  
## 必要条件  
 **ヘッダー :** atlcore.h  
  
## 参照  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)