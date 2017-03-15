---
title: "operator!= (pair) (STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator!= メンバー [STL/CLR]"
ms.assetid: 167005f9-727d-40af-8d6d-2793d0daa96a
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator!= (pair) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

等価比較を組み合わせて使用します。  
  
## 構文  
  
```  
template<typename Value1,  
    typename Value2>  
    bool operator!=(pair<Value1, Value2>% left,  
        pair<Value1, Value2>% right);  
```  
  
#### パラメーター  
 \[left\]  
 比較の左辺のペア。  
  
 \[right\]  
 比較の右辺のペア。  
  
## 解説  
 演算子関数の戻り値 `!(``left``==``right``)`。  2 組のかっこが要素によって比較された要素の場合 `left` が `right` と同じ順序されていないかどうかをテストするときに使用します。  
  
## 使用例  
  
```  
// cliext_pair_operator_ne.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    cliext::pair<wchar_t, int> c2(L'x', 4);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
    System::Console::WriteLine("[x 3] != [x 3] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[x 3] != [x 4] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
  **\[X、3 つ\]**  
**\[X、4 つ\]**  
**\[\]\! x 3\= x 3 \[\] false です。**  
**\[\]\! x 3\= x 4 \[\]当てはまります。**   
## 必要条件  
 **ヘッダー:** \<cliext\/ユーティリティ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [pair](../dotnet/pair-stl-clr.md)   
 [operator\=\= \(pair\)](../dotnet/operator-equality-pair-stl-clr.md)   
 [operator\< \(pair\)](../dotnet/operator-less-than-pair-stl-clr.md)   
 [operator\>\= \(pair\)](../dotnet/operator-greater-or-equal-pair-stl-clr.md)   
 [operator\> \(pair\)](../dotnet/operator-greater-than-pair-stl-clr.md)   
 [operator\<\= \(pair\)](../dotnet/operator-less-or-equal-pair-stl-clr.md)