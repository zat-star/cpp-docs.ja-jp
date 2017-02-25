---
title: "unorm クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::unorm"
  - "amp/Concurrency::graphics::unorm"
dev_langs: 
  - "C++"
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# unorm クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

unorm の数を表します。  各要素は、浮動小数点数値の範囲に\[\]、0.0f 1.0f です。  
  
## 構文  
  
```  
class unorm;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[unorm::unorm コンストラクター](../Topic/unorm::unorm%20Constructor.md)|オーバーロードされます。  既定のコンストラクターです。  0.0f に初期化してください。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|unorm::operator。演算子||  
|unorm::operator の float の演算子|変換演算子。  浮動小数点値に unorm に数値を変換します。|  
|unorm::operator\*\= の演算子||  
|unorm::operator\/\= の演算子||  
|unorm::operator\+\+ の演算子||  
|unorm::operator\+\= の演算子||  
|unorm::operator\= の演算子||  
|unorm::operator\-\= の演算子||  
  
## 継承階層  
 `unorm`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)