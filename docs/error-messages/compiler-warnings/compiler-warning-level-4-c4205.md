---
title: "コンパイラの警告 (レベル 4) C4205 | Microsoft Docs"
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
  - "C4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4205"
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 関数内の静的関数の宣言です。  
  
 Microsoft 拡張機能 \(\/Ze\) では、**static** 関数の宣言を別の関数の中から行うことができます。  この場合、関数はグローバル スコープを持ちます。  
  
## 使用例  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 このような初期化は、ANSI 互換のオプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。