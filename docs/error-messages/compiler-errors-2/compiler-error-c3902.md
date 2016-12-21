---
title: "コンパイラ エラー C3902 | Microsoft Docs"
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
  - "C3902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3902"
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'アクセサー': 最後のパラメーターの型は '型' でなければなりません  
  
 少なくとも 1 つの set メソッドの最後のパラメーターの型が、プロパティの型と一致する必要があります。  詳細については、「[プロパティ](../../windows/property-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3902 が生成されます。  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```