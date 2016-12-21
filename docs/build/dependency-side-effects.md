---
title: "依存関係の副作用 | Microsoft Docs"
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
  - "依存関係の副作用"
  - "NMAKE プログラムでは、参照先"
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 依存関係の副作用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ターゲットは、別の場所に 2 つの依存関係の線にコロン (:) で指定し、コマンドは、後の行の 1 つだけ表示されます。 場合は、(nmake の) は、隣接するまたは結合かのように、依存関係を解釈します。 コマンドがありませんが、依存関係が 1 つの記述ブロックに属しているし、他の依存関係で指定されたコマンドを実行するものとする依存関係の推論規則は呼び出されません。 たとえば、これは、ルールの設定。  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 次のように評価されます。  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 2 つのコロンの場合、この効果は発生しません (`::`) を使用します。 たとえば、これは、ルールの設定。  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 次のように評価されます。  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)