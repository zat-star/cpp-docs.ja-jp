---
title: "コンパイラ エラー C3360 | Microsoft Docs"
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
  - "C3360"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3360"
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3360
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'string': 名前を作成できません  
  
 [uuid](../../windows/uuid-cpp-attributes.md) 属性に渡された値は無効です。  
  
 次の例では C3360 が生成されます。  
  
```  
// C3360.cpp [ uuid("1") ] // try this line instead // [ uuid("12341234-1234-1234-1234-123412341234") ] struct A   // C3360 { }; int main() { }  
```