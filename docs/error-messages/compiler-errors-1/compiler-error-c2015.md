---
title: "コンパイラ エラー C2015 | Microsoft Docs"
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
  - "C2015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2015"
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

定数の文字数が多すぎます。  
  
 文字定数に 3 つ以上の文字が入っています。  文字定数の文字数は、1 文字 \(標準文字定数の場合\) か 2 文字 \(ロング文字定数の場合\) に制限されています。  
  
 \\t などのエスケープ シーケンスは 1 つの文字に変換されます。  
  
## 使用例  
 次の例では警告 C2015 が生成されます。  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## 使用例  
 C2015 は、Microsoft 拡張機能 \(整数に変換される文字定数\) を使用する場合にも発生することがあります。次の例では警告 C2015 が生成されます。  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```