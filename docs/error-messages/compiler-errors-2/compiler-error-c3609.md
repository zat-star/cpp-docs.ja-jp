---
title: "コンパイラ エラー C3609 | Microsoft Docs"
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
  - "C3609"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3609"
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3609
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': sealed 関数または final 関数は仮想である必要があります  
  
 [sealed](../../windows/sealed-cpp-component-extensions.md) キーワードと [final](../../cpp/final-specifier.md) キーワードは、`virtual` でマークされたクラス、構造体、またはメンバー関数でのみ使用できます。  
  
 次の例では C3609 が生成されます。  
  
```  
// C3609.cpp  
// compile with: /clr /c  
ref class C {  
   int f() sealed;   // C3609  
   virtual int f2() sealed;   // OK  
};  
```  
  
 **C\+\+ マネージ拡張**  
  
 次の例では C3609 が生成されます。  
  
```  
// C3609c.cpp  
// compile with: /clr:oldSyntax /c  
__gc class C {  
   __sealed int f();   // C3609  
   __sealed virtual int f2();   // OK  
};  
```