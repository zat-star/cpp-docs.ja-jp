---
title: "コンパイラ エラー C2379 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2379"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2379"
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2379
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

number 番目の引数の型は以前の宣言の型と一致しません。  
  
 指定されたパラメーターの型は、既定の上位変換を行っても以前の宣言にある型と互換性がありません。  これは、ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md) オプション指定\) ではエラーになり、Microsoft 拡張機能 \(**\/Ze** オプション指定\) では警告になります。  
  
 次の例では警告 C2379 が生成されます。  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```