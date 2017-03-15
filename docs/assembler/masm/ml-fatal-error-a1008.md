---
title: "ML Fatal Error A1008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1008"
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**" マクロの入れ子**  
  
 マクロはファイルまたは終了のディレクティブの [ENDM](../../assembler/masm/endm.md) の末尾にマクロ ブロックの外側にある前に終了されていません。  
  
 このエラーの原因の一つと [.REPEAT](../../assembler/masm/dot-repeat.md) 1 または [.WHILE](../../assembler/masm/dot-while.md) の前にドットのオプションです。  
  
## 参照  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)