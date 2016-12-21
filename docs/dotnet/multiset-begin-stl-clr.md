---
title: "multiset::begin (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin メンバー [STL/CLR]"
ms.assetid: 592a6331-0de5-484a-9962-0beda7082589
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::begin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスの先頭を指定します。  
  
## 構文  
  
```  
iterator begin();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの最初の要素を指定するか、返します空のシーケンスの末尾を超えて双方向の反復子を返します。  これを使用して被制御シーケンスの現在の先頭 \(`current`\) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。  
  
## 使用例  
  
```  
// cliext_multiset_begin.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
    Mymultiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// inspect first two items   
    Mymultiset::iterator it = c1.begin();   
    System::Console::WriteLine("*begin() = {0}", *it);   
    System::Console::WriteLine("*++begin() = {0}", *++it);   
    return (0);   
    }  
  
```  
  
  **b c**  
**\*begin\(\) \= a**  
**\*\+\+begin\(\) \= b**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::end](../dotnet/multiset-end-stl-clr.md)