---
title: "CriticalSectionTraits 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSectionTraits 構造体"
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSectionTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CriticalSection オブジェクトが無効なクリティカル セクションまたは関数をクリティカル セクションを解放するためにサポートするよう専用です。  
  
## 構文  
  
```  
struct CriticalSectionTraits;  
```  
  
## メンバー  
  
### パブリック typedef  
  
|名前|説明|  
|--------|--------|  
|`Type`|`typedef` クリティカル セクションにポインターを定義できます。  `Type` は `typedef CRITICAL_SECTION* Type;`として定義されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CriticalSectionTraits::GetInvalidValue メソッド](../windows/criticalsectiontraits-getinvalidvalue-method.md)|常にテンプレートが無効になるように CriticalSection のテンプレートを特殊化します。|  
|[CriticalSectionTraits::Unlock メソッド](../Topic/CriticalSectionTraits::Unlock%20Method.md)|指定クリティカル セクション オブジェクトの所有権を解放をサポートするように CriticalSection のテンプレートを特殊化します。|  
  
## 継承階層  
 `CriticalSectionTraits`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)