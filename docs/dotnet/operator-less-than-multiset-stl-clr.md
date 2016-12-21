---
title: "operator&lt; (multiset) (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< メンバー [STL/CLR]"
ms.assetid: 48150cda-4f3e-4535-860c-89f622a7f0a8
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (multiset) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リストより小さい\) を比較します。  
  
## 構文  
  
```  
template<typename Key>  
    bool operator<(multiset<Key>% left,  
        multiset<Key>% right);  
```  
  
#### パラメーター  
 \[left\]  
 比較の左辺のコンテナー。  
  
 \[right\]  
 比較の右辺のコンテナー。  
  
## 解説  
 演算子関数は、`!(``right``[i] <``left``[i])` が当てはまります。また、`left``[i] <``right``[i]`最小位置 `i` の場合、true を返します。  それ以外の点では、2 種類のマルチセットが要素によって比較された要素の場合 `left` は `right` の前に並べるかをテストするときに使用する `left``->size() <``right``->size()` を返します。  
  
## 使用例  
  
```  
// cliext_multiset_operator_lt.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymultiset c2;   
    c2.insert(L'a');   
    c2.insert(L'b');   
    c2.insert(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b d**  
**b c \[\] \< \[\] b c false です。**  
**b \[\] \< \[\] b c d 当てはまります。**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\)%20\(STL-CLR\).md)   
 [operator\!\= \(multiset\)](../dotnet/operator-inequality-multiset-stl-clr.md)   
 [operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\)%20\(STL-CLR\).md)   
 [operator\> \(multiset\)](../dotnet/operator-greater-than-multiset-stl-clr.md)   
 [operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\)%20\(STL-CLR\).md)