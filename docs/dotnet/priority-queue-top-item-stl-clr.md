---
title: "priority_queue::top_item (STL/CLR) | Microsoft Docs"
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
  - "cliext::priority_queue::top_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "top_item メンバー [STL/CLR]"
ms.assetid: d497403b-6b1d-4c6e-a0f4-c744cc5fad75
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# priority_queue::top_item (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

優先順位の要素にアクセスします。  
  
## 構文  
  
```  
property value_type back_item;  
```  
  
## 解説  
 プロパティ アクセス空でない必要があります。被制御シーケンスの先頭 \(優先順位の\) 要素。  これがわかっている場合に読み込むために使用します。または、優先度の高い要素を作成することはありません。  
  
## 使用例  
  
```  
// cliext_priority_queue_top_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("top_item = {0}", c1.top_item);   
  
// alter last item and reinspect   
    c1.top_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**top\_item \= c**  
 **X b**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [priority\_queue](../Topic/priority_queue%20\(STL-CLR\).md)   
 [priority\_queue::top](../Topic/priority_queue::top%20\(STL-CLR\).md)