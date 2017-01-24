---
title: "vector::operator= (STL/CLR) | Microsoft Docs"
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
  - "cliext::vector::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= メンバー [STL/CLR]"
ms.assetid: c2de9d74-9de7-4560-866f-3d55952e9bd7
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# vector::operator= (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスを置き換えます。  
  
## 構文  
  
```  
vector<Value>% operator=(vector<Value>% right);  
```  
  
#### パラメーター  
 \[right\]  
 コピーするコンテナー。  
  
## 解説  
 このメンバー演算子は、オブジェクトに `right` を返します `*this`をコピーします。  これを使用して、被制御シーケンスを `right` の被制御シーケンスのコピーに置き換えることができます。  
  
## 使用例  
  
```  
// cliext_vector_operator_as.cpp   
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
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2 = c1;   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [vector::assign](../Topic/vector::assign%20\(STL-CLR\).md)