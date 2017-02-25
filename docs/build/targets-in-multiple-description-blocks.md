---
title: "複数の記述ブロックのターゲット | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブロック, 複数の記述"
  - "記述ブロック"
  - "複数の記述ブロック"
ms.assetid: 8618dcd9-c11d-4562-91a7-0c904ed438a8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 複数の記述ブロックのターゲット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

複数の記述ブロックにあるターゲットを異なるコマンドを使って更新するには、ターゲットと依存ファイルの間で 2 つの連続するコロン \(::\) を指定します。  
  
```  
target.lib :: one.asm two.asm three.asm  
    ml one.asm two.asm three.asm  
    lib target one.obj two.obj three.obj  
target.lib :: four.c five.c  
    cl /c four.c five.c  
    lib target four.obj five.obj  
```  
  
## 参照  
 [ターゲット](../build/targets.md)