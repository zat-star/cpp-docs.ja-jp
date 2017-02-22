---
title: "CHeapPtr クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CHeapPtr"
  - "CHeapPtr"
  - "ATL.CHeapPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtr クラス"
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtr クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ヒープ ポインターを管理するためのスマート ポインター クラスです。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename T,  
class Allocator= CCRTAllocator  
> class CHeapPtr :  
public CHeapPtrBase< T, Allocator>  
```  
  
#### パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
 `Allocator`  
 使用するメモリ割り当てのクラス。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtr::CHeapPtr](../Topic/CHeapPtr::CHeapPtr.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtr::Allocate](../Topic/CHeapPtr::Allocate.md)|ストアにオブジェクト ヒープ メモリを割り当てるには、このメソッドを呼び出します。|  
|[CHeapPtr::Reallocate](../Topic/CHeapPtr::Reallocate.md)|ヒープ メモリを再割り当てするには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtr::operator \=](../Topic/CHeapPtr::operator%20=.md)|代入演算子です。|  
  
## 解説  
 `CHeapPtr` は [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) とメモリの割り当ておよび解放を行う既定では、CRT ルーチンから使用 \([CCRTAllocator](../../atl/reference/ccrtallocator-class.md) 内に\) 派生します。  クラス [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) がヒープ ポインターのリストを構築に使用されることがあります。  [CComHeapPtr](../../atl/reference/ccomheapptr-class.md)を参照、COM メモリ割り当てルーチンを使用する。  
  
## 継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## 必要条件  
 **ヘッダー :** atlcore.h  
  
## 参照  
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator クラス](../../atl/reference/ccrtallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)