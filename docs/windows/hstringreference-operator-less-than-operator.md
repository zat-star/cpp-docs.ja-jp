---
title: "HStringReference::Operator&lt; 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<"
dev_langs: 
  - "C++"
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator&lt; 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。  
  
## 構文  
  
```cpp  
  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
  
```  
  
#### パラメーター  
 `lhs`  
 比較する最初のパラメーター。  `lhs` は HStringReference への参照である場合があります。  
  
 `rhs`  
 比較する 2 番目のパラメーター。`rhs` は HStringReference への参照である場合があります。  
  
## 戻り値  
 `lhs` パラメーターである場合 `rhs` パラメーター未満`true` ; それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HStringReference クラス](../windows/hstringreference-class.md)