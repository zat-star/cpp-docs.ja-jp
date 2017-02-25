---
title: "コンパイラ エラー C2582 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2582"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2582"
ms.assetid: ee1b9378-8bcd-4792-b87e-6d7a466d29ed
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# コンパイラ エラー C2582
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' 関数を '型' で使用できません。  
  
 代入演算子を持たないオブジェクトに代入しようとしました。  
  
 次の例では警告 C2582 が生成されます。  
  
```  
// C2582.cpp  
// compile with: /clr  
using namespace System;  
  
struct N {};  
ref struct O {};  
ref struct R {  
   property O prop;   // C2582  
   property O ^ prop2;   // OK  
};  
  
int main() {  
   String ^ st1 = gcnew String("");  
   ^st1 = gcnew String("");   // C2582  
   st1 = "xxx";   // OK  
}  
```