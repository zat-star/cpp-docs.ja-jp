---
title: "HandleT::operator= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 演算子"
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HandleT の現在のオブジェクトへの HandleT オブジェクトの値を移動します。  
  
## 構文  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### パラメーター  
 `h`  
 ハンドルへの rvalue 参照。  
  
## 戻り値  
 HandleT の現在のオブジェクトへの参照。  
  
## 解説  
 この操作は `h`パラメーターで指定された HandleT オブジェクトが無効になります。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HandleT クラス](../Topic/HandleT%20Class.md)