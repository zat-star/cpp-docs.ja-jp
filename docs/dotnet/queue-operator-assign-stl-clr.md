---
title: "queue::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::queue::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= メンバー [STL/CLR]"
ms.assetid: 826c335a-5680-498c-b57d-e7bc93a914be
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# queue::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスを置き換えます。  
  
## 構文  
  
```  
queue <Value, Container>% operator=(queue <Value, Container>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コピーするコンテナーのアダプター。  
  
## 解説  
 このメンバー演算子は、オブジェクトに `right` を返します `*this`をコピーします。  これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーに置き換えることができます。  
  
## 使用例  
  
```  
// cliext_queue_operator_as.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::queue<wchar_t> Myqueue;   
int main()   
    {   
    Myqueue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Myqueue c2;   
    c2 = c1;   
    for each (wchar_t elem in c2.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** \<cliext とキュー\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [キュー](../Topic/queue%20\(STL-CLR\).md)   
 [queue::assign](../dotnet/queue-assign-stl-clr.md)