---
title: "コンパイラの警告 (レベル 1) C4812 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4812"
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

旧形式の宣言スタイル: 'new\_syntax' を使用してください  
  
 現在のリリースの Visual C\+\+ では、コンストラクターの明示的な特殊化がサポートされていますが、将来のリリースではサポートされない可能性があります。  
  
 次の例では C4812 が生成されます。  
  
```  
// C4812.cpp // compile with: /W1 /c template <class T> class MyClass; template<class T> class MyClass<T*> { MyClass(); }; template<class T> MyClass<T*>::MyClass<T*>() {}   // C4812 // try the following line instead // MyClass<T*>::MyClass() {}  
```