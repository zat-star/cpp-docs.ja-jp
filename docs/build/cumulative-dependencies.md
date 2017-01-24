---
title: "依存関係の追加 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "累積的な依存関係"
  - "依存関係の追加 (NMAKE の)"
  - "依存関係"
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 依存関係の追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ターゲットが繰り返し発生する場合は、依存関係を記述ブロックで累積されます。  
  
 たとえば、このルールをセット、  
  
```Output  
bounce.exe : jump.obj  
bounce.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 次のように評価されます。  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 単一の記述ブロックで複数の依存関係の行で複数のターゲットは、独立した記述ブロックで指定された各が依存関係の最後の行に含まれていないターゲットがコマンドのブロックを使用しないかのように評価されます。 NMAKE がこのような対象に対して推論規則を使用しようとするとします。  
  
 たとえば、このルールをセット、  
  
```Output  
leap.exe bounce.exe : jump.obj  
bounce.exe climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
 次のように評価されます。  
  
```Output  
  
leap.exe : jump.obj  
# invokes an inference rule  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
climb.exe : up.obj  
   echo Building bounce.exe...  
```  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)