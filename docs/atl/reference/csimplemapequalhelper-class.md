---
title: "CSimpleMapEqualHelper クラス | Microsoft Docs"
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
  - "CSimpleMapEqualHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleMapEqualHelper クラス"
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleMapEqualHelper クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、[CSimpleMap](../../atl/reference/csimplemap-class.md) クラスのヘルパーです。  
  
## 構文  
  
```  
  
      template <  
   class TKey,  
   class TVal   
>  
class CSimpleMapEqualHelper  
```  
  
#### パラメーター  
 `TKey`  
 キー要素。  
  
 `TVal`  
 値要素。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleMapEqualHelper::IsEqualKey](../Topic/CSimpleMapEqualHelper::IsEqualKey.md)|\(静的\) 等価性 2 種類のキーをテストします。|  
|[CSimpleMapEqualHelper::IsEqualValue](../Topic/CSimpleMapEqualHelper::IsEqualValue.md)|\(静的\) 2 つの値の等価性をテストします。|  
  
## 解説  
 この特徴 \(traits\) クラスは、`CSimpleMap` クラスの補足クラスです。  2 つの `CSimpleMap` オブジェクト要素、特にキー コンポーネントと値コンポーネントが等しいかどうかを比較するメソッドを提供します。  既定では、キーと値の比較には `operator==()` が使用されますが、独自の等値演算子を持たない複合データ型がマップに含まれている場合は、このクラスをオーバーライドして必要な追加機能を提供できます。  
  
## 必要条件  
 **ヘッダー:** atlsimpcoll.h  
  
## 参照  
 [CSimpleMapEqualHelperFalse クラス](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)