---
title: "pair::first (STL/CLR) | Microsoft Docs"
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
  - "cliext::pair::first"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "first メンバー [STL/CLR]"
ms.assetid: 0dd2278f-adf9-46df-8ac8-7e8e1a2ef52e
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# pair::first (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最初のラップされた値。  
  
## 構文  
  
```  
Value1 first;  
```  
  
## 解説  
 最初のオブジェクトは、ラップされた値を格納します。  
  
## 使用例  
  
```  
// cliext_pair_first.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    cliext::pair<wchar_t, int>::first_type first_val = c1.first;   
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;   
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);   
    return (0);   
    }  
  
```  
  
  **\[X、3 つ\]**   
## 必要条件  
 **ヘッダー:** \<cliext\/ユーティリティ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [pair](../dotnet/pair-stl-clr.md)   
 [pair::first\_type](../dotnet/pair-first-type-stl-clr.md)   
 [pair::second](../dotnet/pair-second-stl-clr.md)   
 [pair::second\_type](../dotnet/pair-second-type-stl-clr.md)