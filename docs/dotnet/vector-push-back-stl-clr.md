---
title: "vector::push_back (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::push_back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push_back メンバー [STL/CLR]"
ms.assetid: 4a4c302b-e29f-4b68-b759-2f831814d896
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::push_back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しい最後の要素を追加します。  
  
## 構文  
  
```  
void push_back(value_type val);  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの末尾に値 `val` 要素を挿入します。  ベクターに他の要素を付けるために使用します。  
  
## 使用例  
  
```  
// cliext_vector_push_back.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [vector::pop\_back](../Topic/vector::pop_back%20\(STL-CLR\).md)