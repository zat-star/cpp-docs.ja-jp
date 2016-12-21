---
title: "コンパイラ エラー C2333 | Microsoft Docs"
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
  - "C2333"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2333"
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2333
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 関数宣言のエラーです。関数の本体は無視されます。  
  
 このエラーは、クラス内で定義されているメンバー関数に対して、別のエラーの発生後に発生します。  
  
 次の例では警告 C2333 が生成されます。  
  
```  
// C2333.cpp  
struct s1 {  
   s1(s1) {}   // C2333  
};  
```