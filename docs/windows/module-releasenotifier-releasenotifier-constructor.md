---
title: "Module::ReleaseNotifier::ReleaseNotifier コンストラクター | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier、コンストラクター"
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module::ReleaseNotifier::ReleaseNotifier コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Module::ReleaseNotifier クラスの新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### パラメーター  
 `release`  
 acquire メソッドが呼び出されたときにこのインスタンスを削除する`true` ; このインスタンスを削除しない `false`。  
  
## 例外  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Module::ReleaseNotifier クラス](../Topic/Module::ReleaseNotifier%20Class.md)