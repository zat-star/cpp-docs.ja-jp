---
title: "vector::clear (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::clear"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "clear メンバー [STL/CLR]"
ms.assetid: 4ed20ec8-3089-4c36-b68f-1b51c639041f
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::clear (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべての要素を削除します。  
  
## 構文  
  
```  
void clear();  
```  
  
## 解説  
 メンバー関数は、実質的に [vector::erase](../dotnet/vector-erase-stl-clr.md)`(`[vector::begin](../dotnet/vector-begin-stl-clr.md)`(),`[vector::end](../dotnet/vector-end-stl-clr.md)`())`を呼び出します。  被制御シーケンスが空であることを確認するために使用します。  
  
## 使用例  
  
```  
// cliext_vector_clear.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// clear the container and reinspect   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// add elements and clear again   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    c1.clear();   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **b c**  
**size\(\) \= 0**  
 **b**  
**size\(\) \= 0**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [vector::erase](../dotnet/vector-erase-stl-clr.md)