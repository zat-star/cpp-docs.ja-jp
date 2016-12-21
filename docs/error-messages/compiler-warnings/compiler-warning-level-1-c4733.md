---
title: "コンパイラの警告 (レベル 1) C4733 | Microsoft Docs"
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
  - "C4733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4733"
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インライン asm は 'FS:0' に割り当てています : ハンドラーは安全なハンドラーとして登録されていません。  
  
 新規例外ハンドラーを追加するために FS:0 の値を変更する関数は、安全な例外では動作しないことがあります。このハンドラーを有効な例外ハンドラーとして登録できないためです。「[\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md)」を参照してください。  
  
 この警告を解決するには、FS:0 定義を削除するか、この警告をオフにし、[.SAFESEH](../Topic/.SAFESEH.md) を使用して安全な例外ハンドラーを指定します。  
  
 次の例では警告 C4733 が生成されます。  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```