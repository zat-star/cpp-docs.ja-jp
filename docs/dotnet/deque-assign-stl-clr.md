---
title: "deque::assign (STL/CLR) | Microsoft Docs"
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
  - "cliext::deque::assign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assign メンバー [STL/CLR]"
ms.assetid: 03fafdbb-6b10-4464-b3dc-0cc5cb8ac980
caps.latest.revision: 14
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# deque::assign (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

すべての要素を置き換えます。  
  
## 構文  
  
```  
void assign(size_type count, value_type val);  
template<typename InIt>  
    void assign(InIt first, InIt last);  
void assign(System::Collections::Generic::IEnumerable<Value>^ right);  
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
  
## 解説  
 一つ目のメンバー関数は、値 `val`の `count` 要素の繰り返しで被制御シーケンスを置き換えます。  同じ値を持つ要素でコンテナーを塗りつぶすためにすべてを使用します。  
  
 `InIt` が整数型である場合、2 つ目のメンバー関数は `assign((size_type)``first``, (value_type)``last``)`と同様に動作します。  それ以外の場合は、シーケンス `[``first``,``last``)`と被制御シーケンスを置き換えます。  被制御シーケンスのコピーを作成するために、個別のシーケンスを使用します。  
  
 3 つ目のメンバー関数は、列挙子が `right`指定するシーケンスと被制御シーケンスを置き換えます。  列挙子によって指定されたシーケンスの被制御シーケンスのコピーを作成するために使用します。  
  
## 使用例  
  
```  
// cliext_deque_assign.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
    cliext::deque<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// assign a repetition of values   
    cliext::deque<wchar_t> c2;   
    c2.assign(6, L'x');   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an iterator range   
    c2.assign(c1.begin(), c1.end() - 1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign an enumeration   
    c2.assign(   // NOTE: cast is not needed   
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **X x x x x X**  
 **b**  
 **b c**   
## 必要条件  
 **ヘッダー:** \<cliext\/deque\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [operator\= \(deque\)](../dotnet/operator-assign-deque-stl-clr.md)