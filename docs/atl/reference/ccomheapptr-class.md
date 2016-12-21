---
title: "CComHeapPtr クラス | Microsoft Docs"
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
  - "ATL::CComHeapPtr"
  - "ATL.CComHeapPtr<T>"
  - "ATL::CComHeapPtr<T>"
  - "CComHeapPtr"
  - "ATL.CComHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComHeapPtr クラス"
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComHeapPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ ポインターを管理するためのスマート ポインター クラスです。  
  
## 構文  
  
```  
  
      template<  
   typename T  
> class CComHeapPtr :  
   public CHeapPtr< T, CComAllocator >  
```  
  
#### パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComHeapPtr::CComHeapPtr](../Topic/CComHeapPtr::CComHeapPtr.md)|コンストラクターです。|  
  
## 解説  
 `CComHeapPtr` は、`CHeapPtr`使用 [CComAllocator](../../atl/reference/ccomallocator-class.md) から COM ルーチンを使用してメモリを割り当てる取得します。  使用できるメソッドについては [CHeapPtr](../../atl/reference/cheapptr-class.md) と [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) を参照してください。  
  
## 継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## 必要条件  
 **ヘッダー:** atlbase.h  
  
## 参照  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)