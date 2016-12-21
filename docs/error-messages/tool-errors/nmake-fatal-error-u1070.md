---
title: "NMAKE の致命的なエラー U1070 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1070"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1070"
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE の致命的なエラー U1070
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マクロ定義に 'macroname' に循環定義があります。  
  
 指定されたマクロ定義には、定義にこのマクロが入ったマクロが含まれています。  循環マクロ定義は無効です。  
  
## 使用例  
 次のようなマクロ定義があるとします。  
  
```  
ONE=$(TWO)  
TWO=$(ONE)  
```  
  
 この定義では、次のようなエラーが発生します。  
  
```  
cycle in macro definition 'TWO'  
```