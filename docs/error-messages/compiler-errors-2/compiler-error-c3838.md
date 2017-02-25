---
title: "コンパイラ エラー C3838 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3838"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3838"
ms.assetid: d6f470c2-131a-4a8c-843a-254acd43da83
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3838
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' から明示的に継承することはできません。  
  
 指定された `type` は、クラスの基本クラスとして機能できません。  
  
 次の例では警告 C3838 が生成されます。  
  
```  
// C3838a.cpp  
// compile with: /clr /c  
public ref class B : public System::Enum {};   // C3838  
```  
  
 次の例では警告 C3838 が生成されます。  
  
```  
// C3838b.cpp  
// compile with: /clr:oldSyntax /c  
public __gc class B : public System::ValueType {};   // C3838  
```