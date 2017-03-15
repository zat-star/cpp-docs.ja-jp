---
title: "RoInitializeWrapper::~RoInitializeWrapper デストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: afef4c1f-ffde-4cd2-8654-8de4182eb5f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# RoInitializeWrapper::~RoInitializeWrapper デストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]を初期化前の状態に戻します。  
  
## 構文  
  
```cpp  
~RoInitializeWrapper()  
```  
  
## 解説  
 RoInitializeWrapper クラスは Windows::Foundation::Uninitialize\(\)を呼び出します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HandleT クラス](../Topic/HandleT%20Class.md)