---
title: "list::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert メンバー [STL/CLR]"
ms.assetid: 399ed30f-6b76-41a8-b180-6070e3ca1c68
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した位置の要素を追加します。  
  
## 構文  
  
```  
iterator insert(iterator where, value_type val);  
void insert(iterator where, size_type count, value_type val);  
template<typename InIt>  
    void insert(iterator where, InIt first, InIt last);  
void insert(iterator where,  
    System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### パラメーター  
 count  
 挿入する要素の数。  
  
 最初  
 挿入する範囲の先頭。  
  
 last  
 挿入する範囲の最後。  
  
 \[right\]  
 挿入する列挙体。  
  
 val  
 挿入する要素の値。  
  
 where  
 コンテナーに挿入する場合。  
  
## 解説  
 メンバー関数は、被制御シーケンス内で `where` が指す要素の前に、残りのオペランドによって指定されたシーケンスとして挿入します。  
  
 一つ目のメンバー関数は、値 `val` 要素を挿入し、新しく挿入される要素を指定する反復子を返します。  反復子で指定された位置の前に単一の要素を挿入する場合に使用します。  
  
 2 つ目のメンバー関数は、値 `val`の `count` 要素の繰り返しを挿入します。  同じ値のすべてのコピーであるゼロ使用して以上の連続する要素を挿入するために。  
  
 `InIt` が整数型である場合、3 つ目のメンバー関数は `insert(``where``, (size_type)``first``, (value_type)``last``)`と同様に動作します。  それ以外の場合は、シーケンス `[``first``,``last``)`を挿入します。  別のシーケンスからコピーした使用してゼロ以上の連続する要素を挿入するために。  
  
 4 つ目のメンバー関数は `right`で指定されたシーケンスを挿入します。  列挙子によって指定されたシーケンスを挿入する場合に使用します。  
  
 単一の要素を挿入すると、要素のコピーの数は、シーケンスのカーソル位置と近端間の要素数で直線的です。一つ以上の要素をシーケンスの先頭または末尾に挿入すると、要素のコピーが行われません。\) `InIt` が入力反復子である場合、3 番目のメンバー関数は、シーケンスに効果的に各要素の一つの挿入を実行します。  それ以外の場合は `N` 要素を挿入すると、要素のコピーの数は、シーケンスのカーソル位置と近端間の要素の数と `N` で直線的です。  
  
## 使用例  
  
```  
// cliext_list_insert.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using iterator   
    cliext::list<wchar_t>::iterator it = c1.begin();   
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",   
        *c1.insert(++it, L'x'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a repetition of values   
    cliext::list<wchar_t> c2;   
    c2.insert(c2.begin(), 2, L'y');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    it = c1.end();   
    c2.insert(c2.end(), c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    c2.insert(c2.begin(),   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value using index   
    it = c2.begin();   
    ++it, ++it, ++it;   
    c2.insert(it, L'z');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **b c**  
**insert\(begin\(\)\+1、L'x\) \= x**  
 **x b c**  
 **y 座標**  
 **y 座標 x b**  
 **x b c y 座標 x b**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)