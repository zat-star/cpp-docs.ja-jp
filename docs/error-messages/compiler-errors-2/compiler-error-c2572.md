---
title: "コンパイラ エラー C2572 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2572
dev_langs: C++
helpviewer_keywords: C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a0825883dae30dcee267f09322467590a6a405cd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2572"></a>コンパイラ エラー C2572
'class::member': 既定のパラメーターの再定義: パラメーター param  
  
 既定のパラメーターを再定義することはできません。 必要な場合別の値パラメーターには、既定のパラメーターを未定義のままです。  
  
 次の例では、C2572 が生成されます。  
  
```  
// C2572.cpp  
// compile with: /c  
void f(int i = 1);   // function declaration  
  
// function definition  
void f(int i = 1) {}   // C2572  
  
// try the following line instead  
// void f(int i) {}  
```