---
title: "致命的なエラー C1311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1311"
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 致命的なエラー C1311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

COFF 形式は、'var' をアドレスの '数値' バイトと共に静的に初期化できません  
  
 コンパイル時に値が認識されないアドレスを、型のストレージが 4 バイト未満の変数に静的に代入することはできません。  
  
 このエラーは、有効な C\+\+ 以外のコードで発生します。  
  
 次の例は、C1311 を引き起こす可能性のある 1 個の条件。  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```