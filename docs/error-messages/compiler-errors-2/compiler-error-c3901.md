---
title: "コンパイラ エラー C3901 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3901"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3901"
ms.assetid: 19af4141-39ad-4c16-a68f-3ae76f648186
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3901
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'accessor\_function': 戻り値の型 '型' を指定しなければなりません  
  
 少なくとも 1 つの get メソッドの戻り値の型が、プロパティの型と一致する必要があります。  詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3901 が生成されます。  
  
```  
// C3901.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String^ Name {  
      void get();   // C3901  
      // try the following line instead  
      // String^ get();  
   };  
};  
  
ref class Y {  
   property double values[int, int] {  
      int get(int, int);   // C3901  
      // try the following line instead  
      // double get(int, int);  
   };  
};  
```