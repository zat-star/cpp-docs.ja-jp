---
title: "コンパイラの警告 (レベル 4) C4365 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4365"
ms.assetid: af4b4191-bdfd-4dbb-8229-3ba4405df257
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 4) C4365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'action' : 'type\_1' から 'type\_2' に変換しました。signed\/unsigned が一致しません。  
  
 たとえば、符号なしの値を符号付きの値に変換しようとしました。  
  
 既定では、C4365 はオフに設定されています。詳細については、「[既定で無効になっているコンパイラ警告](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)」を参照してください。  
  
## 使用例  
 次の例では C4365 エラーが生成されます。  
  
```  
// C4365.cpp  
// compile with: /W4  
#pragma warning(default:4365)  
  
int f(int) { return 0; }  
void Test(size_t i) {}  
  
int main() {  
   unsigned int n = 10;  
   int o = 10;  
   n++;  
   f(n);   // C4365  
   f(o);   // OK  
  
   Test( -19 );   // C4365  
}  
```