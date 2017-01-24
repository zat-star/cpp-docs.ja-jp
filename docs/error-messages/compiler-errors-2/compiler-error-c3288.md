---
title: "コンパイラ エラー C3288 | Microsoft Docs"
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
  - "C3288"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3288"
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3288
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : ハンドル型の無効な逆参照です  
  
 コンパイラは、ハンドル型の無効な逆参照を検出しました。  ハンドル型を逆参照して、それを参照に代入できます。  詳細については、「[Tracking Reference Operator](../../windows/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では C3288 エラーが生成されます。  
  
```  
// C3288.cpp  
// compile with: /clr  
ref class R {};  
int main() {  
   *(System::Object^) nullptr;   // C3288  
  
// OK  
   (System::Object^) nullptr;   // OK  
   R^ r;  
   R% pr = *r;  
}  
```