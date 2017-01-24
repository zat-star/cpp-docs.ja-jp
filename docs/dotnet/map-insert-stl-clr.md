---
title: "map::insert (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert メンバー [STL/CLR]"
ms.assetid: 599c702e-7db0-45b8-8247-4ff041a3639c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::insert (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素を追加します。  
  
## 構文  
  
```  
cliext::pair<iterator, bool> insert(value_type val);  
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
  
 一つ目のメンバー関数は、値 `val`要素を挿入することにコミットする `X`値のペアを返します。  `X.second` が TRUE の場合、`X.first` は新しく挿入される要素を指定して; それ以外の場合は `X.first` は等しい要素を指定し、その項目が既に存在している Orders 新しい要素は挿入されません。  単一の要素を挿入する場合に使用します。  
  
 2 つ目のメンバー関数は、ヒントとして `where` を使用して値 `val`要素 \(パフォーマンスを向上させるため\)、戻り値が新しく挿入される要素を指定する反復子を挿入します。  ユーザーがわかっている要素の横にある可能性のある単一の要素を挿入する場合に使用します。  
  
 3 つ目のメンバー関数は、シーケンス `[``first``,``last``)`を挿入します。  別のシーケンスからコピーしたゼロ使用します。または、より多くの要素を挿入するために。  
  
 4 つ目のメンバー関数は `right`で指定されたシーケンスを挿入します。  列挙子によって指定されたシーケンスを挿入する場合に使用します。  
  
 各要素の挿入は、被制御シーケンス内の要素数に比例する対数に時間がかかります。  ただし、挿入はカーソルに隣接する要素を指定するヒントを持つ償却された定数時間で実行できます。  
  
## 使用例  
  
```  
// cliext_map_insert.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
typedef Mymap::pair_iter_bool Pairib;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value, unique and duplicate   
// insert a single value, success and failure   
    Pairib pair1 = c1.insert(Mymap::make_value(L'x', 24));   
    System::Console::WriteLine("insert([L'x' 24]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    pair1 = c1.insert(Mymap::make_value(L'b', 2));   
    System::Console::WriteLine("insert([L'b' 2]) = [[{0} {1}] {2}]",   
        pair1.first->first, pair1.first->second, pair1.second);   
  
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    Mymap::iterator it =   
        c1.insert(c1.begin(), Mymap::make_value(L'y', 25));   
    System::Console::WriteLine("insert(begin(), [L'y' 25]) = [{0} {1}]",   
        it->first, it->second);   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Mymap c2;   
    it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Mymap c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::   
            IEnumerable<Mymap::value_type>^)%c1);   
    for each (Mymap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**挿入 \(\[\]\) L'x 24 \= \[\]X は 24\]\]**  
**挿入 \(\[\]\) L'b 2 \= \[\]b の 2\]\]**  
 **1 \[\] \[\] \[2 b c 3 \[\]x 24\]**  
**insert\(begin\(\)、\[L'y 25 \= \[\]\) y 25\]**  
 **1 \[\] \[\] \[2 b c 3 x 24 \[\] \[\]y 25\]**  
 **1 \[\] \[\] \[2 b c 3 \[\]x 24\]**  
 **1 \[\] \[\] \[2 b c 3 x 24 \[\] \[\]y 25\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [マップ](../dotnet/map-stl-clr.md)