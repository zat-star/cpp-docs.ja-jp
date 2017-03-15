---
title: "queue::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::queue::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size メンバー [STL/CLR]"
ms.assetid: 864510ef-5a00-4377-b286-1e73f237e359
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# queue::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の数をカウントします。  
  
## 構文  
  
```  
size_type size();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの長さを返します。  被制御シーケンスの要素数を現在特定するときに使用します。  では、気遣うのシーケンスに 0 以外のなサイズかどうかのみ、[queue::empty](../Topic/queue::empty%20\(STL-CLR\).md)`()`を参照してください。  
  
## 使用例  
  
```  
// cliext_queue_size.cpp   
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
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **b c**  
**size\(\) \= 3 から始まる 3**  
**size\(\) \= ポップ後の 2**  
**size\(\) \= 2 を追加すると 4**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [queue::empty](../Topic/queue::empty%20\(STL-CLR\).md)