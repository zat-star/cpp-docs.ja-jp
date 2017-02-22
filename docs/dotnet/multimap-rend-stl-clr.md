---
title: "multimap::rend (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::rend"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rend メンバー [STL/CLR]"
ms.assetid: f8d3f683-eeab-4a8b-af3f-fb6653114594
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# multimap::rend (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反転被制御シーケンスの末尾を指定します。  
  
## 構文  
  
```  
reverse_iterator rend();  
```  
  
## 解説  
 このメンバー関数は、反転反復子を被制御シーケンスの先頭を指し示す前方反復子を返します。  したがって、これは反転シーケンスの `end` を指定します。  これを使用して被制御シーケンスの逆順に見た現在の末尾 \(`current`\) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。  
  
## 使用例  
  
```  
// cliext_multimap_rend.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// inspect first two items in reversed sequence   
    Mymultimap::reverse_iterator rit = c1.rend();   
    --rit;   
    --rit;   
    System::Console::WriteLine("*-- --rend() = [{0} {1}]",   
        rit->first, rit->second);   
    ++rit;   
    System::Console::WriteLine("*--rend() = [{0} {1}]",   
        rit->first, rit->second);   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**\*。\-\-rend\(\) \= \[b 2\]**  
**\*\-\-rend\(\) \= \[1\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::begin](../dotnet/multimap-begin-stl-clr.md)   
 [multimap::end](../dotnet/multimap-end-stl-clr.md)   
 [multimap::rbegin](../dotnet/multimap-rbegin-stl-clr.md)