---
title: "HString::Operator!= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::operator!="
dev_langs: 
  - "C++"
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HString::Operator!= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのパラメーターが異なるかどうかを示します。  
  
## 構文  
  
```cpp  
  
   inline bool operator!=(  
                  const HString& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HStringReference& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HStringReference& rhs) throw()  
  
inline bool operator!=(  
                  const HSTRING& lhs,   
                  const HString& rhs) throw()  
  
inline bool operator!=(  
                  const HString& lhs,   
                  const HSTRING& rhs) throw()  
  
```  
  
#### パラメーター  
 `lhs`  
 比較する最初のパラメーター。  `lhs` または HSTRING ハンドル HString または HStringReference オブジェクトになることがあります。  
  
 `rhs`  
 比較する 2 番目のパラメーター。`rhs` または HSTRING ハンドル HString または HStringReference オブジェクトになることがあります。  
  
## 戻り値  
 `lhs` パラメーターと `rhs` パラメーターが等しくない場合は `true`。それ以外の場合は `false`。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HString クラス](../windows/hstring-class.md)