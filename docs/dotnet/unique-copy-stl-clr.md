---
title: "unique_copy (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::unique_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_copy 関数 [STL/CLR]"
ms.assetid: 37aa5b06-42c5-420d-94c5-00f00ad26471
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# unique_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

互いに隣接する重複する要素を除く先の範囲にソース範囲内の要素をコピーします。  
  
## 構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Pr> inline  
    _OutIt unique_copy(_InIt _First, _InIt _Last, _OutIt _Dest,  
        _Pr _Pred);  
```  
  
## 解説  
 この関数は、STL 関数 `unique_copy`も同じように動作します。  詳細については、「[unique\_copy](../Topic/unique_copy.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)