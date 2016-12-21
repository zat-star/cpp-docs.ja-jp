---
title: "hash_set::size (STL/CLR) | Microsoft Docs"
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
  - "cliext::hash_set::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size メンバー [STL/CLR]"
ms.assetid: e006590e-8710-4294-b3a3-dcded0668a24
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# hash_set::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の数をカウントします。  
  
## 構文  
  
```  
size_type size();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの長さを返します。  被制御シーケンスの要素数を現在特定するときに使用します。  では、気遣うのシーケンスに 0 以外のなサイズかどうかのみ、[hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)`()`を参照してください。  
  
## 使用例  
  
```  
// cliext_hash_set_size.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0} after clearing", c1.size());   
  
// add elements and clear again   
    c1.insert(L'a');   
    c1.insert(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
  **b c**  
**size\(\) \= 3 から始まる 3**  
**size\(\) \= の削除後 0**  
**size\(\) \= 2 を追加すると 2**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::empty](../dotnet/hash-set-empty-stl-clr.md)