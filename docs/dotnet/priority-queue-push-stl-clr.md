---
title: "priority_queue::push (STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue::push"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push メンバー [STL/CLR]"
ms.assetid: 317d3feb-0688-4658-866b-a26cae060354
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::push (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しい要素を追加します。  
  
## 構文  
  
```  
void push(value_type val);  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの値 `val` 要素を挿入し、ヒープの作業分野を維持するために、被制御シーケンスの順序を変更します。  キューに他の要素を追加する場合に使用します。  
  
## 使用例  
  
```  
// cliext_priority_queue_push.cpp   
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
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [priority\_queue::pop](../dotnet/priority-queue-pop-stl-clr.md)