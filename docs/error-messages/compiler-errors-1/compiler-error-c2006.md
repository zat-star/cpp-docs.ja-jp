---
title: "コンパイラ エラー C2006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'ディレクティブ' : 'token' はファイル名ではありません。  
  
 [\#include](../../preprocessor/hash-include-directive-c-cpp.md) や [\#import](../Topic/%23import%20Directive%20\(C++\).md) などのディレクティブにはファイル名が必要です。  このエラーを解決するには、*token* に有効なファイル名を指定してください。  または、ファイル名を二重引用符または山かっこで囲んでください。  
  
 次の例では警告 C2006 が生成されます。  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 解決方法 :  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```