---
title: "CElementTraits クラス | Microsoft Docs"
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
  - "ATL.CElementTraits<T>"
  - "ATL::CElementTraits"
  - "ATL.CElementTraits"
  - "ATL::CElementTraits<T>"
  - "CElementTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CElementTraits クラス"
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CElementTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、移動、コピー、比較、ハッシュの各操作のメソッドと関数を提供するために、コレクション クラスによって使用されます。  
  
## 構文  
  
```  
  
      template<  
   typename T  
>  
class CElementTraits : public CDefaultElementTraits< T >  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## 解説  
 このクラスは、移動、コピー、比較、およびコレクション クラス オブジェクトに格納されているハッシュ要素に既定の静的関数とメソッドを提供します。  `CElementTraits` は、コレクション クラス [CAtlArray](../../atl/reference/catlarray-class.md)、[CAtlList](../Topic/CAtlList%20Class.md)、[CRBMap](../../atl/reference/crbmap-class.md)、[CRBMultiMap](../../atl/reference/crbmultimap-class.md)と [CRBTree](../../atl/reference/crbtree-class.md)によってこれらの操作の既定のプロバイダーとして指定されます。  
  
 既定の実装では、単純なデータ型に足ります、より複雑なオブジェクトを格納する場合は、コレクション クラスが使用された場合に、関数とメソッドは、ユーザーが指定した実装でオーバーライドする必要があります。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [CDefaultElementTraits クラス](../../atl/reference/cdefaultelementtraits-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)