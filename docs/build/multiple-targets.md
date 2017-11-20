---
title: "複数のターゲット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, targets
- multiple targets in NMAKE
- targets, multiple in NMAKE
- NMAKE program, targets
ms.assetid: b609a179-0b9f-4b08-9930-998047588ae0
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c610b5a65dfc676d12d414754248ba74ebc4b81c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="multiple-targets"></a>複数のターゲット
(Nmake の) は、個別の記述ブロックでそれぞれ指定した場合と、単一の依存関係の複数のターゲットを評価します。  
  
 例えばこの。。。  
  
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
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)