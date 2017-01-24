---
title: "MutexTraits 構造体 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MutexTraits 構造体"
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MutexTraits 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ミューテックス](../Topic/Mutex%20Class1.md) クラスのような共通の特性を定義します。  
  
## 構文  
  
```  
struct MutexTraits : HANDLENullTraits;  
  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[MutexTraits::Unlock メソッド](../windows/mutextraits-unlock-method.md)|共有リソースの排他制御を解放します。|  
  
## 継承階層  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)