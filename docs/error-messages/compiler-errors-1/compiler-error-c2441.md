---
title: "コンパイラ エラー C2441 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2441"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2441"
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラ エラー C2441
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'変数' : \_\_declspec\(process\) と共に宣言されたシンボルは、\/clr:pure モードで const を指定しなければなりません  
  
 既定では、**\/clr:pure** を指定した場合、変数はアプリケーション ドメインごとに有効になります。  **\/clr:pure** を指定して `__declspec(process)` とマークされている変数は、あるアプリケーション ドメインで変更され、別のドメインで読み取られるとエラーが発生しやすくなります。  
  
 このため、コンパイラは、**\/clr:pure** が指定されている場合はプロセスごとに変数を強制的に `const` にして、すべてのアプリケーション ドメインで読み取り専用にします。  
  
 詳細については、「[プロセス](../../cpp/process.md)」および「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## 使用例  
 次の例では C2441 エラーが生成されます。  
  
```  
// C2441.cpp  
// compile with: /clr:pure /c  
__declspec(process) int i;   // C2441  
__declspec(process) const int j = 0;   // OK  
```