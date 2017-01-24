---
title: "コンパイラ エラー C3484 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3484"
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

戻り値の型の前に '\-\>' が必要です  
  
 ラムダ式の戻り値の型の前に `->` を指定する必要があります。  
  
### このエラーを解決するには  
  
-   戻り値の型の前に `->` を指定します。  
  
## 使用例  
 次の例では C3484 が生成されます。  
  
```  
// C3484a.cpp int main() { return []() . int { return 42; }(); // C3484 }  
```  
  
## 使用例  
 次の例では、ラムダ式の戻り値の型の前に `->` を指定して C3484 を解決します。  
  
```  
// C3484b.cpp int main() { return []() -> int { return 42; }(); }  
```  
  
## 参照  
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)