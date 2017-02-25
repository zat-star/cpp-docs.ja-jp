---
title: "list::push_back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::push_back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "push_back メンバー [STL/CLR]"
ms.assetid: f2c70470-a899-4e5f-8f3e-b55d6a8bff0e
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# list::push_back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しい最後の要素を追加します。  
  
## 構文  
  
```  
void push_back(value_type val);  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの末尾に値 `val` 要素を挿入します。  リストに他の要素を付けるために使用します。  
  
## 使用例  
  
```  
// cliext_list_push_back.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::pop\_back](../dotnet/list-pop-back-stl-clr.md)   
 [list::pop\_front](../dotnet/list-pop-front-stl-clr.md)   
 [list::push\_front](../Topic/list::push_front%20\(STL-CLR\).md)