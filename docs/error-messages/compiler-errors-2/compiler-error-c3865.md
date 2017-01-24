---
title: "コンパイラ エラー C3865 | Microsoft Docs"
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
  - "C3865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3865"
ms.assetid: 9bc62bb0-4fb8-4856-a5cf-c7cb4029a596
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'calling\_convention' : ネイティブ メンバー関数でのみ使用することができます  
  
 グローバル関数、またはマネージ メンバー関数である関数で呼び出し規約が使用されました。  呼び出し規約は、ネイティブ \(非マネージ\) メンバー関数でだけ使用できます。  
  
 詳細については、「[呼び出し規約](../Topic/Calling%20Conventions.md)」を参照してください。  
  
 次の例では警告 C3865 が生成されます。  
  
```  
// C3865.cpp  
// compile with: /clr  
// processor: x86  
void __thiscall Func(){}   // C3865  
  
// OK  
struct MyType {  
   void __thiscall Func(){}  
};  
```