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
ms.openlocfilehash: 93009d77c40535997ecc42ccb715f5fe81d79798
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
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