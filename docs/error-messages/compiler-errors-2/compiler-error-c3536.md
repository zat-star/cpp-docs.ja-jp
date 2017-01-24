---
title: "コンパイラ エラー C3536 | Microsoft Docs"
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
  - "C3536"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3536"
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3536
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 初期化前に使用することはできません  
  
 指定されたシンボルは、初期化する前に使用することはできません。  実際には、変数はその変数自体を初期化するために使用できないことを意味します。  
  
### このエラーを解決するには  
  
1.  変数を使用してその変数自体を初期化しようとしないでください。  
  
## 使用例  
 次の例では、各変数がその関数自体を使用して初期化されるため、C3536 が発生します。  
  
```  
// C3536.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto a = a;     //C3536  
   auto b = &b;    //C3536  
   auto c = c + 1; //C3536  
   auto* d = &d;   //C3536  
   auto& e = e;    //C3536  
   return 0;  
};  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)