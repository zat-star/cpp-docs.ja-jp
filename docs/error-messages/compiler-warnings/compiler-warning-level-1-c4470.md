---
title: "コンパイラの警告 (レベル 1) C4470 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4470"
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 1) C4470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点の制御 pragmas は \/clr で無視されました  
  
 この警告は、以下の浮動小数点の制御プラグマが使用されている場合に発生する可能性があります。  
  
-   [fenv\_access](../../preprocessor/fenv-access.md)  
  
-   [float\_control](../Topic/float_control.md)  
  
-   [fp\_contract](../../preprocessor/fp-contract.md)  
  
 これらは、[\/clr](../../build/reference/clr-common-language-runtime-compilation.md) が指定されている場合は無効です。  
  
 次の例では警告 C4470 が生成されます。  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```