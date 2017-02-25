---
title: "コンパイラ エラー C3662 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3662"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3662"
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C3662
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'member': オーバーライド指定子 'specifier' は、マネージまたは WinRT クラスのメンバー関数でのみ使用できます  
  
 オーバーライド指定子が、ネイティブ型のメンバーで使用されました。これは許可されていません。  
  
 詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3662 が生成されます。  
  
```  
// C3662.cpp  
// compile with: /clr /c  
struct S {  
   virtual void f();  
};  
  
struct S1 : S {  
   virtual void f() new;   // C3662  
};  
  
ref struct T {  
   virtual void f();  
};  
  
ref struct T1 : T {  
   virtual void f() new;   // OK  
};  
```