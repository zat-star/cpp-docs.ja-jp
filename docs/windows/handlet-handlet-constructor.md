---
title: "HandleT::HandleT コンストラクター | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT、コンストラクター"
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::HandleT コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HandleT クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### パラメーター  
 `h`  
 ハンドル。  
  
## 解説  
 最初のコンストラクターはオブジェクトに有効なハンドルではない HandleT オブジェクトを初期化します。  2 番目のコンストラクターは、パラメーター `h`から HandleT の新しいオブジェクトを作成します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [HandleT クラス](../Topic/HandleT%20Class.md)