---
title: "hash_set::count (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::count"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "count メンバー [STL/CLR]"
ms.assetid: 99dbaef5-64fd-4bef-bac4-a6072dd231f1
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# hash_set::count (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したキーに一致する要素の数を検索します。  
  
## 構文  
  
```  
size_type count(key_type key);  
```  
  
#### パラメーター  
 key  
 検索するキー値。  
  
## 解説  
 このメンバー関数は `key`と順序付け等価である、被制御シーケンス内の要素数を返します。  被制御シーケンス内の指定したキーに一致する現在の要素の数を確認する場合に、これを使用します。  
  
## 使用例  
  
```  
// cliext_hash_set_count.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));   
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));   
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));   
    return (0);   
    }  
  
```  
  
  **b c**  
**数値 \(L'A\) \= 0**  
**数値 \(L'b\) \= 1**  
**数値 \(L'C\) \= 0**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)