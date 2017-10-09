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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 559dba68c8c171fbc84be17e64c2628b4bbf5011
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="crtdbgflag"></a>_crtDbgFlag
**_crtDbgFlag** フラグは、ヒープのデバッグ バージョンでのメモリ割り当てがどのように追跡、検証、報告、およびダンプされるかを制御する 5 つのビット フィールドで構成されます。 このフラグのビット フィールドは、[_CrtSetDbgFlag](../c-runtime-library/reference/crtsetdbgflag.md) 関数を使用して設定されます。 このフラグとそのビット フィールドは、Crtdbg.h で宣言されます。 このフラグは、[_DEBUG](../c-runtime-library/debug.md) フラグがアプリケーションで定義されている場合にのみ使用できます。  
  
 このフラグを他のデバッグ機能と組み合わせて使用する方法の詳細については、「[ヒープの状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コントロール フラグ](../c-runtime-library/control-flags.md)
