---
title: "no_dual_interfaces | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "no_dual_interfaces"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_dual_interfaces 属性"
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_dual_interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+ 固有の仕様**  
  
 コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。  
  
## 構文  
  
```  
no_dual_interfaces  
```  
  
## 解説  
 通常、ラッパーは、そのインターフェイスの仮想関数テーブルからメソッドを呼び出します。  `no_dual_interfaces` では、ラッパーはメソッドを呼び出すために、代わりに **IDispatch::Invoke** を呼び出します。  
  
 **END C\+\+ 固有の仕様**  
  
## 参照  
 [\#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import ディレクティブ](../Topic/%23import%20Directive%20\(C++\).md)