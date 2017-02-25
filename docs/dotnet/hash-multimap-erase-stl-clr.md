---
title: "hash_multimap::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase メンバー [STL/CLR]"
ms.assetid: 663c67f6-8070-47db-abdc-58f7ace69736
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_multimap::erase (STL/CLR)
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
 一つ目のメンバー関数は、そのような要素が存在しない場合 `where`が指す被制御シーケンスの要素を削除し、削除した要素を後に残った一つ目の要素を指定する場合は [hash\_multimap::end](../dotnet/hash-multimap-end-stl-clr.md)`()` 反復子を返します。  単一の要素を削除する場合に使用します。  
  
 2 つ目のメンバー関数は、そのような要素が存在しない場合 `[`範囲`first``,``last``)`の被制御シーケンスの要素を削除し、要素を削除した後に残った一つ目の要素を指定する `end()` または反復子を返します。  使用するゼロ以上の連続する要素を削除するには、それを。  
  
 3 つ目のメンバー関数は、キーに `key`に並べる等価を削除し、削除した要素の数を返します。被制御シーケンスの要素を紹介します。  指定したキーに一致するすべての要素を削除し、count の場合に使用します。  
  
 各要素の削除は、被制御シーケンス内の要素数に比例する対数に時間がかかります。  
  
## 使用例  
  
```  
// cliext_hash_multimap_erase.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    cliext::hash_multimap<wchar_t, int> c1;   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'a', 1));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'b', 2));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    cliext::hash_multimap<wchar_t, int>::iterator it =   
        c1.erase(c1.begin());   
    System::Console::WriteLine("erase(begin()) = [{0} {1}]",   
        it->first, it->second);   
  
// add elements and display " b c d e"   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'd', 4));   
    c1.insert(cliext::hash_multimap<wchar_t, int>::make_value(L'e', 5));   
    for each (cliext::hash_multimap<wchar_t, int>::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// erase all but end   
    it = c1.end();   
    it = c1.erase(c1.begin(), --it);   
    System::Console::WriteLine("erase(begin(), end()-1) = [{0} {1}]",   
        it->first, it->second);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// erase end   
    System::Console::WriteLine("erase(L'x') = {0}", c1.erase(L'x'));   
    System::Console::WriteLine("erase(L'e') = {0}", c1.erase(L'e'));   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**erase\(begin\(\)\) \= \[b 2\]**  
 **\[\] \[3 2 b c d 4 \[\] \[\]e 5\]**  
**erase\(begin\(\)、end\(\)\-1\) \= \[e 5\]**  
**size\(\) \= 1**  
**erase \(L'x\) \= 0**  
**erase \(L'e\) \= 1**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::clear](../dotnet/hash-multimap-clear-stl-clr.md)