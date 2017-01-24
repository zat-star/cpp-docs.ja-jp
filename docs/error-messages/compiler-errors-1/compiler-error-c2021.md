---
title: "コンパイラ エラー C2021 | Microsoft Docs"
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
  - "C2021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2021"
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'文字' でなく指数の値が必要です。  
  
 文字が浮動小数点定数の指数として使用されていますが、この文字は有効な数値ではありません。  有効範囲内の指数を使用してください。  
  
## 使用例  
 次の例では警告 C2021 が生成されます。  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## 使用例  
 解決方法 :  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```