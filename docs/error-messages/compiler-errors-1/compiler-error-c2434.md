---
title: "コンパイラ エラー C2434 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2434"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2434"
ms.assetid: 01329e26-7c74-4219-b74f-69e3a40c9738
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2434
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'シンボル' : \_\_declspec\(process\) と共に宣言されたシンボルは、\/clr:pure モードで動的に初期化できません  
  
 プロセスごとの変数は **\/clr:pure** 環境で動的に初期化できません。  詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」および「[プロセス](../../cpp/process.md)」を参照してください。  
  
## 使用例  
 次の例では C2434 エラーが生成されます。  
  
```  
// C2434.cpp  
// compile with: /clr:pure /c  
int f() { return 0; }  
__declspec(process) int i = f();   // C2434  
__declspec(process) int i2 = 0;   // OK  
```