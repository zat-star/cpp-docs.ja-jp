---
title: "コンパイラ エラー C3854 | Microsoft Docs"
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
  - "C3854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3854"
ms.assetid: 32a9ead0-c6c7-485a-8802-c7b1fe921d3a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\=' の左辺の式は、関数に対して評価します。関数に割り当てられません。\(関数は左辺値ではありません\)  
  
 参照を再初期化できません。  関数への参照を逆参照して生成される関数は右辺値であるため、代入できません。  そのため、参照を使用して関数に代入することはできません。  
  
 次の例では警告 C3854 が生成されます。  
  
```  
// C3854.cpp  
int afunc(int i)  
{  
   return i;  
}  
  
typedef int (& rFunc_t)(int);  
typedef int (* pFunc_t)(int);  
  
int main()  
{  
   rFunc_t rf = afunc;   // OK binding a reference to function  
   pFunc_t pf = &afunc;   // OK initializing a pointer to function  
  
   *pf = &afunc;   // C3854  
   // try the following line instead  
   // pf = &afunc;  
   *rf = &afunc;   // C3854  
}  
```