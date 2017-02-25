---
title: "count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count 関数 [STL/CLR]"
ms.assetid: 6d10abb4-3c48-469c-804c-281015b12865
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値が指定された値と一致する範囲の要素数を返します。  
  
## 構文  
  
```  
template<class _InIt, class _Ty> inline  
    typename iterator_traits<_InIt>::difference_type  
        count(_InIt _First, _InIt _Last, const _Ty% _Val);  
```  
  
## 解説  
 この関数は、STL 関数 `count`も同じように動作します。  詳細については、「[count](../Topic/count.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)