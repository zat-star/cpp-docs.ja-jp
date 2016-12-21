---
title: "generate_n (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::generate_n"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generate_n 関数 [STL/CLR]"
ms.assetid: 2f56e649-7a6f-4861-ae49-d0b25f5cd50c
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# generate_n (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した数の要素への関数オブジェクトによって生成される値が最後に割り当てられた値を超える位置 1 までの範囲と戻り割り当てます。  
  
## 構文  
  
```  
template<class _OutIt, class _Diff, class _Fn0> inline  
    void generate_n(_OutIt _Dest, _Diff _Count, _Fn0 _Func);  
```  
  
## 解説  
 この関数は、STL 関数 `generate_n`も同じように動作します。  詳細については、「[generate\_n](../Topic/generate_n.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)