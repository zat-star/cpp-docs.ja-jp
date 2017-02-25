---
title: "hash_set::upper_bound (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_set::upper_bound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "upper_bound メンバー [STL/CLR]"
ms.assetid: dc8815f1-8b45-4f3d-a51f-54050d434d8f
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# hash_set::upper_bound (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定したキーに一致する範囲の末尾を検索します。  
  
## 構文  
  
```  
iterator upper_bound(key_type key);  
```  
  
#### パラメーター  
 key  
 検索するキー値。  
  
## 解説  
 このメンバー関数は `key` と同じバケットにハッシュし、`key`に並べる等価である被制御シーケンスの最後の要素 `X` が決まります。  そのような要素が存在しない場合、または `X` が被制御シーケンスの最後の要素である場合、[hash\_set::end](../dotnet/hash-set-end-stl-clr.md)`()`;を返します それ以外の場合は `X`を超える最初の要素を指定する反復子を返します。  被制御シーケンスで指定したキーに一致する要素のシーケンスの最後を現在の検索に使用されます。  
  
## 使用例  
  
```  
// cliext_hash_set_upper_bound.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_set<wchar_t> Myhash_set;   
int main()   
    {   
    Myhash_set c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",   
        c1.upper_bound(L'x') == c1.end());   
  
    System::Console::WriteLine("*upper_bound(L'a') = {0}",   
        *c1.upper_bound(L'a'));   
    System::Console::WriteLine("*upper_bound(L'b') = {0}",   
        *c1.upper_bound(L'b'));   
    return (0);   
    }  
  
```  
  
  **b c**  
**upper\_bound\(L'x'\)\=\=end\(\) \= true**  
**\*upper\_bound \(L'a \= b\)**   
**\*upper\_bound \(L'b\) \= c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_set](../dotnet/hash-set-stl-clr.md)   
 [hash\_set::count](../dotnet/hash-set-count-stl-clr.md)   
 [hash\_set::equal\_range](../dotnet/hash-set-equal-range-stl-clr.md)   
 [hash\_set::find](../Topic/hash_set::find%20\(STL-CLR\).md)   
 [hash\_set::lower\_bound](../dotnet/hash-set-lower-bound-stl-clr.md)