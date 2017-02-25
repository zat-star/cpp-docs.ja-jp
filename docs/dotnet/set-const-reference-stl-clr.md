---
title: "set::const_reference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::const_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_reference メンバー [STL/CLR]"
ms.assetid: 25326f25-b4d3-4a92-950a-a843cdff7486
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# set::const_reference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素への定数参照の型です。  
  
## 構文  
  
```  
typedef value_type% const_reference;  
```  
  
## 解説  
 型は要素への定数参照について説明します。  
  
## 使用例  
  
```  
// cliext_set_const_reference.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    Myset::const_iterator cit = c1.begin();   
    for (; cit != c1.end(); ++cit)   
        {   // get a const reference to an element   
        Myset::const_reference cref = *cit;   
        System::Console::Write(" {0}", cref);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [設定](../dotnet/set-stl-clr.md)   
 [set::reference](../dotnet/set-reference-stl-clr.md)   
 [set::value\_type](../dotnet/set-value-type-stl-clr.md)