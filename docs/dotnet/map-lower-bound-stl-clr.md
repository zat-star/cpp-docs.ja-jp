---
title: "map::lower_bound (STL/CLR) | Microsoft Docs"
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
  - "cliext::map::lower_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lower_bound メンバー [STL/CLR]"
ms.assetid: 959651a0-f949-4cc1-859b-248b6930f16c
caps.latest.revision: 16
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# map::lower_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したキーに一致する範囲の先頭を検索します。  
  
## 構文  
  
```  
iterator lower_bound(key_type key);  
```  
  
#### パラメーター  
 key  
 検索するキー値。  
  
## 解説  
 このメンバー関数は `key`に並べる等価である被制御シーケンスの最初の要素 `X` が決まります。  そのような要素が存在しない場合、[map::end](../dotnet/map-end-stl-clr.md)`()`;を返します それ以外の場合は `X`を指定する反復子を返します。  被制御シーケンスで指定したキーに一致する要素のシーケンスの先頭を現在の検索に使用されます。  
  
## 使用例  
  
```  
// cliext_map_lower_bound.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",   
        c1.lower_bound(L'x') == c1.end());   
  
    Mymap::iterator it = c1.lower_bound(L'a');   
    System::Console::WriteLine("*lower_bound(L'a') = [{0} {1}]",   
        it->first, it->second);   
    it = c1.lower_bound(L'b');   
    System::Console::WriteLine("*lower_bound(L'b') = [{0} {1}]",   
        it->first, it->second);   
    return (0);   
    }  
  
```  
  
  **1 \[\] \[b 2 \[\]c 3\]**  
**lower\_bound\(L'x'\)\=\=end\(\) \= true**  
**\*lower\_bound \(L'a\) \= \[1 つ\]**  
**\*lower\_bound \(L'b\) \= \[b 2\]**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [マップ](../dotnet/map-stl-clr.md)   
 [map::count](../dotnet/map-count-stl-clr.md)   
 [map::equal\_range](../dotnet/map-equal-range-stl-clr.md)   
 [map::find](../Topic/map::find%20\(STL-CLR\).md)   
 [map::upper\_bound](../dotnet/map-upper-bound-stl-clr.md)