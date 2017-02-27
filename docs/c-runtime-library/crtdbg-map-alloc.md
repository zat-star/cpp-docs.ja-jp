---
title: _CRTDBG_MAP_ALLOC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs:
- C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 709ba57e3cca392d2440c7ad528125dc31070cac

---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
**_CRTDBG_MAP_ALLOC** フラグがアプリケーションのデバッグ バージョンに定義されていると、ヒープ関数の基本バージョンがそのデバッグ バージョンに直接マッピングされます。 このフラグは、マッピングを行うために、Crtdbg.h で使用されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。  
  
 ヒープ関数のデバッグ バージョンと基本バージョンの違いについては、「[Using the Debug Version Versus the Base Version](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」 (デバッグ バージョンと基本バージョンの違い) を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コントロール フラグ](../c-runtime-library/control-flags.md)


<!--HONumber=Feb17_HO4-->


