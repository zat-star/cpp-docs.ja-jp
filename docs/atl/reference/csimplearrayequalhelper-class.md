---
title: "CSimpleArrayEqualHelper クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleArrayEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleArrayEqualHelper クラス"
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleArrayEqualHelper クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[CSimpleArray](../../atl/reference/csimplearray-class.md) クラスのヘルパーです。  
  
## 構文  
  
```  
  
      template <  
   class T   
>  
class CSimpleArrayEqualHelper  
```  
  
#### パラメーター  
 `T`  
 派生クラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleArrayEqualHelper::IsEqual](../Topic/CSimpleArrayEqualHelper::IsEqual.md)|\(静的等値\) テストの 2 個の `CSimpleArray` のオブジェクト要素。|  
  
## 解説  
 この特徴 \(traits\) クラスは、`CSimpleArray` クラスの補足クラスです。  これは `CSimpleArray` のオブジェクトに格納されている 2 個の要素を比較するメソッドを提供します。  既定では、要素は **operator\=\(\)**を使用して比較されますが、配列、独自の等値演算子を持たないに複合データ型が含まれており、このクラスをオーバーライドする必要があります。  
  
## 必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
## 参照  
 [CSimpleArray クラス](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse クラス](../Topic/CSimpleArrayEqualHelperFalse%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)