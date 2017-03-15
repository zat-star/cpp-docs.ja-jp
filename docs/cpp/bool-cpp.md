---
title: "bool (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bool_cpp"
  - "bool"
  - "__BOOL_DEFINED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__BOOL_DEFINED マクロ"
  - "bool キーワード [C++]"
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bool (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このキーワードは組み込みの型です。  この型の変数には、値 [true](../cpp/true-cpp.md) と [false](../Topic/false%20\(C++\).md) を設定できます。  条件式の型は `bool` であるため、その値は `bool` 型になります。  たとえば、`i!=0` は、`i` の値に応じて、**true** または **false** になります。  
  
 値 **true** と **false** には次のような関係があります。  
  
```  
!false == true  
!true == false  
```  
  
 次のステートメントがあるとします。  
  
```  
if (condexpr1) statement1;   
```  
  
 `condexpr1` が **true** の場合、`statement1` は常に実行されます。`condexpr1` が **false** の場合、`statement1` は実行されません。  
  
 後置または前置 `++` 演算子が `bool` 型の変数に適用されると、変数は **true** に設定されます。  後置または前置 `--` 演算子は、この型の変数には適用できません。  
  
 `bool` 型は整数の上位変換に使用されます。  `bool` 型の右辺値は `int` 型の右辺値に変換できます。**false** は 0 に、**true** は 1 になります。  別個の型として、`bool` はオーバーロードの解決に使用されます。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [基本型](../cpp/fundamental-types-cpp.md)