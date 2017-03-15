---
title: "deque::resize (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::deque::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize メンバー [STL/CLR]"
ms.assetid: c83f3c57-38b3-4706-a124-59bafbf88484
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# deque::resize (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

要素の数を変更します。  
  
## 構文  
  
```  
void resize(size_type new_size);  
void resize(size_type new_size, value_type val);  
```  
  
#### パラメーター  
 new\_size  
 被制御シーケンスの新しいサイズ。  
  
 val  
 埋め込みの要素の値。  
  
## 解説  
 メンバー関数も、その [deque::size](../Topic/deque::size%20\(STL-CLR\).md)`()` その後 `new_size`を返すことを確認します。  これは、被制御シーケンスをよりも長くする必要がある一つ目のメンバー関数は、2 つ目のメンバー関数は、値 `val`要素を振っていますが、値 `value_type()`要素を追加します。  被制御シーケンスを短くするには、メンバー関数も、効果的に要素の [deque::size](../Topic/deque::size%20\(STL-CLR\).md)最後の`() -``new_size` 時間を消去します。  、被制御シーケンスのサイズ `new_size`を持つトリミングまたは埋め込みを詳細に確認するために現在の被制御シーケンスを使用します。  
  
## 使用例  
  
```  
// cliext_deque_resize.cpp   
// compile with: /clr   
#include <cliext/deque>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::deque<wchar_t> c1;   
    System::Console::WriteLine("size() = {0}", c1.size());   
    c1.resize(4);   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", (int)elem);   
    System::Console::WriteLine();   
  
// resize to empty   
    c1.resize(0);   
    System::Console::WriteLine("size() = {0}", c1.size());   
  
// resize and pad   
    c1.resize(5, L'x');   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **size\(\) \= 0**  
 **0 0 0 0**  
**size\(\) \= 0**  
 **X x x x X**   
## 必要条件  
 **ヘッダー:** \<cliext\/deque\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [deque](../dotnet/deque-stl-clr.md)   
 [deque::clear](../dotnet/deque-clear-stl-clr.md)   
 [deque::erase](../Topic/deque::erase%20\(STL-CLR\).md)   
 [deque::insert](../dotnet/deque-insert-stl-clr.md)