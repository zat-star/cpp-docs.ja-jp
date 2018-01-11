---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4949 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4949
dev_langs: C++
helpviewer_keywords: C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d23a6d6e030007289cc50ce0372acc8f99e7ed3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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