---
title: "multiset::multiset (STL/CLR) | Microsoft Docs"
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
  - "cliext::multiset::multiset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multiset メンバー [STL/CLR]"
ms.assetid: a6ddb2df-d7cd-4b12-aee7-81da1f67f57f
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# multiset::multiset (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー オブジェクトを構築します。  
  
## 構文  
  
```  
multiset();  
explicit multiset(key_compare^ pred);  
multiset(multiset<Key>% right);  
multiset(multiset<Key>^ right);  
template<typename InIter>  
    multisetmultiset(InIter first, InIter last);  
template<typename InIter>  
    multiset(InIter first, InIter last,  
        key_compare^ pred);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);  
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,  
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
  
 `multiset();`  
  
 既定の順序述語 `key_compare()`要素を持たない被制御シーケンスを、初期化します。  既定の順序述語の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `explicit multiset(key_compare^ pred);`  
  
 命令述語 `pred`要素を持たない被制御シーケンスを、初期化します。  順序指定述語の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `multiset(multiset<Key>% right);`  
  
 既定の順序述語のシーケンス `[``right``.`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),``right``.`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`の被制御シーケンスを、初期化します。  マルチセット オブジェクト `right`によって制御されるシーケンスのコピーである既定命令述語の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `multiset(multiset<Key>^ right);`  
  
 既定の順序述語のシーケンス `[``right``->`[multiset::begin](../dotnet/multiset-begin-stl-clr.md)`(),``right``->`[multiset::end](../dotnet/multiset-end-stl-clr.md)`())`の被制御シーケンスを、初期化します。  マルチセット オブジェクト `right`によって制御されるシーケンスのコピーである既定命令述語の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last);`  
  
 既定の順序述語のシーケンス `[``first``,``last``)`の被制御シーケンスを、初期化します。  既定の順序述語の別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `multiset(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 述語 `pred`命令のシーケンス `[``first``,``last``)`の被制御シーケンスを、初期化します。  順序指定述語の別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 既定の順序述語列挙子を `right`、指定したシーケンスの被制御シーケンスを初期化します。  既定の順序述語の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `multiset(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 命令述語 `pred`列挙子を `right`、指定したシーケンスの被制御シーケンスを初期化します。  順序指定述語の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
## 使用例  
  
```  
// cliext_multiset_construct.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::multiset<wchar_t> Mymultiset;   
int main()   
    {   
// construct an empty container   
    Mymultiset c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Mymultiset c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Mymultiset c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Mymultiset c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Mymultiset c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Mymultiset c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Mymultiset c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mymultiset c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **b c**  
**size\(\) \= 0**  
 **a b c**  
 **b c**  
 **a b c**  
 **b c**  
 **a b c**  
 **a b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multiset](../dotnet/multiset-stl-clr.md)   
 [multiset::generic\_container](../dotnet/multiset-generic-container-stl-clr.md)   
 [multiset::operator\=](../dotnet/multiset-operator-assign-stl-clr.md)