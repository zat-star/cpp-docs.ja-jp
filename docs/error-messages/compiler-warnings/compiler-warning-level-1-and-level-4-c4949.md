---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4949 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4949
dev_langs:
- C++
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 241e0295b16ae350cec213bf25b93f7ad72a0808
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>コンパイラの警告 (レベル 1 およびレベル 4) C4949
マネージおよびアンマネージのプラグマはコンパイルしたときにのみ意味のある '/clr [: オプション]'  
  
 コンパイラは無視、[マネージ](../../preprocessor/managed-unmanaged.md)と、ソース コードがコンパイルされていない場合は、プラグマをアンマネージ[/clr](../../build/reference/clr-common-language-runtime-compilation.md)です。 これは、情報提供の警告です。  
  
 次の例では、C4949 が生成されます。  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 ときに**#pragma をアンマネージ**なしで使われた**/clr**C4949 はレベル 4 の警告です。  
  
 次の例では、C4949 が生成されます。  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```
