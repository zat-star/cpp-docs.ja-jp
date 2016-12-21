---
title: "HString::Operator&lt; 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator<"
dev_langs: 
  - "C++"
ms.assetid: 48a051cb-4609-42be-b48c-d35fc99d1eab
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator&lt; 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最初のパラメーターが 2 番目のパラメーターより小さいかどうかを示します。  
  
## 構文  
  
```cpp  
  
inline bool operator<(  
    const HString& lhs,   
    const HString& rhs) throw()  
  
```  
  
#### パラメーター  
 `lhs`  
 比較する最初のパラメーター。  `lhs` は HString への参照である場合があります。  
  
 `rhs`  
 比較する 2 番目のパラメーター。  `rhs` は HString への参照である場合があります。  
  
## 戻り値  
 `lhs` パラメーターである場合 `rhs` パラメーター未満`true` ; それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HString クラス](../windows/hstring-class.md)