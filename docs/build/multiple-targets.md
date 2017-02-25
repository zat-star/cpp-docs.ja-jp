---
title: "複数のターゲット | Microsoft Docs"
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
  - "メイクファイルのターゲット"
  - "複数のターゲット (NMAKE の)"
  - "ターゲットを複数 (nmake の)"
  - "NMAKE プログラムでは、ターゲット"
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 複数のターゲット
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE は、それぞれが独立した記述ブロックで指定されたかのように単一の依存関係の複数のターゲットを評価します。  
  
 次に例をしています.  
  
```Output  
bounce.exe leap.exe : jump.obj  
   echo Building...  
```  
  
 .. 評価結果。  
  
```Output  
bounce.exe : jump.obj  
   echo Building...  
leap.exe : jump.obj  
   echo Building...  
```  
  
## <a name="see-also"></a>「  
 [ターゲット](../build/targets.md)