---
title: "コンパイラ エラー C2208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2208"
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラ エラー C2208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : メンバーのない列挙型、構造体、共用体が定義されました。  
  
 型名に解決する識別子は集約宣言にありますが、コンパイラがメンバーを宣言できません。  
  
 次の例では警告 C2208 が生成されます。  
  
```  
// C2208.cpp  
class C {  
   C;   // C2208  
   C(){}   // OK  
};  
```