---
title: "コンパイラ エラー C3721 | Microsoft Docs"
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
  - "C3721"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3721"
ms.assetid: c696ca38-3e00-4875-abbe-7bce0f46930e
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3721
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'signature' : イベントのシグネチャは互換性がありません。  
  
 イベントの宣言が正しくありません。  詳細については、「[\_\_event](../../cpp/event.md)」を参照してください。  
  
 C3721 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
## 使用例  
 次の例では C3721 エラーが生成されます。  
  
```  
// C3721.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
public __delegate void MyDel();  
  
public __gc class X {  
   __event void add_E1();      // C3721  
   // try the following line instead  
   // __event void add_E1(MyDel * p);  
  
   __event void remove_E1();   // C3721  
   // __event void remove_E1(MyDel * p);  
   // try the following line instead  
  
   __event void raise_E1();  
};  
```