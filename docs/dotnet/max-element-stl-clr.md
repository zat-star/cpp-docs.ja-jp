---
title: "max_element (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::max_element"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_element 関数 [STL/CLR]"
ms.assetid: c6274bae-1216-4285-b395-254280253dae
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# max_element (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

並べ替え基準をバイナリ述語で指定できる、指定された範囲内の最大の要素の最初の出現箇所を検索します。  
  
## 構文  
  
```  
template<class _FwdIt> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last);  
template<class _FwdIt, class _Pr> inline  
    _FwdIt max_element(_FwdIt _First, _FwdIt _Last, _Pr _Pred);  
```  
  
## 解説  
 この関数は、STL 関数 `max_element`も同じように動作します。  詳細については、「[max\_element](../Topic/max_element.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)