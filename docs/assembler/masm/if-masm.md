---
title: "IF (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IF directive"
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# IF (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*expression1 が*  真 \(以外\) または *elseifstatements* *expression1* の場合は false *ifstatements* のアセンブリを許可します \(0\) と *expression2 は*  TRUE です。  
  
## 構文  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## 解説  
 次のディレクティブは [ELSEIF](../../assembler/masm/elseif-masm.md) の代わりになる可能性があります : **ELSEIFBELSEIFDEFELSEIFDIFELSEIFDIFIELSEIFEELSEIFIDNELSEIFIDNIELSEIFNB** と **ELSEIFNDEF**。  必要に応じて前の式が FALSE の場合*elsestatements を*  構成します。  式がアセンブリ時に評価されることに注意してください。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)