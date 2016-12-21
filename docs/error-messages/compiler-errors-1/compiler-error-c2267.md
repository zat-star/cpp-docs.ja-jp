---
title: "コンパイラ エラー C2267 | Microsoft Docs"
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
  - "C2267"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2267"
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2267
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : ブロック スコープを持つ関数は、static として宣言できません。  
  
 ローカル関数が `static` として宣言されています。  静的関数はグローバル スコープを持つ必要があります。  
  
 次の例では警告 C2267 が生成されます。  
  
```  
// C2267.cpp  
static int func2();   // OK  
int main() {  
    static int func1();   // C2267  
}  
```