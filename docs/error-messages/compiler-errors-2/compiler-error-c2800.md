---
title: "コンパイラ エラー C2800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2800"
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator' : 関数はオーバーロードできません。  
  
 オーバーロードできない演算子は、クラス メンバーに対するアクセス演算子 \(`.`\)、ポインター メンバー演算子 \(`.*`\)、スコープ解決演算子 \(`::`\)、条件式演算子 \(`? :`\)、および `sizeof` 演算子です。  
  
 次の例では警告 C2800 が生成されます。  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```