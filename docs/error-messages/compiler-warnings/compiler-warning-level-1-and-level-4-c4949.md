---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4949 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4949"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4949"
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1 およびレベル 4) C4949
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マネージおよびアンマネージのプラグマは、'\/clr\[:option\]' でコンパイルされるときにのみ有効です  
  
 ソース コードが [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) なしでコンパイルされた場合、[マネージ](../../preprocessor/managed-unmanaged.md)およびアンマネージのプラグマは無視されます。  この警告は、情報を提供するためだけのものです。  
  
 次の例では警告 C4949 が生成されます。  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 **\/clr** なしで **\#pragma unmanaged** が使用されている場合、C4949 はレベル 4 の警告になります。  
  
 次の例では警告 C4949 が生成されます。  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```