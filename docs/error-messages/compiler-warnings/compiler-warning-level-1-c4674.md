---
title: "コンパイラの警告 (レベル 1) C4674 | Microsoft Docs"
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
  - "C4674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4674"
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' は宣言された 'static' であり、パラメーターを 1 つだけ持たなければなりません。  
  
 変換演算子の署名が正しくありません。 メソッドは、ユーザー定義の変換とは見なされません。  
  
 新しい構文 \(**\/clr**\) を使用する場合、演算子の定義については、「[ユーザー定義の演算子](../../dotnet/user-defined-operators-cpp-cli.md)」と「[ユーザー定義変換](../../dotnet/user-defined-conversions-cpp-cli.md)」を参照してください。  
  
## 使用例  
 次の例では C4674 が生成されます。  
  
```  
// C4674.cpp // compile with: /clr /WX /W1 /LD ref class G { int op_Implicit(int i) {   // C4674 return 0; } };  
```  
  
## 使用例  
 次の例では C4674 が生成されます。  
  
```  
// C4674_b.cpp // compile with: /clr:oldSyntax /W1 /LD __gc class G { int op_Implicit(int i) {   // C4674 // try the following line instead // static int op_Implicit(int i) { return 0; } };  
```