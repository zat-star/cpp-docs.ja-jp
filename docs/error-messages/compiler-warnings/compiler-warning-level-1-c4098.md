---
title: "コンパイラの警告 (レベル 1) C4098 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4098"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4098"
ms.assetid: 8c8aef1c-1639-44ec-a3dd-c0dfe9aa727d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 1) C4098
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 戻り値の型が void で宣言された関数が、値を返しました。  
  
 戻り値の型を [void](../../cpp/void-cpp.md) 型として宣言した関数に、値を返す `return` ステートメントがあります。  コンパイラは、この関数の戻り値を `int`型の値であると見なします。