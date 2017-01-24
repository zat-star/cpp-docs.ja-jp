---
title: "norm クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::norm"
dev_langs: 
  - "C++"
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# norm クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

標準の数を表します。  各要素は、浮動小数点数値の範囲です\- \[\]、1.0f 1.0f。  
  
## 構文  
  
```  
class norm;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[norm::norm コンストラクター](../Topic/norm::norm%20Constructor.md)|オーバーロードされます。  既定のコンストラクターです。  0.0f に初期化してください。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|norm::operator\-の演算子||  
|norm::operator。演算子||  
|norm::operator の float の演算子|変換演算子。  浮動小数点値標準に数値を変換します。|  
|norm::operator\*\= の演算子||  
|norm::operator\/\= の演算子||  
|norm::operator\+\+ の演算子||  
|norm::operator\+\= の演算子||  
|norm::operator\= の演算子||  
|norm::operator\-\= の演算子||  
  
## 継承階層  
 `norm`  
  
## 必要条件  
 **ヘッダー:** amp\_short\_vectors.h  
  
 **名前空間:** Concurrency::graphics  
  
## 参照  
 [Concurrency::graphics 名前空間](../../../parallel/amp/reference/concurrency-graphics-namespace.md)