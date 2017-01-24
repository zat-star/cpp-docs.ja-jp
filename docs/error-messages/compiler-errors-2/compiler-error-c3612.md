---
title: "コンパイラ エラー C3612 | Microsoft Docs"
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
  - "C3612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3612"
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': シール クラスを抽象にすることはできません。  
  
 既定では、`value` \(または [\_\_value](../../misc/value.md)\) で定義された型はシールされます。クラスは、基本となるすべてのメソッドを実装しない限り抽象クラスになります。  シールされた抽象クラスは、基本クラスにできず、インスタンス化もできません。  
  
 詳細については、「[Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3612 が生成されます。  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```