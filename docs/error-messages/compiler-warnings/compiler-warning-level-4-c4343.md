---
title: "コンパイラの警告 (レベル 4) C4343 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4343
dev_langs:
- C++
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bf7ab18e58a7c77da42e6497c39e716b632d2f7b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4343"></a>コンパイラの警告 (レベル 4) C4343
\#プラグマ optimize("g",off)/Og オプションをオーバーライドします  
  
 この警告 (Itanium プロセッサ ファミリ (IPF) コンパイラでのみ有効) は、pragma [optimize](../../preprocessor/optimize.md) が [/Og](../../build/reference/og-global-optimizations.md) コンパイラ オプションをオーバーライドしたことを報告します。  
  
 次の例では C4343 が生成されます。  
  
```  
// C4343.cpp  
// compile with: /Og /W4 /LD  
// processor: IPF  
#pragma optimize ("g", off)   // C4343  
```