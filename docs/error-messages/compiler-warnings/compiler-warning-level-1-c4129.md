---
title: "コンパイラの警告 (レベル 1) C4129 | Microsoft Docs"
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
  - "C4129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4129"
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' : エスケープ シーケンスとして正しく認識されませんでした。  
  
 文字定数か文字列定数の円記号 \(\\\) の後の文字 `character` が、エスケープ シーケンスとして正しく認識されません。  円記号は無視され、表示されません。  円記号の後の文字は表示されます。  
  
 円記号を表示するには、\\\\ のように二重に円記号を指定してください。  
  
 C\+\+ 標準のセクション 2.13.2 には、エスケープ シーケンスについての説明があります。  
  
 次の例では警告 C4129 が生成されます。  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```