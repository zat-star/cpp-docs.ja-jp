---
title: "hash_set::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase メンバー [STL/CLR]"
ms.assetid: 620998a0-00c9-4be6-899b-2d71661375b6
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_set::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した位置にある要素を削除します。  
  
## 構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
bool erase(key_type key)  
```  
  
#### パラメーター  
 最初  
 消去する範囲の先頭。  
  
 key  
 消去するキー値。  
  
 last  
 消去する範囲の最後。  
  
 where  
 消去する要素。  
  
## 解説  
 一つ目のメンバー関数は、そのような要素が存在しない場合 `where`が指す被制御シーケンスの要素を削除し、削除した要素を後に残った一つ目の要素を指定する場合は [hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()` 反復子を返します。  単一の要素を削除する場合に使用します。  
  
 2 つ目のメンバー関数は、そのような要素が存在しない場合 `[`範囲`first``,``last``)`の被制御シーケンスの要素を削除し、要素を削除した後に残った一つ目の要素を指定する `end()` または反復子を返します。  使用するゼロ以上の連続する要素を削除するには、それを。  
  
 3 つ目のメンバー関数は、キーに `key`に並べる等価を削除し、削除した要素の数を返します。被制御シーケンスの要素を紹介します。  指定したキーに一致するすべての要素を削除し、count の場合に使用します。  
  
 各要素の削除は、被制御シーケンス内の要素数に比例する対数に時間がかかります。  
  
## 使用例  
  
```  
// cliext_hash_set_erase.cpp   
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
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.insert(L'd');   
    c1.insert(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    Myhash_set::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **b c**  
**erase\(begin\(\)\= b\)**   
 **b c d e**  
**erase\(begin\(\)、end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::clear](../dotnet/hash-set-clear-stl-clr.md)