---
title: "コンパイラの警告 (レベル 1 およびレベル 4) C4700 | Microsoft Docs"
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
  - "C4700"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4700"
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1 およびレベル 4) C4700
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

初期化されていないローカル変数 '名前' が使用されます  
  
 初めに値を代入せずに、ローカル変数 *name* を使用しています。このため、予想しない結果になることがあります。  
  
 次の例では警告 C4700 が生成されます。  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 [\/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) の場合、これはレベル 4 の警告です。次の例では警告 C4700 が生成されます。  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```