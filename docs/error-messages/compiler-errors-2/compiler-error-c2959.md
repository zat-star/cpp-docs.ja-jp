---
title: "コンパイラ エラー C2959 | Microsoft Docs"
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
  - "C2959"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2959"
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2959
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ジェネリック クラスまたは関数は、テンプレートのメンバーになることはできません  
  
 詳細については、「[Windows Runtime and Managed Templates](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)」および「[Generics](../../windows/generics-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C2959 エラーが生成されます。  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```