---
title: "コンパイラ エラー C2313 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2313"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2313"
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2313
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1': 行番号の参照 \('type2'\) でキャッチされます  
  
 例外の型には 2 つのハンドラーがあります。 2 番目の catch の型は、最初の型への参照です。  
  
 次の例では C2313 が生成されます。  
  
```  
// C2313.cpp // compile with: /EHsc #include <eh.h> class C {}; int main() { try { throw "ooops!"; } catch( C& ) {} catch( C ) {}   // C2313 }  
```