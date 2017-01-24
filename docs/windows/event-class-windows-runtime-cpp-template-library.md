---
title: "Event クラス (Windows ランタイム C++ テンプレート ライブラリ) | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::Event"
dev_langs: 
  - "C++"
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Event クラス (Windows ランタイム C++ テンプレート ライブラリ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベントを表します。  
  
## 構文  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[Event::Event コンストラクター \(Windows ランタイム C\+\+ テンプレート ライブラリ\)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Event クラスの新しいインスタンスを初期化します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[Event::operator\= 演算子](../windows/event-operator-assign-operator.md)|指定された Event 参照を現在の Event インスタンスに割り当てます。|  
  
## 継承階層  
 `HandleT`  
  
 `Event`  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [Microsoft::WRL::Wrappers 名前空間](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)