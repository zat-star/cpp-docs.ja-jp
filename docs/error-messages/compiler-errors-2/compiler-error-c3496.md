---
title: "コンパイラ エラー C3496 | Microsoft Docs"
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
  - "C3496"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3496"
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3496
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' は常に値によってキャプチャされます。'&' は無視されました  
  
 参照で`this` ポインターをキャプチャすることはできません。  
  
### このエラーを解決するには  
  
-   値で`this` ポインターをキャプチャします。  
  
## 使用例  
 次の例では、`this` ポインターへの参照がラムダ式のキャプチャ リストにあるため、C3496 が生成されます。  
  
```  
// C3496.cpp // compile with: /c class C { void f() { [&this] {}(); // C3496 } };  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)