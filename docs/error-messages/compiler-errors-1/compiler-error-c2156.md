---
title: "コンパイラ エラー C2156 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2156"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2156"
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2156
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プラグマは、関数の外に指定されなければなりません。  
  
 グローバル レベル \(関数本体外\) で指定する必要があるプラグマが関数内にあります。  
  
 次の例では C2156 が生成されます。  
  
```  
// C2156.cpp #pragma optimize( "l", on )   // OK int main() { #pragma optimize( "l", on )   // C2156 }  
```