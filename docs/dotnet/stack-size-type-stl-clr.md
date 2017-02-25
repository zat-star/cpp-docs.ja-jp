---
title: "stack::size_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::stack::size_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size_type メンバー [STL/CLR]"
ms.assetid: 713ba8c5-41e5-422a-a334-cfeab16b4496
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# stack::size_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素間の符号付きな間隔の種類。  
  
## 構文  
  
```  
typedef int size_type;  
```  
  
## 解説  
 型は負の要素数を指定します。  
  
## 使用例  
  
```  
// cliext_stack_size_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// compute positive difference   
    Mystack::size_type diff = c1.size();   
    c1.pop();   
    c1.pop();   
    diff -= c1.size();   
    System::Console::WriteLine("size difference = {0}", diff);   
    return (0);   
    }  
  
```  
  
  **b c**  
**サイズの違い \= 2**   
## 必要条件  
 **ヘッダー:** \<cliext とスタック\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [スタック](../dotnet/stack-stl-clr.md)   
 [stack::empty](../dotnet/stack-empty-stl-clr.md)