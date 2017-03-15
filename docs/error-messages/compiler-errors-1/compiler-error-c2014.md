---
title: "コンパイラ エラー C2014 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2014"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2014"
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C2014
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プリプロセッサ ディレクティブのシャープ記号 \(\#\) の前に、空白文字以外の文字があります。  
  
 プリプロセッサ ディレクティブのシャープ記号 \(`#`\) は、行の空白文字以外の最初の文字であることが必要です。  
  
 次の例では警告 C2014 が生成されます。  
  
```  
// C2014.cpp  
int k; #include <stdio.h>   // C2014  
```  
  
 解決方法 :  
  
```  
// C2014b.cpp  
// compile with: /c  
int k;   
#include <stdio.h>  
```