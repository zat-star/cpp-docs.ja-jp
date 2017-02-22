---
title: "コンパイラ エラー C3179 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3179"
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C3179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
  
 次の例は C3179 を生成し、その修正方法を示しています。  
  
```  
// C3179b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
typedef __value struct {   // C3179  
// try the following line instead  
// typedef __value struct MyStruct {  
   int i;  
} V;  
```