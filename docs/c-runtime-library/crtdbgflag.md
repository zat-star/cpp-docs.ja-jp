---
title: _crtDbgFlag | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _crtDbgFlag
- crtDbgFlag
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, tracking flag
- crtDbgFlag constant
- _crtDbgFlag constant
- debug heap, tracking memory on
- debug heap, control flags
- enable memory allocation tracking flag
- memory, tracking on the debug heap
ms.assetid: 9e7adb47-8ab9-4e19-81d5-e2f237979973
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 4f4c3a874d59095d620a04d5ebb6ac88e2bdfa66
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
**_crtDbgFlag** フラグは、ヒープのデバッグ バージョンでのメモリ割り当てがどのように追跡、検証、報告、およびダンプされるかを制御する 5 つのビット フィールドで構成されます。 このフラグのビット フィールドは、[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して設定されます。 このフラグとそのビット フィールドは、Crtdbg.h で宣言されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。  
  
 このフラグを他のデバッグ機能と組み合わせて使用する方法の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コントロール フラグ](../c-runtime-library/control-flags.md)
