---
title: "CriticalSectionTraits::GetInvalidValue メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue メソッド"
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSectionTraits::GetInvalidValue メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

常にテンプレートが無効になるように CriticalSection のテンプレートを特殊化します。  
  
## 構文  
  
```  
inline static Type GetInvalidValue();  
```  
  
## 戻り値  
 無効なクリティカル セクションへのポインターを返します。  
  
## 解説  
 *Type* 修飾子は `typedef CRITICAL_SECTION* Type;`として定義されます。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)