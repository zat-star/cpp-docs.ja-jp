---
title: "関数呼び出し (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "関数呼び出し"
  - "関数呼び出し, C 関数"
  - "関数 [C], 呼び出し"
ms.assetid: 35c66719-3f15-4d3b-97da-4e19dc97b308
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 関数呼び出し (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

"関数呼び出し" は、呼び出される関数の名前または関数ポインターの値、および、関数に渡される省略可能な引数の値を含む式です。  
  
## 構文  
 *postfix\-expression*:  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *argument\-expression\-list*:  
 *assignment\-expression*  
  
 *argument\-expression\-list*  **,**  *assignment\-expression*  
  
 *postfix\-expression* は、関数アドレス \(たとえば、関数の識別子または関数ポインターの値\) に評価される必要があります。*argument\-expression\-list* は、式の \(コンマ区切りの\) リストで、各式の値 \(引数\) が関数に渡されます。  *argument\-expression\-list* 引数は空の場合もあります。  
  
 関数呼び出しの式は、関数の戻り値の値と型を持ちます。  関数は配列型のオブジェクトを返すことができません。  関数の戻り値の型が `void` \(つまり、値を返さない関数であると宣言されている\) の場合、関数呼び出し式も `void` 型になります  \(詳細については、「[関数呼び出し](../c-language/function-calls.md)」を参照してください\)。  
  
## 参照  
 [関数呼び出し演算子: \(\)](../cpp/function-call-operator-parens.md)