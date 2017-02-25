---
title: "コンパイラの警告 (レベル 3) C4570 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4570"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4570"
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 3) C4570
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : 明示的に抽象として宣言されていませんが、抽象関数を含んでいます  
  
 [abstract](../../windows/abstract-cpp-component-extensions.md) 関数を含む型は、それ自体が abstract としてマークされている必要があります。  
  
## 使用例  
 次の例では C4570 エラーが生成されます。  
  
```  
// C4570.cpp  
// compile with: /clr /W3 /c  
ref struct X {   // C4570  
// try the following line instead  
// ref class X abstract {  
   virtual void f() abstract;  
};  
```