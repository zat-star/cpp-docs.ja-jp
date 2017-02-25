---
title: "queue::front_item (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::front_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_item メンバー [STL/CLR]"
ms.assetid: 389ab030-4351-48e6-9b03-417f1d3fcb86
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# queue::front_item (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最初の要素にアクセスします。  
  
## 構文  
  
```  
property value_type front_item;  
```  
  
## 解説  
 プロパティ アクセス空でない必要があります。被制御シーケンスの最初の要素。  これがわかっている場合に読み込むために使用します。または、最初の要素を作成することはありません。  
  
## 使用例  
  
```  
// cliext_queue_front_item.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter last item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**front\_item \= a**  
 **X b c**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [queue::back](../dotnet/queue-back-stl-clr.md)   
 [queue::back\_item](../dotnet/queue-back-item-stl-clr.md)   
 [queue::front](../Topic/queue::front%20\(STL-CLR\).md)   
 [queue::front](../Topic/queue::front%20\(STL-CLR\).md)