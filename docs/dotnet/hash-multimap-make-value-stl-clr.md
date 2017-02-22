---
title: "hash_multimap::make_value (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::make_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_value メンバー [STL/CLR]"
ms.assetid: 300fb6ec-98c8-48d5-8626-0646878a8462
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multimap::make_value (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値オブジェクトを構築します。  
  
## 構文  
  
```  
static value_type make_value(key_type key, mapped_type mapped);  
```  
  
#### パラメーター  
 key  
 使用するキー値。  
  
 マップされた  
 検索するマップされたな値。  
  
## 解説  
 このメンバー関数は、キーが `key` であり、マップされたな値が `mapped`である `value_type` オブジェクトを返します。  他のメンバー関数の使用に適したオブジェクトを構成するために使用します。  
  
## 使用例  
  
```  
// cliext_hash_multimap_make_value.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::key\_type](../dotnet/hash-multimap-key-type-stl-clr.md)   
 [hash\_multimap::mapped\_type](../Topic/hash_multimap::mapped_type%20\(STL-CLR\).md)   
 [hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)