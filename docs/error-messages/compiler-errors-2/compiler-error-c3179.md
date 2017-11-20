---
title: "コンパイラ エラー C3179 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3179
dev_langs: C++
helpviewer_keywords: C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8ce81f56a9cbdfda7ddef7ac1a6f9fcd7954d7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3179"></a>コンパイラ エラー C3179
匿名のマネージまたは WinRT 型は使用できません  
  
すべての CLR および WinRT のクラスと構造体には、名前が必要です。  
  
次の例は C3179 を生成し、その修正方法を示しています。  
  
```  
// C3179a.cpp  
// compile with: /clr /c  
typedef value struct { // C3179  
// try the following line instead  
// typedef value struct MyStruct {  
   int i;  
} V;  
```  
