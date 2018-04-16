---
title: "コンパイラの警告 (レベル 1) C4237 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4237
dev_langs:
- C++
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89fa6a15c77ad0107dc3ef39a3563cae3ddecab4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4237"></a>コンパイラの警告 (レベル 1) C4237
'keyword' キーワードがサポートされていませんが、将来使用するために予約されています  
  
 C++ の仕様のキーワードは、Visual C コンパイラで実装されていませんが、キーワードは、ユーザー定義の記号として使用できません。  
  
 次の例では、C4237 が生成されます。  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```