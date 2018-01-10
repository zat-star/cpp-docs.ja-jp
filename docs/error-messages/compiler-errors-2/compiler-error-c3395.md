---
title: "コンパイラ エラー C3395 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3395
dev_langs: C++
helpviewer_keywords: C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d937766291b32850c32b87c1405aa5ea0b71956
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3395"></a>コンパイラ エラー C3395
'function': 方式を伴う関数に適用できません、 \__clrcall 呼び出し規約  
  
 `__declspec(dllexport)`および[_ _clrcall](../../cpp/clrcall.md)は互換性がありません。  詳細については、次を参照してください。 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)です。  
  
 次の例では、C3395 が生成されます。  
  
```  
// C3395.cpp  
// compile with: /clr /c  
  
__declspec(dllexport) void __clrcall Test(){}   // C3395  
void __clrcall Test2(){}   // OK  
__declspec(dllexport) void Test3(){}   // OK  
```