---
title: _CRTDBG_MAP_ALLOC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
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
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a2b61b315baa337675147ded1232a943e82b24ec
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
**_CRTDBG_MAP_ALLOC** フラグがアプリケーションのデバッグ バージョンに定義されていると、ヒープ関数の基本バージョンがそのデバッグ バージョンに直接マッピングされます。 このフラグは、マッピングを行うために、Crtdbg.h で使用されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。  
  
 ヒープ関数のデバッグ バージョンと基本バージョンの違いについては、「[Using the Debug Version Versus the Base Version](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」 (デバッグ バージョンと基本バージョンの違い) を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コントロール フラグ](../c-runtime-library/control-flags.md)
