---
title: "CHeapPtrElementTraits クラス | Microsoft Docs"
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
  - "ATL.CHeapPtrElementTraits"
  - "CHeapPtrElementTraits"
  - "ATL::CHeapPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeapPtrElementTraits クラス"
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHeapPtrElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ヒープ ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename T,  
class Allocator= ATL::CCRTAllocator  
>  
class CHeapPtrElementTraits : public CDefaultElementTraits<  
ATL::CHeapPtr< T, Allocator>  
>  
```  
  
#### パラメーター  
 `T`  
 コレクション クラスに格納されるオブジェクトの型。  
  
 `Allocator`  
 使用するメモリ割り当てのクラス。  既定値は [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)です。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CHeapPtrElementTraits::INARGTYPE](../Topic/CHeapPtrElementTraits::INARGTYPE.md)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|  
|[CHeapPtrElementTraits::OUTARGTYPE](../Topic/CHeapPtrElementTraits::OUTARGTYPE.md)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|  
  
## 解説  
 このクラスには、ヒープ ポインターを含むコレクション クラス オブジェクトの作成を支援するメソッド、静的関数、および typedef が用意されています。  クラス `CHeapPtrList` は `CHeapPtrElementTraits`から取得します。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 継承階層  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CHeapPtrElementTraits`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr クラス](../../atl/reference/ccomheapptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)