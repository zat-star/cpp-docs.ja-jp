---
title: "コンパイラ エラー C3375 | Microsoft Docs"
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
  - "C3375"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3375"
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3375
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': あいまいなデリゲート関数です  
  
 デリゲートのインスタンス化が静的メンバー関数向けであるか、またはインスタンス関数へのバインドされていないデリゲートとして存在した可能性があるため、コンパイラはこのエラーを発行しました。  
  
 詳細については、「[delegate](../../windows/delegate-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では警告 C3375 が生成されます。  
  
```  
// C3375.cpp // compile with: /clr ref struct R { static void f(R^) {} void f() {} }; delegate void Del(R^); int main() { Del ^ a = gcnew Del(&R::f);   // C3375 }  
```