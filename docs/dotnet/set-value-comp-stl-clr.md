---
title: "set::value_comp (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set::value_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_comp メンバー [STL/CLR]"
ms.assetid: 3b7e469d-ca73-415b-bd20-24968c51107c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# set::value_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素の値の順序のデリゲートをコピーします。  
  
## 構文  
  
```  
value_compare^ value_comp();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの並べ替えに使用されるごとにデリゲートを返します。  2 要素の値を比較するときに使用します。  
  
## 使用例  
  
```  
// cliext_set_value_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    Myset::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\(L'a、L'a\) \= false を比較します。**  
**\(L'a、L'b\) \= True を比較します。**  
**\(L'b、L'a\) \= false を比較します。**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [設定](../dotnet/set-stl-clr.md)   
 [set::value\_compare](../Topic/set::value_compare%20\(STL-CLR\).md)   
 [set::value\_type](../dotnet/set-value-type-stl-clr.md)