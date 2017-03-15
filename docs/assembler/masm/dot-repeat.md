---
title: ".REPEAT | Microsoft Docs"
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
  - ".REPEAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".REPEAT directive"
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .REPEAT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`condition` が true になるまでコードを *ステートメント*  ブロックを繰り返し実行生成されます。  [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md) は [.UNTIL](../../assembler/masm/dot-until.md) の CX が true になるC の場合は代わりになることがあります。  `condition` は **.UNTILCXZ** とオプションです。  
  
## 構文  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)