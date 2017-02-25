---
title: "CDefaultCompareTraits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CDefaultCompareTraits<T>"
  - "ATL::CDefaultCompareTraits"
  - "ATL.CDefaultCompareTraits"
  - "ATL::CDefaultCompareTraits<T>"
  - "CDefaultCompareTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDefaultCompareTraits クラス"
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDefaultCompareTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、既定の要素比較関数が用意されています。  
  
## 構文  
  
```  
  
      template<  
   typename T  
>  
class CDefaultCompareTraits  
```  
  
#### パラメーター  
 `T`  
 コレクションに格納されるデータの型。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDefaultCompareTraits::CompareElements](../Topic/CDefaultCompareTraits::CompareElements.md)|\(静的\) 等値の 2 種類の要素を比較するには、この関数を呼び出します。|  
|[CDefaultCompareTraits::CompareElementsOrdered](../Topic/CDefaultCompareTraits::CompareElementsOrdered.md)|\(静的関数\) を超えると、要素を判断するには、この関数を呼び出します。|  
  
## 解説  
 このクラスには、コレクション クラス オブジェクトに格納されている要素を比較するには、次の 2 とおりの静的関数が含まれています。  このクラスは [CDefaultElementTraits のクラス](../../atl/reference/cdefaultelementtraits-class.md)によって使用されます。  
  
 詳細については、[ATL のコレクション クラス](../../atl/atl-collection-classes.md)を参照してください。  
  
## 必要条件  
 **Header:** atlcoll.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)