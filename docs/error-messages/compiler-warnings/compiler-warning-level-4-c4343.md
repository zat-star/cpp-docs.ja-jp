---
title: "コンパイラの警告 (レベル 4) C4343 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
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
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: a67b44c766f51acb7a9d4cacc94448f1b4594c3e
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-4-c4343"></a>コンパイラの警告 (レベル 4) C4343
\#プラグマ optimize("g",off)/Og オプションをオーバーライドします  
  
 この警告でのみ、Itanium プロセッサ ファミリ (IPF) コンパイラでは有効であると報告プラグマ[最適化](../../preprocessor/optimize.md)加わりました、 [/Og](../../build/reference/og-global-optimizations.md)コンパイラ オプション。  
  
 次の例では C4343 が生成されます。  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```
