---
title: "コンパイラの警告 (レベル 4) C4682 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4682"
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'parameter': 方向性のあるパラメーター属性が指定されていません。\[in\] を既定とします  
  
 属性付きインターフェイスのパラメーターのメソッドに、方向属性 [in](../Topic/in%20\(C++\).md) または [out](../Topic/out%20\(C++\).md) が指定されていません。 パラメーターの既定値は in です。  
  
 既定では、この警告はオフに設定されています。 詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
 次の例では C4682 警告が生成されます。  
  
```  
// C4682.cpp // compile with: /W4 #pragma warning(default : 4682) #include <windows.h> [module(name="MyModule")]; [ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ] __interface IMyIface : IUnknown { HRESULT f1(int i, int *pi); // C4682 // try the following line // HRESULT f1([in] int i, [in] int *pi); }; int main() { }  
```