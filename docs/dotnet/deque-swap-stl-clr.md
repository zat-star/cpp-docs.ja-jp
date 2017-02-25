---
title: "deque::swap (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap メンバー [STL/CLR]"
ms.assetid: 511e1aa8-3069-43f3-aa77-150f1de1e195
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# deque::swap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つのコンテナーのコンテンツを交換します。  
  
## 構文  
  
```  
void swap(deque<Value>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コンテンツの交換先のコンテナー。  
  
## 解説  
 このメンバー関数は、`*this` と `right` の間で被制御シーケンスを交換します。  この処理は定数時間で実行され、例外はスローしません。  2 個のコンテナーのコンテンツを交換する単純として使用します。  
  
## 使用例  
  
```  
// cliext_deque_swap.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct another container with repetition of values   
    cliext::deque<wchar_t> c2(5, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// swap and redisplay   
    c1.swap(c2);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **X x x x X**  
 **X x x x X**  
 **b c**   
## 必要条件  
 **ヘッダー:** \<cliext\/deque\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::assign](../dotnet/deque-assign-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)