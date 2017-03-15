---
title: "コンパイラ エラー C3910 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3910"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3910"
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C3910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'イベント': メンバー 'メソッド' を定義しなければなりません  
  
 イベントが定義されましたが、指定された必須アクセサー メソッドが含まれていません。  
  
 詳細については、「[イベント](../../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3910 が生成されます。  
  
```  
// C3910.cpp  
// compile with: /clr /c  
delegate void H();  
ref class X {  
   event H^ E {  
      // uncomment the following lines  
      // void add(H^) {}  
      // void remove( H^ h ) {}  
      // void raise( ) {}  
   };   // C3910  
  
   event H^ E2; // OK data member  
};  
```