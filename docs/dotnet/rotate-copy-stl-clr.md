---
title: "rotate_copy (STL/CLR) | Microsoft Docs"
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
  - "cliext::rotate_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rotate_copy 関数 [STL/CLR]"
ms.assetid: ed697552-130f-474f-9ab6-133332bb2587
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# rotate_copy (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照元の範囲内の 2 種類の隣接する span 要素を交換し、割り当て先範囲に結果をコピーします。  
  
## 構文  
  
```  
template<class _FwdIt, class _OutIt> inline  
    _OutIt rotate_copy(_FwdIt _First, _FwdIt _Mid, _FwdIt _Last,  
        _OutIt _Dest);  
```  
  
## 解説  
 この関数は、STL 関数 `rotate_copy`も同じように動作します。  詳細については、「[rotate\_copy](../Topic/rotate_copy.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/アルゴリズム\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)