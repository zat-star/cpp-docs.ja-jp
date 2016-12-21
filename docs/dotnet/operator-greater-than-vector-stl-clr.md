---
title: "operator&gt; (vector) (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator> メンバー [STL/CLR]"
ms.assetid: c9c55c3f-5e82-4504-90e3-708dab7aa660
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&gt; (vector) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

比較より大きいベクター。  
  
## 構文  
  
```  
template<typename Value>  
    bool operator>(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### パラメーター  
 \[left\]  
 比較の左辺のコンテナー。  
  
 \[right\]  
 比較の右辺のコンテナー。  
  
## 解説  
 演算子関数の戻り値 `right``<``left`。  2 個のベクターが要素によって比較された要素の場合 `left` が `right` の後に並べるかをテストするときに使用します。  
  
## 使用例  
  
```  
// cliext_vector_operator_gt.cpp   
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
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] > [a b c] is {0}",   
        c1 > c1);   
    System::Console::WriteLine("[a b d] > [a b c] is {0}",   
        c2 > c1);   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b d**  
**b c \[\] \> \[\] b c false です。**  
**\[\] \> b c d b \[\]当てはまります。**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)   
 [operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\< \(vector\)](../dotnet/operator-less-than-vector-stl-clr.md)   
 [operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)