---
title: "CDefaultHashTraits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDefaultHashTraits"
  - "ATL.CDefaultHashTraits<T>"
  - "ATL::CDefaultHashTraits<T>"
  - "ATL.CDefaultHashTraits"
  - "ATL::CDefaultHashTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultHashTraits クラス"
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultHashTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ハッシュ値を計算するための静的関数が用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename T  
>  
class CDefaultHashTraits  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDefaultHashTraits::Hash](../Topic/CDefaultHashTraits::Hash.md)|\(静的\) 特定の要素のハッシュ値を計算するには、この関数を呼び出します。|  
  
## 解説  
 このクラスは、指定した要素のハッシュ値を返す一つの静的関数が含まれています。  このクラスは [CDefaultElementTraits のクラス](../../atl/reference/cdefaultelementtraits-class.md)によって使用されます。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)