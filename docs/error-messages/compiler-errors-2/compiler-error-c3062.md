---
title: "コンパイラ エラー C3062 | Microsoft Docs"
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
  - "C3062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3062"
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum': 基になる型が '型' であるため、列挙子には値が必要です  
  
 列挙型の基になる型を指定できます。  ただし一部の型では、各列挙型に値を代入する必要があります。  
  
 列挙型の詳細については、「[enum クラス](../../windows/enum-class-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3062 が生成されます。  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```