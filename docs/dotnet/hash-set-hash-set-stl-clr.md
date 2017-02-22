---
title: "hash_set::hash_set (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::hash_set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "hash_set メンバー [STL/CLR]"
ms.assetid: 006414ed-db5a-4c08-ac81-4a8ae57d0aad
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# hash_set::hash_set (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンテナー オブジェクトを構築します。  
  
## 構文  
  
```  
hash_set();  
explicit hash_set(key_compare^ pred);  
hash_set(key_compare^ pred, hasher^ hashfn);  
hash_set(hash_set<Key>% right);  
hash_set(hash_set<Key>^ right);  
template<typename InIter>  
    hash_sethash_set(InIter first, InIter last);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred);  
template<typename InIter>  
    hash_set(InIter first, InIter last,  
        key_compare^ pred, hasher^ hashfn);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred);  
hash_set(System::Collections::Generic::IEnumerable<GValue>^ right,  
    key_compare^ pred, hasher^ hashfn);  
```  
  
#### パラメーター  
 最初  
 挿入する範囲の先頭。  
  
 hashfn  
 バケットにキーを割り当てるためのハッシュ関数。  
  
 last  
 挿入する範囲の最後。  
  
 pred  
 被制御シーケンスの順序述語。  
  
 \[right\]  
 挿入するオブジェクトまたは範囲。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `hash_set();`  
  
 要素なし、既定命令述語 `key_compare()`と、既定のハッシュ関数と被制御シーケンスを初期化します。  既定の順序述語、ハッシュ関数の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `explicit hash_set(key_compare^ pred);`  
  
 要素を持たない、および述語 `pred`と、既定のハッシュ関数と被制御シーケンスを初期化します。  指定した述語命令と既定のハッシュ関数の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(key_compare^ pred, hasher^ hashfn);`  
  
 要素を持たない、および述語 `pred`、ハッシュ関数 `hashfn`と被制御シーケンスを初期化します。  順序指定述語、ハッシュ関数の空の最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(hash_set<Key>% right);`  
  
 シーケンス `[``right``.`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),``right``.`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`、既定の順序述語、および既定のハッシュ関数の被制御シーケンスを初期化します。  既定の順序述語、ハッシュ関数を hash\_set オブジェクト `right`、によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(hash_set<Key>^ right);`  
  
 シーケンス `[``right``->`[hash\_set::begin](../dotnet/hash-set-begin-stl-clr.md)`(),``right``->`[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`())`、既定の順序述語、および既定のハッシュ関数の被制御シーケンスを初期化します。  既定の順序述語、ハッシュ関数を hash\_set オブジェクト `right`、によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定する場合に使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last);`  
  
 シーケンス `[``first``,``last``)`、既定の順序述語、および既定のハッシュ関数の被制御シーケンスを初期化します。  既定の順序述語、ハッシュ関数を別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred);`  
  
 シーケンス `[``first``,``last``)`の順序、述語 `pred`の、既定のハッシュ関数の被制御シーケンスを初期化します。  指定した述語命令と既定のハッシュ関数を別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `template<typename InIter>`  
  
 `hash_set(InIter first, InIter last,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 シーケンス `[``first``,``last``)`の順序、述語 `pred`、およびハッシュ関数 `hashfn`の被制御シーケンスを初期化します。  指定した述語命令とハッシュ関数を別のシーケンスの被制御シーケンスのコピーを、作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right);`  
  
 列挙子は、既定 `right`命令述語で指定すると、シーケンスのおよび既定のハッシュ関数の被制御シーケンスを初期化します。  既定の順序述語、ハッシュ関数の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred);`  
  
 列挙子が `right`、および述語 `pred`を指定すると、シーケンスの既定のハッシュ関数の被制御シーケンスを初期化します。  指定した述語命令と既定のハッシュ関数の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
 次のコンストラクターを見てください。  
  
 `hash_set(System::Collections::Generic::IEnumerable<Key>^ right,`  
  
 `key_compare^ pred, hasher^ hashfn);`  
  
 列挙子が `right`、および述語 `pred`を指定すると、シーケンスのハッシュ関数 `hashfn`の被制御シーケンスを初期化します。  指定した述語命令とハッシュ関数の列挙子は、作成している別のシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
## 使用例  
  
```  
// cliext_hash_set_construct.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
int myfun(wchar_t key)   
    { // hash a key   
    return (key ^ 0xdeadbeef);   
    }   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
// construct an empty container   
    Myhash_set c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule   
    Myhash_set c2 = cliext::greater_equal<wchar_t>();   
    System::Console::WriteLine("size() = {0}", c2.size());   
  
    c2.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an ordering rule and hash function   
    Myhash_set c2h(cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    System::Console::WriteLine("size() = {0}", c2h.size());   
  
    c2h.insert(c1.begin(), c1.end());   
    for each (wchar_t elem in c2h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an iterator range   
    Myhash_set c3(c1.begin(), c1.end());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule   
    Myhash_set c4(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an iterator range and an ordering rule and hash function   
    Myhash_set c4h(c1.begin(), c1.end(),   
        cliext::greater_equal<wchar_t>(),   
        gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c4h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct with an enumeration   
    Myhash_set c5(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);   
    for each (wchar_t elem in c5)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule   
    Myhash_set c6(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>());   
    for each (wchar_t elem in c6)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct with an enumeration and an ordering rule and hash function   
    Myhash_set c6h(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,   
            cliext::greater_equal<wchar_t>(),   
                gcnew Myhash_set::hasher(&myfun));   
    for each (wchar_t elem in c6h)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine();   
  
// construct from a generic container   
    Myhash_set c7(c4);   
    for each (wchar_t elem in c7)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Myhash_set c8(%c3);   
    for each (wchar_t elem in c8)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **b c**  
**size\(\) \= 0**  
 **b c**  
**size\(\) \= 0**  
 **a b c**  
 **b c**  
 **b c**  
 **a b c**  
 **b c**  
 **b c**  
 **a b c**  
 **b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::generic\_container](../Topic/hash_set::generic_container%20\(STL-CLR\).md)   
 [hash\_set::operator\=](../dotnet/hash-set-operator-assign-stl-clr.md)