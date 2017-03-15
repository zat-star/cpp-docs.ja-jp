---
title: "Event::Event コンストラクター (Windows ランタイム C++ テンプレート ライブラリ) | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event::Event"
dev_langs: 
  - "C++"
ms.assetid: 21495297-9612-4095-9256-16e168cc0021
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event::Event コンストラクター (Windows ランタイム C++ テンプレート ライブラリ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Event クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```  
explicit Event(  
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);  
WRL_NOTHROW Event(  
   _Inout_ Event&& h  
);  
```  
  
#### パラメーター  
 `h`  
 イベントに対するハンドル。  既定では、`h` は `nullptr` に初期化されます。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Event クラス \(Windows ランタイム C\+\+ テンプレート ライブラリ\)](../windows/event-class-windows-runtime-cpp-template-library.md)