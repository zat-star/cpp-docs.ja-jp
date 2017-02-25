---
title: "list::list (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::list"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "list メンバー [STL/CLR]"
ms.assetid: 51b58f63-c65a-4d54-b746-0c10635b123b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::list (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー オブジェクトを構築します。  
  
## 構文  
  
```  
list();  
list(list<Value>% right);  
list(list<Value>^ right);  
explicit list(size_type count);  
list(size_type count, value_type val);  
template<typename InIt>  
    list(InIt first, InIt last);  
list(System::Collections::Generic::IEnumerable<Value>^ right);  
```  
  
#### パラメーター  
 count  
 挿入する要素の数。  
  
 最初  
 挿入する範囲の先頭。  
  
 last  
 挿入する範囲の最後。  
  
 \[right\]  
 挿入するオブジェクトまたは範囲。  
  
 val  
 挿入する要素の値。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `list();`  
  
 要素を持たない被制御シーケンスを初期化します。  空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `list(list<Value>% right);`  
  
 被制御シーケンスが `[``right``.`[list::begin](../Topic/list::begin%20\(STL-CLR\).md)`(),` `right``.`[list::end](../Topic/list::end%20\(STL-CLR\).md)`())` というシーケンスで初期化されます。  リスト オブジェクト `right`によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `list(list<Value>^ right);`  
  
 被制御シーケンスが `[``right``->`[list::begin](../Topic/list::begin%20\(STL-CLR\).md)`(),` `right``->`[list::end](../Topic/list::end%20\(STL-CLR\).md)`())` というシーケンスで初期化されます。  ハンドルが `right`であるリスト オブジェクトによって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `explicit list(size_type count);`  
  
 値 `value_type()`で `count` 要素との被制御シーケンスを個別に初期化します。  既定値を持つ要素でコンテナーを塗りつぶすためにすべてを使用します。  
  
 次のコンストラクターを見てください。  
  
 `list(size_type count, value_type val);`  
  
 値 `val`で `count` 要素との被制御シーケンスを個別に初期化します。  同じ値を持つ要素でコンテナーを塗りつぶすためにすべてを使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIt>`  
  
 `list(InIt first, InIt last);`  
  
 シーケンス `[``first``,``last``)`の被制御シーケンスを初期化します。  別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `list(System::Collections::Generic::IEnumerable<Value>^ right);`  
  
 列挙子が `right`指定したシーケンスの被制御シーケンスを初期化します。  列挙子によって指定された別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
## 使用例  
  
```  
// cliext_list_construct.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container   
    cliext::list<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// construct with a repetition of default values   
    cliext::list<wchar_t> c2(3);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// construct with a repetition of values   
    cliext::list<wchar_t> c3(6, L'x');   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    cliext::list<wchar_t>::iterator it = c3.end();   
    cliext::list<wchar_t> c4(c3.begin(), --it);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    cliext::list<wchar_t> c7(c3);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    cliext::list<wchar_t> c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0**  
 **X x x x x X**  
 **X x x x X**  
 **X x x x x X**  
 **X x x x x X**  
 **X x x x x X**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::assign](../dotnet/list-assign-stl-clr.md)   
 [list::generic\_container](../dotnet/list-generic-container-stl-clr.md)   
 [list::operator\=](../dotnet/list-operator-assign-stl-clr.md)