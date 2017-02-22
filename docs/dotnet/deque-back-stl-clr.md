---
title: "deque::back (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::back"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back メンバー [STL/CLR]"
ms.assetid: 5608cdda-212d-42f6-866b-b04aec04ef8e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# deque::back (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

最後の要素にアクセスします。  
  
## 構文  
  
```  
reference back();  
```  
  
## 解説  
 メンバー関数は空でない必要があります。被制御シーケンスの最後の要素への参照を返します。  確認する場合は、最後の要素にアクセスするために使用していることを確認します。  
  
## 使用例  
  
```  
// cliext_deque_back.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect last item   
    System::Console::WriteLine("back() = {0}", c1.back());   
  
// alter last item and reinspect   
    c1.back() = L'x';   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**back\(\) \= c**  
 **b X**   
## 必要条件  
 **ヘッダー:** \<cliext\/deque\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::back\_item](../Topic/deque::back_item%20\(STL-CLR\).md)   
 [deque::front](../Topic/deque::front%20\(STL-CLR\).md)   
 [deque::front\_item](../dotnet/deque-front-item-stl-clr.md)