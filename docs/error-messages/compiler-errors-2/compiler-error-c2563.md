---
title: "コンパイラ エラー C2563 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2563"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2563"
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2563
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

仮引数リストまたは関数へのポインターが、適合していません。  
  
 関数の仮パラメーター リスト \(または関数へのポインター\) が、ほかの関数の仮パラメーター リスト \(またはメンバー関数へのポインター\) と一致していません。  このため、関数やポインターの代入ができません。  
  
 次の例では警告 C2563 が生成されます。  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```