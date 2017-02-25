---
title: "CHeapPtrList クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CHeapPtrList"
  - "CHeapPtrList"
  - "ATL.CHeapPtrList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrList クラス"
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHeapPtrList クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ヒープ ポインターのリストを構築するときに役立つメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename E,  
class Allocator = ATL::CCRTAllocator  
>  
class CHeapPtrList : public CAtlList<  
ATL::CHeapPtr< E, Allocator>,  
CHeapPtrElementTraits< E, Allocator>  
>  
```  
  
#### パラメーター  
 `E`  
 コレクション クラスに格納されるオブジェクトの型。  
  
 `Allocator`  
 使用するメモリ割り当てのクラス。  既定値は [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrList::CHeapPtrList](../Topic/CHeapPtrList::CHeapPtrList.md)|コンストラクターです。|  
  
## 解説  
 このクラスは、コンストラクターを提供し、[CAtlList](../Topic/CAtlList%20Class.md) と [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) からヒープ ポインターを格納するコレクション クラス オブジェクトの作成を支援するメソッドを取得します。  
  
## 継承階層  
 [CAtlList](../Topic/CAtlList%20Class.md)  
  
 `CHeapPtrList`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CAtlList クラス](../Topic/CAtlList%20Class.md)   
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits クラス](../../atl/reference/cheapptrelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)