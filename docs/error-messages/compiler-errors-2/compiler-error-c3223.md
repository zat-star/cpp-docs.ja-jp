---
title: "コンパイラ エラー C3223 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3223"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3223"
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3223
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property' : 'typeid' をプロパティに適用できません  
  
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) をプロパティに適用できません。  
  
## 使用例  
 次の例では C3223 が生成されます。  
  
```  
// C3223.cpp // compile with: /clr ref class R { public: property int myprop; }; int main() { System::Type^ type2 = R::myprop::typeid;   // C3223 }  
```