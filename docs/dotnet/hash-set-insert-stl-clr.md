---
title: "hash_set::insert (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert メンバー [STL/CLR]"
ms.assetid: 0a9bc9aa-012e-4101-9e8c-f1f4b6b76af7
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_set::insert (STL/CLR)
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
// cliext_hash_set_insert.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
typedef Myhash_set::pair_iter_bool Pairib;   
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
  
// insert a single value, unique and duplicate   
    Pairib pair1 = c1.insert(L'x');   
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    pair1 = c1.insert(L'b');   
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",   
        *pair1.first, pair1.second);   
  
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert a single value with hint   
    System::Console::WriteLine("insert(begin(), L'y') = {0}",   
        *c1.insert(c1.begin(), L'y'));   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an iterator range   
    Myhash_set c2;   
    Myhash_set::iterator it = c1.end();   
    c2.insert(c1.begin(), --it);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// insert an enumeration   
    Myhash_set c3;   
    c3.insert(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
**挿入 L'x \(\) \= \[X true\]**  
**挿入 L'b \(\) \= \[false b\]**  
 **b c X**  
**insert\(begin\(\)、L'y y \=\)**   
 **X\-Y b c**  
 **b c X**  
 **X\-Y b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)