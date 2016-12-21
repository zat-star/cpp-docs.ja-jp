---
title: "コンパイラ エラー C2845 | Microsoft Docs"
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
  - "C2845"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2845"
ms.assetid: 31b28ee9-978f-403b-94d8-dbaacd24cce0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2845
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'演算子' : ポインター演算はこの型では使用できません  
  
 マネージ クラスへのポインターはインクリメントできません。  
  
 **C\+\+ マネージ拡張**  
  
 [\_\_gc](../Topic/__gc.md) クラスへのポインターはインクリメントできません。また、文字列演算子は **\/clr** でのみ使用でき、**\/clr:oldSyntax** では使用できません。  
  
 次の例では警告 C2845 が生成されます。  
  
```  
// C2845b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class X {};  
  
int main() {  
   X *pX = new X;  
   pX++;   // C2845  
  
   String * a = new String("abc");  
   String * b = new String("def");  
   Console::WriteLine(a + b);   // C2845 not with /clr:oldSyntax  
}  
```