---
title: "Event::operator= 演算子 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 演算子"
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event::operator= 演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定された Event 参照を現在の Event インスタンスに割り当てます。  
  
## 構文  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### パラメーター  
 `h`  
 イベント インスタンスへの rvalue 参照。  
  
## 戻り値  
 現在のイベント インスタンスへのポインター。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Event クラス \(Windows ランタイム C\+\+ テンプレート ライブラリ\)](../windows/event-class-windows-runtime-cpp-template-library.md)