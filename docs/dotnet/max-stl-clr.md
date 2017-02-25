---
title: "max (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::max"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max 関数 [STL/CLR]"
ms.assetid: bf51aedc-b7a0-4b6c-a76e-fdbc4af042fa
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# max (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのオブジェクトを比較し、大きい方のオブジェクトを返します。順序の基準は、二項述語によって指定できます。  
  
## 構文  
  
```  
template<class _Ty> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right);  
template<class _Ty, class _Pr> inline  
    const _Ty max(const _Ty% _Left, const _Ty% _Right, _Pr _Pred);  
```  
  
## 解説  
 この関数は、STL 関数 `max`も同じように動作します。  詳細については、「[max](../Topic/max.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)