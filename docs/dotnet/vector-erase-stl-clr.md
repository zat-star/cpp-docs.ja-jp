---
title: "vector::erase (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::erase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase メンバー [STL/CLR]"
ms.assetid: 624905eb-83c0-499b-a07a-c10aebd7acc3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# vector::erase (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定した位置にある要素を削除します。  
  
## 構文  
  
```  
iterator erase(iterator where);  
iterator erase(iterator first, iterator last);  
```  
  
#### パラメーター  
 最初  
 消去する範囲の先頭。  
  
 last  
 消去する範囲の最後。  
  
 where  
 消去する要素。  
  
## 解説  
 一つ目のメンバー関数は `where`が指す被制御シーケンスの要素を削除します。  単一の要素を削除する場合に使用します。  
  
 2 つ目のメンバー関数は、範囲 `[``first``,``last``)`の被制御シーケンスの要素を削除します。  使用するゼロ以上の連続する要素を削除するには、それを。  
  
 このメンバー関数は、そのような要素が存在しない場合、要素を削除した後に残った一つ目の要素を指定する場合は [vector::end](../dotnet/vector-end-stl-clr.md)`()` 反復子を返します。  
  
 要素をオフにすると、要素のコピーの数は削除とシーケンスの最後の近端間の要素数で直線的です。一つ以上の要素をシーケンスの先頭または末尾に無効に \(要素のコピーが行われません。\)  
  
## 使用例  
  
```  
// cliext_vector_erase.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase an element and reinspect   
    System::Console::WriteLine("erase(begin()) = {0}",   
        *c1.erase(c1.begin()));   
  
// add elements and display " b c d e"   
    c1.push_back(L'd');   
    c1.push_back(L'e');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// erase all but end   
    cliext::vector<wchar_t>::iterator it = c1.end();   
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",   
        *c1.erase(c1.begin(), --it));   
    System::Console::WriteLine("size() = {0}", c1.size());   
    return (0);   
    }  
  
```  
  
  **b c**  
**erase\(begin\(\)\= b\)**   
 **b c d e**  
**erase\(begin\(\)、end\(\)\-1\) \= e**  
**size\(\) \= 1**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [vector::clear](../dotnet/vector-clear-stl-clr.md)