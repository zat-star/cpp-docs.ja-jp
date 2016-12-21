---
title: "hash_map::value_compare (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_map::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare メンバー [STL/CLR]"
ms.assetid: a137d23f-0dd0-4858-ad5e-74782d85bf59
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_map::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素の値の順序のデリゲート。  
  
## 構文  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## 解説  
 型は値の引数の順序を決定するデリゲートのシノニムです。  
  
## 使用例  
  
```  
// cliext_hash_map_value_compare.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_map;   
int main()   
    {   
    Myhash_map c1;   
    Myhash_map::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Myhash_map::make_value(L'a', 1),   
            Myhash_map::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Myhash_map::make_value(L'a', 1),   
            Myhash_map::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Myhash_map::make_value(L'b', 2),   
            Myhash_map::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\(\[\] L'a、1、1、L'a \[\]\) \= True を比較します。**  
**\(\[\] L'a、1、2、L'b \[\]\) \= True を比較します。**  
**\(\[\] L'b、2、1、L'a \[\]\) \= false を比較します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_map](../dotnet/hash-map-stl-clr.md)   
 [hash\_map::key\_compare](../Topic/hash_map::key_compare%20\(STL-CLR\).md)   
 [hash\_map::value\_comp](../dotnet/hash-map-value-comp-stl-clr.md)   
 [hash\_map::value\_type](../dotnet/hash-map-value-type-stl-clr.md)