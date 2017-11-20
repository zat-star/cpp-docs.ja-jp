---
title: "コンパイラ エラー C2586 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2586
dev_langs: C++
helpviewer_keywords: C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c98f9a9f5e5f16cec23c8bc6de7efda7a7ce473d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2586"></a>コンパイラ エラー C2586
ユーザー定義の変換を正しくない構文: 無効な間接指定  
  
 変換演算子の間接参照を指定することはできません。  
  
 次の例では、C2586 が生成されます。  
  
```  
// c2586.cpp  
// compile with: /c  
struct C {  
   * operator int();   // C2586  
   operator char();   // OK  
};  
```