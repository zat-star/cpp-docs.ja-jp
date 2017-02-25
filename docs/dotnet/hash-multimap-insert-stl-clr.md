---
title: "hash_multimap::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert メンバー [STL/CLR]"
ms.assetid: 51cd98b0-c959-4a44-b914-582c00681bd7
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_multimap::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素を追加します。  
  
## 構文  
  
```  
iterator insert(value_type val);  
iterator insert(iterator where, value_type val);  
template<typename InIter>  
    void insert(InIter first, InIter last);  
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);  
```  
  
#### パラメーター  
 最初  
 挿入する範囲の先頭。  
  
 last  
 挿入する範囲の最後。  
  
 \[right\]  
 挿入する列挙体。  
  
 val  
 挿入するキー値。  
  
 where  
 コンテナー内の挿入位置 \(ヒントのみ\)。  
  
## 解説  
 メンバー関数は残りのオペランドで指定されたシーケンスを挿入します。  
  
 一つ目のメンバー関数は、値 `val`要素を挿入し、新しく挿入される要素を指定する反復子を返します。  単一の要素を挿入する場合に使用します。  
  
 2 つ目のメンバー関数は、ヒントとして `where` を使用して値 `val`要素 \(パフォーマンスを向上させるため\)、戻り値が新しく挿入される要素を指定する反復子を挿入します。  ユーザーがわかっている要素の横にある可能性のある単一の要素を挿入する場合に使用します。  
  
 3 つ目のメンバー関数は、シーケンス `[``first``,``last``)`を挿入します。  別のシーケンスからコピーしたゼロ使用します。または、より多くの要素を挿入するために。  
  
 4 つ目のメンバー関数は `right`で指定されたシーケンスを挿入します。  列挙子によって指定されたシーケンスを挿入する場合に使用します。  
  
 各要素の挿入は、被制御シーケンス内の要素数に比例する対数に時間がかかります。  ただし、挿入はカーソルに隣接する要素を指定するヒントを持つ償却された定数時間で実行できます。  
  
## 使用例  
  
```  
// cliext_hash_multimap_insert.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_multimap<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    c1.insert(Myhash_multimap::make_value(L'a', 1));   
    c1.insert(Myhash_multimap::make_value(L'b', 2));   
    c1.insert(Myhash_multimap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
    Myhash_multimap::iterator it =   
        c1.insert(Myhash_multimap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [{0} {1}]",   
        it->first, it->second);   
  
    it = c1.insert(Myhash_multimap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [{0} {1}]",   
        it->first, it->second);   
  
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    it = c1.insert(c1.begin(), Myhash_multimap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Myhash_multimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_multimap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Myhash_multimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_multimap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Myhash_multimap::value_type>^)%c1);   
    for each (Myhash_multimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**挿入 \(\[L'x 24 \= \[\]\) x 24\]**  
**挿入 \(\[L'b 2 \= \[\]\) b 2\]**  
 **1 \[\] \[b 2\] \[\] \[2 b c 3 \[\]x 24\]**  
**insert\(begin\(\)、\[L'y 25 \= \[\]\) y 25\]**  
 **1 \[\] \[b 2\] \[\] \[2 b c 3 x 24 \[\] \[\]y 25\]**  
 **1 \[\] \[b 2\] \[\] \[2 b c 3 \[\]x 24\]**  
 **1 \[\] \[b 2\] \[\] \[2 b c 3 x 24 \[\] \[\]y 25\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)