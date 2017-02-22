---
title: "multimap::to_array (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::to_array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "to_array メンバー [STL/CLR]"
ms.assetid: eb4872dd-5e32-4a82-8ad4-37b533eb6814
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multimap::to_array (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しい配列に被制御シーケンスをコピーします。  
  
## 構文  
  
```  
cli::array<value_type>^ to_array();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスを格納した配列を返します。  配列のフォームの被制御シーケンスのコピーを取得するために使用します。  
  
## 使用例  
  
```  
// cliext_multimap_to_array.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// copy the container and modify it   
    cli::array<Mymultimap::value_type>^ a1 = c1.to_array();   
  
    c1.insert(Mymultimap::make_value(L'd', 4));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// display the earlier array copy   
    for each (Mymultimap::value_type elem in a1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[\] \[2 b c 3 \[\]d 4\]**  
 **1 \[\] \[b 2 \[\]c 3\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)