---
title: "list::front_item (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::front_item"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "front_item メンバー [STL/CLR]"
ms.assetid: c871873b-7745-442b-9760-9d8096fa8610
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::front_item (STL/CLR)
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
// cliext_list_front_item.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first item   
    System::Console::WriteLine("front_item = {0}", c1.front_item);   
  
// alter first item and reinspect   
    c1.front_item = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**front\_item \= a**  
 **X b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::back](../dotnet/list-back-stl-clr.md)   
 [list::back\_item](../Topic/list::back_item%20\(STL-CLR\).md)   
 [list::front](../dotnet/list-front-stl-clr.md)