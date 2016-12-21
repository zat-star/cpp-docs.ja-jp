---
title: "list::unique (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::unique"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique メンバー [STL/CLR]"
ms.assetid: c3a29e4e-0ec1-4472-b050-7a9511037132
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::unique (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたテストに合格した隣接する要素を削除します。  
  
## 構文  
  
```  
void unique();  
template<typename Pred2>  
    void unique(Pred2 pred);  
```  
  
#### パラメーター  
 pred  
 要素のペアの比較子。  
  
## 解説  
 一つ目のメンバー関数は、被制御シーケンス \(消去\) の直前の要素に等しいするすべての要素を削除します。。要素が `X` 要素 `Y` と `X == Y`を指定し、メンバー関数は `Y`を削除します。  等号を比較する隣接する要素のすべてのサブシーケンスの 1 枚のコピーを除くすべてを削除するときに使用します。  、メンバー関数のリーフ固有の値を持つ要素を被制御シーケンスが [list::sort](../dotnet/list-sort-stl-clr.md)`()`を呼び出すなど、Orders されることに注意してください。\(したがって、名前\)。  
  
 2 つ目のメンバー関数は、まず 1 番目と同様に動作します。ただし、`pred``(X, Y)`要素 `X` 以降の各要素 `Y` を削除します。  述語関数を満たす利用するかを指定できる点を委任し、隣接する要素のすべてのサブシーケンスの 1 枚のコピーを除くすべてを削除するために。  、メンバー関数のリーフの他の要素に並べる等価がない要素のみ被制御シーケンスが `sort(``pred``)`を呼び出すなど、Orders されることに注意してください。  
  
## 使用例  
  
```  
// cliext_list_unique.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique   
    cliext::list<wchar_t> c2(c1);   
    c2.unique();   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display contents after unique(not_equal_to)   
    c2 = c1;   
    c2.unique(cliext::not_equal_to<wchar_t>());   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b c**  
 **a**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::remove](../dotnet/list-remove-stl-clr.md)   
 [list::remove\_if](../dotnet/list-remove-if-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)