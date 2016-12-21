---
title: "multiset::equal_range (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::equal_range"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "equal_range メンバー [STL/CLR]"
ms.assetid: 0fa617fb-8316-4310-b906-0322fa04aebe
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::equal_range (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したキーに一致する範囲を検索します。  
  
## 構文  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### パラメーター  
 key  
 検索するキー値。  
  
## 解説  
 このメンバー関数は、反復子 `cliext::pair<iterator, iterator>(`[multiset::lower\_bound](../Topic/multiset::lower_bound%20\(STL-CLR\).md)`(``key``),`[multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)`(``key``))`のペアを返します。  指定したキーに一致する、被制御シーケンス内の要素の範囲を現在特定するときに使用します。  
  
## 使用例  
  
```  
// cliext_multiset_equal_range.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
typedef Mymultiset::pair_iter_iter Pairii;   
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
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**equal\_range \(L'x\) は空けましたり \= True を**  
 **b**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::count](../dotnet/multiset-count-stl-clr.md)   
 [multiset::find](../Topic/multiset::find%20\(STL-CLR\).md)   
 [multiset::lower\_bound](../Topic/multiset::lower_bound%20\(STL-CLR\).md)   
 [multiset::upper\_bound](../dotnet/multiset-upper-bound-stl-clr.md)