---
title: "コンパイラ エラー C2785 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2785"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2785"
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# コンパイラ エラー C2785
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration1' および 'declaration2' で戻り値の型が異なります。  
  
 特化された形式の関数テンプレートとプライマリ関数テンプレートの戻り値の型が異なります。  
  
### このエラーを解決するには  
  
1.  特化された形式のすべての関数テンプレートについて、戻り値の型に一貫性があるかどうかを確認してください。  
  
## 使用例  
 次の例では警告 C2785 が生成されます。  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```