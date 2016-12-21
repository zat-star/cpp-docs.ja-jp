---
title: "コンパイラの警告 (レベル 4) C4213 | Microsoft Docs"
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
  - "C4213"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4213"
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4213
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 左辺値でキャストしました。  
  
 既定の Microsoft 拡張機能 \(\/Ze\) では、代入ステートメントの左辺でキャストを使用できます。  
  
## 使用例  
  
```  
// C4213.c  
// compile with: /W4  
void *a;  
void f()  
{  
   int   i[3];  
   a = &i;  
   *(( int * )a )++ = 3;  // C4213  
}  
  
int main()  
{  
}  
```  
  
 このようなキャストは ANSI 互換オプション \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) では無効です。