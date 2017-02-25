---
title: "priority_queue::generic_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::priority_queue::generic_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_value メンバー [STL/CLR]"
ms.assetid: d534e95b-7939-4fb4-bb71-2164e2b97c4f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# priority_queue::generic_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーのジェネリック インターフェイスで使用する要素の型。  
  
## 構文  
  
```  
typedef GValue generic_value;  
```  
  
## 解説  
 この型は、テンプレートのコンテナー クラスのジェネリック インターフェイスで使用するために格納された要素の値を記述する型 `GValue` オブジェクトを表します。\(`GValue` は `value_type` が ref 型の場合は `value_type` または `value_type^` です\)。  
  
## 使用例  
  
```  
// cliext_priority_queue_generic_value.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// get interface to container   
    Mypriority_queue::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1->get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display in priority order using generic_value   
    for (; !gc1->empty(); gc1->pop())   
        {   
        Mypriority_queue::generic_value elem = gc1->top();   
  
        System::Console::Write(" {0}", elem);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**  
 **a b c**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [priority\_queue::generic\_container](../dotnet/priority-queue-generic-container-stl-clr.md)   
 [priority\_queue::value\_type](../dotnet/priority-queue-value-type-stl-clr.md)