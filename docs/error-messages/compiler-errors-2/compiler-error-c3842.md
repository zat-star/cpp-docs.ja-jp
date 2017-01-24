---
title: "コンパイラ エラー C3842 | Microsoft Docs"
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
  - "C3842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3842"
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT またはマネージ型のメンバー関数に対する 'function': 'const' および 'volatile' 修飾子はサポートされていません  
  
 [const](../../cpp/const-cpp.md) と [volatile](../../cpp/volatile-cpp.md) は、Windows ランタイムまたはマネージ型のメンバー関数ではサポートされていません。  
  
 次の例では C3842 が生成されます。  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
  
```