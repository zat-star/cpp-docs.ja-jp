---
title: "コンパイラ エラー C2711 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2711"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2711"
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2711
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : この関数はマネージとしてコンパイルできません。\#pragma をアンマネージで使用してください  
  
 一部の命令により、コンパイラは外側の関数の MSIL を生成できなくなります。  
  
 次の例では警告 C2711 が生成されます。  
  
```  
// C2711.cpp  
// compile with: /clr  
// processor: x86  
using namespace System;  
value struct V {  
   static const t = 10;  
};  
  
void bar() {  
   V::t;  
   __asm int 3   // C2711 inline asm can't be compiled managed  
}  
```