---
title: "CSimpleMapEqualHelperFalse クラス | Microsoft Docs"
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
  - "ATL::CSimpleMapEqualHelperFalse"
  - "CSimpleMapEqualHelperFalse"
  - "ATL.CSimpleMapEqualHelperFalse"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelperFalse クラス"
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelperFalse クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。  
  
## 構文  
  
```  
  
template < class TKey, class TVal > class CSimpleMapEqualHelperFalse  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](../Topic/CSimpleMapEqualHelperFalse::IsEqualKey.md)|\(静的\) 等価性 2 種類のキーをテストします。|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](../Topic/CSimpleMapEqualHelperFalse::IsEqualValue.md)|静的 \(false\) を返します。|  
  
## 解説  
 この特徴 \(traits\) クラスは、`CSimpleMap` クラスの補足クラスです。  これは `CSimpleMap` のオブジェクト \(特に、値 2 または 2 個の要素キー要素に含まれる 2 個の要素を比較するメソッドを提供します。  
  
 また値の比較は参照されている場合、false を、False の引数で呼び出す `ATLASSERT` 常に返す。  等価テストが完全に定義されていない場合、このクラスは、ほとんどのメソッドで正しく動作するに [CSimpleMap::FindVal](../Topic/CSimpleMap::FindVal.md)のような比較に依存するメソッドの明示する形で失敗するキーと値のペアを含むマップができますが。  
  
## 必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
## 参照  
 [CSimpleMapEqualHelper クラス](../../atl/reference/csimplemapequalhelper-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)