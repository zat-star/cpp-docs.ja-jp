---
title: "inplace_merge (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::inplace_merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "inplace_merge 関数 [STL/CLR]"
ms.assetid: e6948c03-8c5b-4a7c-915c-0a531946a321
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# inplace_merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

並べ替えの条件が二項述語で指定できる単一の並べ替えられた範囲の 2 個の連続する並べ替えられた範囲の要素を連結します。  
  
## 構文  
  
```  
template<class _BidIt> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last);  
template<class _BidIt, class _Pr> inline  
    void inplace_merge(_BidIt _First, _BidIt _Mid, _BidIt _Last,  
        _Pr _Pred);  
```  
  
## 解説  
 この関数は、STL の関数の `inplace_merge` の詳細についてが、[inplace\_merge](../Topic/inplace_merge.md)に参照するものとして動作します。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)