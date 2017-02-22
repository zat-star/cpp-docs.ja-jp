---
title: "コンパイラ エラー C3646 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3646"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3646"
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3646
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'指定子' : 不明なオーバーライド指定子です  
  
 コンパイラは、オーバーライド指定子が指定されているはずの位置にトークンを見つけましたが、このトークンを認識できませんでした。  
  
 詳細については、「[オーバーライド指定子](../../windows/override-specifiers-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3646 が生成されます。  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```