---
title: "MutexTraits::Unlock メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock メソッド"
ms.assetid: 7c4e5664-6d95-498a-95bb-d30b5e866c2c
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# MutexTraits::Unlock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共有リソースの排他制御を解放します。  
  
## 構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### パラメーター  
 `h`  
 ミューテックス オブジェクトへのハンドル。  
  
## 戻り値  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [MutexTraits 構造体](../windows/mutextraits-structure.md)