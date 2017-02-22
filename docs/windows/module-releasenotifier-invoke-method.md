---
title: "Module::ReleaseNotifier::Invoke メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier::Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Invoke メソッド"
ms.assetid: f62686fe-74bf-482b-a46b-6a3c09b80e7e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::ReleaseNotifier::Invoke メソッド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

実装された場合、呼び出しイベント ハンドラー モジュールの最後のオブジェクトが解放されたときに。  
  
## 構文  
  
```  
virtual void Invoke() = 0;  
```  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Module::ReleaseNotifier クラス](../Topic/Module::ReleaseNotifier%20Class.md)