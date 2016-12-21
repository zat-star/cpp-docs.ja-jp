---
title: "multimap::multimap (STL/CLR) | Microsoft Docs"
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
  - "cliext::multimap::multimap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multimap メンバー [STL/CLR]"
ms.assetid: cdf9c5dc-774c-424e-aeea-7554643e401c
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multimap::multimap (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー オブジェクトを構築します。  
  
## 構文  
  
```  
multimap();  
explicit multimap(key_compare^ pred);  
multimap(multimap<Key, Mapped>% right);  
multimap(multimap<Key, Mapped>^ right);  
template<typename InIter>  
    multimapmultimap(InIter first, InIter last);  
template<typename InIter>  
    multimap(InIter first, InIter last,  
        key_compare^ pred);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right);  
multimap(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
```  
  
#### パラメーター  
 最初  
 挿入する範囲の先頭。  
  
 last  
 挿入する範囲の最後。  
  
 pred  
 被制御シーケンスの順序述語。  
  
 \[right\]  
 挿入するオブジェクトまたは範囲。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `multimap();`  
  
 既定の順序述語 `key_compare()`要素を持たない被制御シーケンスを、初期化します。  既定の順序述語の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `explicit multimap(key_compare^ pred);`  
  
 命令述語 `pred`要素を持たない被制御シーケンスを、初期化します。  順序指定述語の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `multimap(multimap<Key, Mapped>% right);`  
  
 既定の順序述語のシーケンス `[``right``.`[multimap::begin](../dotnet/multimap-begin-stl-clr.md)`(),``right``.`[multimap::end](../dotnet/multimap-end-stl-clr.md)`())`の被制御シーケンスを、初期化します。  `right`multimap オブジェクトによって制御されるシーケンスのコピーである既定命令述語の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `multimap(multimap<Key, Mapped>^ right);`  
  
 既定の順序述語のシーケンス `[``right``->`[multimap::begin](../dotnet/multimap-begin-stl-clr.md)`(),``right``->`[multimap::end](../dotnet/multimap-end-stl-clr.md)`())`の被制御シーケンスを、初期化します。  `right`multimap オブジェクトによって制御されるシーケンスのコピーである既定命令述語の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `multimap(InIter first, InIter last);`  
  
 既定の順序述語のシーケンス `[``first``,``last``)`の被制御シーケンスを、初期化します。  既定の順序述語の別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `multimap(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 述語 `pred`命令のシーケンス `[``first``,``last``)`の被制御シーケンスを、初期化します。  順序指定述語の別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 既定の順序述語列挙子を `right`、指定したシーケンスの被制御シーケンスを初期化します。  既定の順序述語の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `multimap(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 命令述語 `pred`列挙子を `right`、指定したシーケンスの被制御シーケンスを初期化します。  順序指定述語の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
## 使用例  
  
```  
// cliext_multimap_construct.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
// construct an empty container   
    Mymultimap c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(Mymultimap::make_value(L'a', 1));   
    c1.insert(Mymultimap::make_value(L'b', 2));   
    c1.insert(Mymultimap::make_value(L'c', 3));   
    for each (Mymultimap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultimap c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultimap c3(c1.begin(), c1.end());   
    for each (Mymultimap::value_type elem in c3)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultimap c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c4)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultimap c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3);   
    for each (Mymultimap::value_type elem in c5)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultimap c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<   
            Mymultimap::value_type>^)%c3,   
                cliext::greater_equal<wchar_t>());   
    for each (Mymultimap::value_type elem in c6)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultimap c7(c4);   
    for each (Mymultimap::value_type elem in c7)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mymultimap c8(%c3);   
    for each (Mymultimap::value_type elem in c8)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **1 \[\] \[b 2 \[\]c 3\]**  
**size\(\) \= 0**  
 **\[\] \[b c 3 2 \[\]1 つ\]**  
 **1 \[\] \[b 2 \[\]c 3\]**  
 **\[\] \[b c 3 2 \[\]1 つ\]**  
 **1 \[\] \[b 2 \[\]c 3\]**  
 **\[\] \[b c 3 2 \[\]1 つ\]**  
 **\[\] \[b c 3 2 \[\]1 つ\]**  
 **1 \[\] \[b 2 \[\]c 3\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::generic\_container](../dotnet/multimap-generic-container-stl-clr.md)   
 [multimap::operator\=](../dotnet/multimap-operator-assign-stl-clr.md)