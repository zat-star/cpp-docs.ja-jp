---
title: "コンパイラ エラー C2055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2055"
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型リストではなく、仮引数リストが必要です。  
  
 関数定義の中で、仮パラメーター リストを置く必要がある部分にパラメーターの型リストが置かれています。  ANSI C では、void または省略記号 \(`...`\) 以外の仮パラメーターには名前を付ける必要があります。  
  
 次の例では警告 C2055 が生成されます。  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```