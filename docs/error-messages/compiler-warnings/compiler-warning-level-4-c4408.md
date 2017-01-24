---
title: "コンパイラの警告 (レベル 4) C4408 | Microsoft Docs"
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
  - "C4408"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4408"
ms.assetid: 8488a186-ed1d-425c-aaeb-c72472c1da68
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4408
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

匿名構造体または匿名共用体にデータ メンバーの宣言がありません  
  
 匿名構造体または匿名共用体には、少なくとも 1 つのデータ メンバーが必要です。  
  
 次の例では C4408 が生成されます。  
  
```  
// C4408.cpp  
// compile with: /W4 /LD  
static union  
{  
   // int i;  
};  
// a named union can have no data members  
// } MyUnion;  
```