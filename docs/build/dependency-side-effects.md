---
title: 依存関係の副作用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f595099d2a71c948c769adf7f7eafcbc373f3146
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dependency-side-effects"></a>依存関係の副作用
ターゲットが、異なる場所に 2 つの依存関係の線にコロン (:) で指定されている場合、および行の 1 つだけの後にコマンドが表示されない場合は、隣接するまたは結合まるで (nmake の) の依存関係は解釈します。 コマンドがありませんが、代わりにでは、依存関係の説明を 1 つのブロックに属するし、コマンドを実行するその他の依存関係と共に指定する依存関係の推論規則は呼び出されません。 たとえば、これは、ルールの設定。  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
```  
  
 この評価されます。  
  
```Output  
bounce.exe : jump.obj up.obj  
   echo Building bounce.exe...  
```  
  
 場合、二重のコロンこの効果は発生しません (`::`) を使用します。 たとえば、これは、ルールの設定。  
  
```Output  
bounce.exe :: jump.obj  
   echo Building bounce.exe...  
  
bounce.exe :: up.obj  
```  
  
 この評価されます。  
  
```Output  
bounce.exe : jump.obj  
   echo Building bounce.exe...  
  
bounce.exe : up.obj  
# invokes an inference rule  
```  
  
## <a name="see-also"></a>参照  
 [ターゲット](../build/targets.md)