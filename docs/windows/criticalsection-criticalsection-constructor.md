---
title: "CriticalSection::CriticalSection コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CriticalSection、コンストラクター"
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CriticalSection::CriticalSection コンストラクター
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ミューテックス オブジェクトに似ていますが、初期化しましたり単一プロセスのスレッドだけで使用できます。同期オブジェクトを示します。  
  
## 構文  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### パラメーター  
 `spincount`  
 クリティカル セクション オブジェクトのスピン カウント。  既定値は 0 です。  
  
## 解説  
 crticial セクションと spincounts に関する詳細については、Windows API documenation の同期セクションの **InitializeCriticalSectionAndSpinCount** 関数を参照します。  
  
## 必要条件  
 **ヘッダー:** corewrappers.h  
  
 **名前空間:** Microsoft::WRL::Wrappers  
  
## 参照  
 [CriticalSection クラス](../Topic/CriticalSection%20Class.md)