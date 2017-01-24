---
title: "discard_block_engine クラス | Microsoft Docs"
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
  - "tr1.discard_block_engine"
  - "std.tr1.discard_block_engine"
  - "std::tr1::discard_block_engine"
  - "random/std::tr1::discard_block_engine"
  - "discard_block_engine"
  - "tr1::discard_block_engine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "discard_block_engine クラス"
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
caps.latest.revision: 18
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# discard_block_engine クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ベースとなるエンジンから返された値を破棄することによってランダム シーケンスを生成します。  
  
## 構文  
  
```  
template<class Engine, size_t P, size_t R> class discard_block_engine;  
```  
  
#### パラメーター  
 `Engine`  
 ベースのエンジンの型。  
  
 `P`  
 **ブロック サイズ**。  各ブロックの値の数。  
  
 `R`  
 **使用されるブロック**。  使用される各ブロックの値の数。  残りは破棄されます \(`P` \- `R`\).  **前提条件**: `0 < R ≤ P`  
  
## メンバー  
  
||||  
|-|-|-|  
|`discard_block_engine::discard_block_engine`|`discard_block_engine::base`|`discard_block_engine::discard`|  
|`discard_block_engine::operator()`|`discard_block_engine::base_type`|`discard_block_engine::seed`|  
  
 エンジンのメンバーの詳細については、「[\<random\>](../standard-library/random.md)」を参照してください。  
  
## 解説  
 このテンプレート クラスは、ベースのエンジンによって返された値の一部を破棄することで値を生成するエンジン アダプターを表します。  
  
## 必要条件  
 **ヘッダー:** \<random\>  
  
 **名前空間:** std  
  
## 参照  
 [\<random\>](../standard-library/random.md)