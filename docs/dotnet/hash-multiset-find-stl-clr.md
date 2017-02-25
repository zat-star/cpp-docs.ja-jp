---
title: "hash_multiset::find (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::find"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "find メンバー [STL/CLR]"
ms.assetid: fbedeb37-242e-4c2a-b1f8-234bcfd9cd25
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multiset::find (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したキーに一致する要素を検索します。  
  
## 構文  
  
```  
iterator find(key_type key);  
```  
  
#### パラメーター  
 key  
 検索するキー値。  
  
## 解説  
 被制御シーケンスの 1 個以上の要素に `key`と順序付け等価メンバー関数がある場合は、それらの要素の 1 を指定する反復子を返します。; それ以外の場合は [hash\_multiset::end](../dotnet/hash-multiset-end-stl-clr.md)`()`を返します。  指定したキーに一致する、被制御シーケンス内の要素を、現在の検索に使用されます。  
  
## 使用例  
  
```  
// cliext_hash_multiset_find.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("find {0} = {1}",   
        L'A', c1.find(L'A') != c1.end());   
    System::Console::WriteLine("find {0} = {1}",   
        L'b', *c1.find(L'b'));   
    System::Console::WriteLine("find {0} = {1}",   
        L'C', c1.find(L'C') != c1.end());   
    return (0);   
    }  
  
```  
  
  **b c**  
**A \= false を探します。**  
**b \= b 探します。**  
**C \= false を探します。**   
## 説明  
 要素が必要です。複数のいずれかを `find` が保証されないことに注意してください。  
  
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::equal\_range](../Topic/hash_multiset::equal_range%20\(STL-CLR\).md)   
 [hash\_multiset::lower\_bound](../Topic/hash_multiset::lower_bound%20\(STL-CLR\).md)   
 [hash\_multiset::upper\_bound](../dotnet/hash-multiset-upper-bound-stl-clr.md)