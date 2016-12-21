---
title: "コンパイラ エラー C2906 | Microsoft Docs"
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
  - "C2906"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2906"
ms.assetid: 30f652f1-6af6-4a2f-a69e-a1a4876cc8c6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2906
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

「specialization」: 明示的な特殊化は必要な"テンプレート \<\>」  
  
 テンプレートの明示的な特化には、新しい構文を使用する必要があります。  
  
 次の例では警告 C2906 が生成されます。  
  
```  
// C2906.cpp  
// compile with: /c  
template<class T> class X{};   // primary template  
class X<int> { }   // C2906  
template<> class X<int> { };   // new syntax  
```