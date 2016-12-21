---
title: "list::resize (STL/CLR) | Microsoft Docs"
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
  - "cliext::list::resize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resize メンバー [STL/CLR]"
ms.assetid: c4b8d41f-a62b-4dbc-8568-0e0a9da24016
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# list::resize (STL/CLR)
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
 メンバー関数も、その [list::size](../dotnet/list-size-stl-clr.md)`()` その後 `new_size`を返すことを確認します。  これは、被制御シーケンスをよりも長くする必要がある一つ目のメンバー関数は、2 つ目のメンバー関数は、値 `val`要素を振っていますが、値 `value_type()`要素を追加します。  被制御シーケンスを短くするには、メンバー関数も、効果的に要素の [list::size](../dotnet/list-size-stl-clr.md)最後の`() -``new_size` 時間を消去します。  、被制御シーケンスのサイズ `new_size`を持つトリミングまたは埋め込みを詳細に確認するために現在の被制御シーケンスを使用します。  
  
## 使用例  
  
```  
// cliext_list_resize.cpp   
// compile with: /clr   
#include <cliext/list>   
  
int main()   
    {   
// construct an empty container and pad with default values   
    cliext::list<wchar_t> c1;   
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
 **ヘッダー:** の \<cliext\/リスト\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [一覧](../dotnet/list-stl-clr.md)   
 [list::clear](../dotnet/list-clear-stl-clr.md)   
 [list::erase](../dotnet/list-erase-stl-clr.md)   
 [list::insert](../dotnet/list-insert-stl-clr.md)