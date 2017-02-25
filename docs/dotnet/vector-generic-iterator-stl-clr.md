---
title: "vector::generic_iterator (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::generic_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "generic_iterator メンバー [STL/CLR]"
ms.assetid: e396bce6-5b1e-46b6-afa5-6bb96cf5d5d5
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# vector::generic_iterator (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナーのジェネリック インターフェイスで使用の反復子の型。  
  
## 構文  
  
```  
typedef Microsoft::VisualC::StlClr::Generic::  
    ContainerRandomAccessIterator<generic_value>  
    generic_iterator;  
```  
  
## 解説  
 この型は、テンプレートのコンテナー クラスにジェネリック インターフェイスで使用できるジェネリック反復子について説明します。  
  
## 使用例  
  
```  
// cliext_vector_generic_iterator.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct a generic container   
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;   
    for each (wchar_t elem in gc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// modify generic and display original   
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();   
    cliext::vector<wchar_t>::generic_value gcval = *gcit;   
    *++gcit = gcval;   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**  
 **C\+\+.**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [vector::generic\_container](../dotnet/vector-generic-container-stl-clr.md)   
 [vector::generic\_reverse\_iterator](../Topic/vector::generic_reverse_iterator%20\(STL-CLR\).md)