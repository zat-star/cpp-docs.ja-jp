---
title: "set::size (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "size メンバー [STL/CLR]"
ms.assetid: f231c515-b07e-4e18-90fd-535b13c2db70
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# set::size (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の数をカウントします。  
  
## 構文  
  
```  
size_type size();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの長さを返します。  被制御シーケンスの要素数を現在特定するときに使用します。  では、気遣うのシーケンスに 0 以外のなサイズかどうかのみ、[set::empty](../dotnet/set-empty-stl-clr.md)`()`を参照してください。  
  
## 使用例  
  
```  
// cliext_set_size.cpp   
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
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [設定](../dotnet/set-stl-clr.md)   
 [set::empty](../dotnet/set-empty-stl-clr.md)