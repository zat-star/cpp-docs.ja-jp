---
title: "SemaphoreTraits::Unlock メソッド | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unlock メソッド"
ms.assetid: 4e0ea808-b70d-43f7-81ef-998c3b34e3a0
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SemaphoreTraits::Unlock メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

共有リソースの解放を制御します。  
  
## 構文  
  
```  
inline static void Unlock(  
   _In_ Type h  
);  
```  
  
#### パラメーター  
 `h`  
 セマフォ オブジェクトへのハンドル。  
  
## 解説  
 ロック解除操作が失敗した場合、Unlock\(\) は失敗の理由を示すエラーが発生します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 参照  
 [SemaphoreTraits 構造体](../Topic/SemaphoreTraits%20Structure.md)