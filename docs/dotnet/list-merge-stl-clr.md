---
title: "list::merge (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::list::merge"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "merge メンバー [STL/CLR]"
ms.assetid: f8e93cd3-bd08-4086-859b-08a2899cc9a6
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# list::merge (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 つの順序付けされた被制御シーケンスをマージします。  
  
## 構文  
  
```  
void merge(list<Value>% right);  
template<typename Pred2>  
    void merge(list<Value>% right, Pred2 pred);  
```  
  
#### パラメーター  
 pred  
 要素のペアの比較子。  
  
 \[right\]  
 マージするコンテナー。  
  
## 解説  
 一つ目のメンバー関数は `right` によって制御されるシーケンスからすべての要素を削除し、被制御シーケンスに挿入します。  シーケンスには、両方とも `operator<` で事前に順番に配置する必要があります。。要素が値のいずれかのシーケンスで管理すると同時に減って必要があります。  結果のシーケンスには、`operator<`に並べ替えられます。  このシーケンスに 2 文字のシーケンスを値の代わりに増加またはマージするには、この値を大きくメンバー関数を使用します。  
  
 2 つ目のメンバー関数は、まず 1 番目と同様に動作します。ただし、シーケンスは `pred` に並べ替えられます。`pred``(X, Y)` は、シーケンスの要素 `Y` に従ってすべての要素 `X` に false である必要があります。  述語関数に並べ替えられた 2 二つのシーケンスを結合または指定できます。デリゲートする場合に使用します。  
  
 関数は、どちらも安定したマージを実行します。。元の被制御シーケンスの要素のペアは、被制御シーケンスの反転されません。  また、被制御シーケンスの要素 `X` と `Y` のペアに同じ大小関係がある場合、。`!(X < Y) && !(X < Y)`。元の被制御シーケンスの要素は `right`によって制御されるシーケンスの要素の前面に表示されます。  
  
## 使用例  
  
```  
// cliext_list_merge.cpp   
// compile with: /clr   
#include <cliext/list>   
  
typedef cliext::list<wchar_t> Mylist;   
int main()   
    {   
    cliext::list<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'c');   
    c1.push_back(L'e');   
  
// display initial contents " a c e"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    cliext::list<wchar_t> c2;   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
    c2.push_back(L'f');   
  
// display initial contents " b d f"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// merge and display   
    cliext::list<wchar_t> c3(c1);   
    c3.merge(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c2.size() = {0}", c2.size());   
  
// sort descending, merge descending, and redisplay   
    c1.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.sort(cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    c3.merge(c1, cliext::greater<wchar_t>());   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("c1.size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **C\+\+. e**  
 **b \\ f**  
 **a b c d e f**  
**c2.size\(\) \= 0**  
 **e.c a.**  
 **f e a b c d**  
 **f e e c a b c d**  
**c1.size\(\) \= 0**   
## 必要条件  
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::sort](../dotnet/list-sort-stl-clr.md)   
 [list::splice](../Topic/list::splice%20\(STL-CLR\).md)