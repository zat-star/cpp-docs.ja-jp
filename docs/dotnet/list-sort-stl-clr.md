---
title: "list::sort (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::sort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sort メンバー [STL/CLR]"
ms.assetid: f811d5f4-a19e-4194-8765-1e68097c52f0
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# list::sort (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

被制御シーケンスを順序付けます。  
  
## 構文  
  
```  
void sort();  
template<typename Pred2>  
    void sort(Pred2 pred);  
```  
  
#### パラメーター  
 pred  
 要素のペアの比較子。  
  
## 解説  
 一つ目のメンバー関数は `operator<` に並べ替えられたよう、被制御シーケンスの要素を再配置します。。要素は、値のシーケンスによって進行とともに減りません。  昇順のシーケンスを並べ替えるには、このメンバー関数を使用します。  
  
 2 つ目のメンバー関数は、まず 1 番目と同様に動作します。ただし、シーケンスは `pred` に並べ替えられます。`pred``(X, Y)` は、生成されたシーケンスの要素 `Y` に従ってすべての要素 `X` の場合は false になります。  、述語関数またはデリゲートで指定した順序でシーケンスを並べ替えるために使用します。  
  
 関数は、どちらも安定した並べ替えを実行します。。元の被制御シーケンス内の要素のペアは、被制御シーケンスの反転されません。  
  
## 使用例  
  
```  
// cliext_list_sort.cpp   
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
  
// sort descending and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// sort ascending and redisplay   
    c1.sort();   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**  
 **a b c**  
 **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::merge](../dotnet/list-merge-stl-clr.md)   
 [list::reverse](../dotnet/list-reverse-stl-clr.md)   
 [list::splice](../Topic/list::splice%20\(STL-CLR\).md)   
 [list::unique](../dotnet/list-unique-stl-clr.md)