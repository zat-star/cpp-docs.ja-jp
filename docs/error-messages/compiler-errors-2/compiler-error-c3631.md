---
title: "コンパイラ エラー C3631 | Microsoft Docs"
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
  - "C3631"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3631"
ms.assetid: 88cbd2d5-6fef-4940-be34-d8cbe816d3da
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3631
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': マネージ イベントまたは WinRT イベントをオーバーロードできません  
  
 マネージ イベントまたは WinRT イベントをオーバーロードできません。  
  
## 使用例  
 C3631 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では C3631 が生成されます。  
  
```  
// C3631.cpp  
// compile with: /clr:oldSyntax /c  
  
public __gc struct S2 {  
   __event void func1();     
   __event void func1(int);   // C3631 delete second declaration of func1  
};  
  
public __gc struct S1 {  
   __delegate void del1();  
   __delegate void del2();  
   __event int add_myE(del1*) { return 0; }     
   __event int remove_myE(del1*) { return 0; }     
   __event int add_myE(del2*) { return 0; }   // C3631  
   __event int remove_myE(del2*) { return 0; }   // C3631  
};  
```