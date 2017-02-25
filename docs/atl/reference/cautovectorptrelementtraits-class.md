---
title: "CAutoVectorPtrElementTraits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoVectorPtrElementTraits<T>"
  - "ATL.CAutoVectorPtrElementTraits"
  - "ATL.CAutoVectorPtrElementTraits<T>"
  - "ATL::CAutoVectorPtrElementTraits"
  - "CAutoVectorPtrElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtrElementTraits クラス"
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAutoVectorPtrElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ベクターの new 演算子と delete 演算子を使用してスマート ポインターのコレクションを作成するときに役立つメソッド、静的関数、および typedef が用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template<  
typename T  
>  
class CAutoVectorPtrElementTraits : public CDefaultElementTraits<  
ATL::CAutoVectorPtr< T>  
>  
```  
  
#### パラメーター  
 `T`  
 ポインター型。  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|[CAutoVectorPtrElementTraits::INARGTYPE](../Topic/CAutoVectorPtrElementTraits::INARGTYPE.md)|コレクション クラス オブジェクトに要素を追加するために使用するデータ型。|  
|[CAutoVectorPtrElementTraits::OUTARGTYPE](../Topic/CAutoVectorPtrElementTraits::OUTARGTYPE.md)|コレクション クラス オブジェクトから要素を取得するために使用するデータ型。|  
  
## 解説  
 このクラスは、スマート ポインターを含むコレクション クラス オブジェクトの作成を支援するメソッド、静的関数、および typedef が用意されています。  [CAutoPtrElementTraits](../Topic/CAutoPtrElementTraits%20Class.md)とは異なり、このクラスは、ベクターの new 演算子と delete 演算子を使用します。  
  
## 継承階層  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoVectorPtrElementTraits`  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [CAutoVectorPtr クラス](../../atl/reference/cautovectorptr-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)