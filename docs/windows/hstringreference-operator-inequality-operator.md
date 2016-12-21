---
title: "HStringReference::Operator!= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!="
dev_langs: 
  - "C++"
ms.assetid: 01ab6691-1fc7-4feb-85f0-fe795593a160
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator!= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのパラメーターが異なるかどうかを示します。  
  
## 構文  
  
```cpp  
  
inline bool operator==(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HSTRING& lhs,   
               const HStringReference& rhs) throw()  
  
inline bool operator!=(  
               const HStringReference& lhs,   
               const HSTRING& rhs) throw()  
  
```  
  
#### パラメーター  
 `lhs`  
 比較する最初のパラメーター。  `lhs` は HStringReference オブジェクトまたは HSTRING ハンドルのいずれかです。  
  
 `rhs`  
 比較する 2 番目のパラメーター。`rhs` は HStringReference オブジェクトまたは HSTRING ハンドルのいずれかです。  
  
## 戻り値  
 `lhs` パラメーターと `rhs` パラメーターが等しくない場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HStringReference クラス](../windows/hstringreference-class.md)