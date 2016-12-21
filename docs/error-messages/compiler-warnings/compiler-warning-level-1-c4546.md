---
title: "コンパイラの警告 (レベル 1) C4546 | Microsoft Docs"
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
  - "C4546"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4546"
ms.assetid: 071e1709-3841-46c1-8e71-96109cd22041
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4546
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンマの前の関数呼び出しに引数一覧がありません。  
  
 不正な形式のコンマ式が検出されました。  
  
 既定では、この警告はオフに設定されています。  詳細については、「[Compiler Warnings That Are Off by Default](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
## 使用例  
 次の例では警告 C4546 が生成されます。  
  
```  
// C4546.cpp  
// compile with: /W1  
#pragma warning (default : 4546)  
void f(int i) {  
   i++;  
}  
  
int main() {  
   int i = 0, k = 0;  
  
   if ( f, k )   // C4546  
   // try the following line instead  
   // if ( f(i), k )  
      i++;  
}  
```