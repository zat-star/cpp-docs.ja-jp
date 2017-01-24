---
title: "HStringReference::Operator= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator="
dev_langs: 
  - "C++"
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::Operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

別の HStringReference オブジェクトの値を現在の HStringReference オブジェクトに移動します。  
  
## 構文  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
#### パラメーター  
 `other`  
 HStringReference の既存のオブジェクト。  
  
## 解説  
 `other` で既存のオブジェクトの値は HStringReference の現在のオブジェクトにコピーされ、`other` オブジェクトは破棄されます。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HStringReference クラス](../windows/hstringreference-class.md)