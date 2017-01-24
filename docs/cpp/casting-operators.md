---
title: "キャスト演算子 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "キャスト演算子"
  - "演算子 [C++], キャスト"
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# キャスト演算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 言語には、固有のキャスト演算子がいくつかあります。  これらの演算子は、以前のスタイルの C 言語のキャストが持つあいまいさと危険性の一部を取り除くことを目的としています。  このような演算子を次に示します。  
  
-   [dynamic\_cast](../cpp/dynamic-cast-operator.md) ポリモーフィックな型の変換に使用します。  
  
-   [static\_cast](../cpp/static-cast-operator.md) 非ポリモーフィックな型の変換に使用します。  
  
-   [const\_cast](../Topic/const_cast%20Operator.md) `const`、`volatile`、および `__unaligned` 属性を削除するために使用します。  
  
-   [reinterpret\_cast](../cpp/reinterpret-cast-operator.md) ビットの単純な再解釈に使用します。  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md) 検証可能な MSIL を生成するために使用します。  
  
 `const_cast` と `reinterpret_cast` には以前の形式と同じ危険性があるため、これらの演算子は最後の手段として使用してください。  それでも、これらは、以前のスタイルのキャストを完全に置き換えるために必要です。  
  
## 参照  
 [キャスト](../cpp/casting.md)