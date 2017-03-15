---
title: "コンパイラ エラー C2095 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2095"
ms.assetid: 44f8ada1-974f-4e81-a408-33ac6695aa53
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : void 型引数を関数に渡そうとしました。'number' 番目の引数にエラーがあります。  
  
 関数に渡されたパラメーターは `void` 型ですが、この型は使用できません。  代わりに void 型へのポインター \(`void *`\) を使用してください。  
  
 `number` は `void` 型のパラメーターを示します。