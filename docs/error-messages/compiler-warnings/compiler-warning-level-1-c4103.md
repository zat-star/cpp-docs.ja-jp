---
title: "コンパイラの警告 (レベル 1) C4103 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 115c88a43f38065541fe925b023d61679c06be53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4103"></a>コンパイラの警告 (レベル 1) C4103
'filename': #pragma pack(pop) がないため配置ヘッダーを含めた後に変更された可能性があります  
  
 梱包、クラスのレイアウトに影響して、一般的には、複数のヘッダー ファイルの変更を梱包する場合は問題があります。  
  
 #Pragma[パック](../../preprocessor/pack.md)(pop) この警告を解決するのには、ヘッダー ファイルを終了する前にします。  
  
 次の例では、C4103 が生成されます。  
  
```  
// C4103.h  
#pragma pack(push, 4)  
  
// defintions and declarations  
  
// uncomment the following line to resolve  
// #pragma pack(pop)  
```  
  
 この場合、次のようになります。  
  
```  
// C4103.cpp  
// compile with: /LD /W1  
#include "c4103.h"   // C4103  
```