---
title: "multiset::rbegin (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::rbegin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rbegin メンバー [STL/CLR]"
ms.assetid: beec0024-9565-4809-86f9-8b2c4e533923
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::rbegin (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反転被制御シーケンスの先頭を指定します。  
  
## 構文  
  
```  
reverse_iterator rbegin();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの最後の要素を指定するか、返します空のシーケンスの先頭を指し示す反転反復子を返します。  したがって、これは反転シーケンスの `beginning` を指定します。  これを使用して被制御シーケンスの逆順に見た現在の \(`current`\) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。  
  
## 使用例  
  
```  
// cliext_multiset_rbegin.cpp   
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
  
// inspect first two items in reversed sequence   
    Mymultiset::reverse_iterator rit = c1.rbegin();   
    System::Console::WriteLine("*rbegin() = {0}", *rit);   
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);   
    return (0);   
    }  
  
```  
  
  **b c**  
**\*rbegin\(\) \= c**  
**\*\+\+rbegin\(\) \= b**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::begin](../dotnet/multiset-begin-stl-clr.md)   
 [multiset::end](../dotnet/multiset-end-stl-clr.md)   
 [multiset::rend](../Topic/multiset::rend%20\(STL-CLR\).md)