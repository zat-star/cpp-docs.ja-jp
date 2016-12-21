---
title: "CDefaultElementTraits クラス | Microsoft Docs"
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
  - "ATL::CDefaultElementTraits<T>"
  - "ATL.CDefaultElementTraits"
  - "ATL::CDefaultElementTraits"
  - "ATL.CDefaultElementTraits<T>"
  - "CDefaultElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultElementTraits クラス"
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDefaultElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、コレクション クラス用の既定のメソッドと関数が用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename T  
>  
class CDefaultElementTraits : public CElementTraitsBase< T >,  
   public CDefaultHashTraits< T >,  
   public CDefaultCompareTraits< T >  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## 解説  
 このクラスは、移動、コピー、比較、およびコレクション クラス オブジェクトに格納されているハッシュ要素に既定の静的関数とメソッドを提供します。  このクラスは [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)と [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)から関数とメソッドを取得し、[CElementTraits](../../atl/reference/celementtraits-class.md)、[CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)と [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)によって使用されます。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)