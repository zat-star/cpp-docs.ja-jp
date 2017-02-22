---
title: "コンパイラ エラー C2461 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2461"
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : コンストラクターに、仮パラメーターが指定されていません。  
  
 クラスのコンストラクターでは、仮パラメーターが指定されていません。  コンストラクターの宣言には、仮パラメーターを指定する必要があります。リストは空でもかまいません。  
  
 `class` `::` `class` の後ろに一組のかっこを付けてください。  
  
 次の例では警告 C2461 が生成されます。  
  
```  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;   // C2461  
   C::C();   // OK  
};  
```