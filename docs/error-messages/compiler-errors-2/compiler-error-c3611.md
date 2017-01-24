---
title: "コンパイラ エラー C3611 | Microsoft Docs"
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
  - "C3611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3611"
ms.assetid: 42f3e320-41de-420a-bd05-8924cab765aa
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数': シール関数は純粋指定子を含むことはできません  
  
 シール関数の宣言が正しくありません。詳細については、「[sealed](../../windows/sealed-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3611 エラーが生成されます。  
  
```  
// C3611.cpp  
// compile with: /clr /c  
  
ref struct V {  
   virtual void Test() sealed = 0;   // C3611  
   virtual void Test2() sealed;   // OK  
   virtual void Test3() = 0;   // OK  
};  
```