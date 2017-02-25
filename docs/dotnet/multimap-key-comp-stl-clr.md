---
title: "multimap::key_comp (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::multimap::key_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_comp メンバー [STL/CLR]"
ms.assetid: 05250549-d589-4e1d-8ae9-321ff4ad384b
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# multimap::key_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 種類のキーの順序のデリゲートをコピーします。  
  
## 構文  
  
```  
key_compare^key_comp();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの並べ替えに使用されるごとにデリゲートを返します。  2 つのキーを比較する場合にこれを使用します。  
  
## 使用例  
  
```  
// cliext_multimap_key_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::multimap<wchar_t, int> Mymultimap;   
int main()   
    {   
    Mymultimap c1;   
    Mymultimap::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Mymultimap c2 = cliext::greater<wchar_t>();   
    kcomp = c2.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    return (0);   
    }  
  
```  
  
  **\(L'a、L'a\) \= false を比較します。**  
**\(L'a、L'b\) \= True を比較します。**  
**\(L'b、L'a\) \= false を比較します。**  
**\(L'a、L'a\) \= false を比較します。**  
**\(L'a、L'b\) \= false を比較します。**  
**\(L'b、L'a\) \= True を比較します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [multimap](../dotnet/multimap-stl-clr.md)   
 [multimap::key\_compare](../dotnet/multimap-key-compare-stl-clr.md)   
 [multimap::key\_type](../dotnet/multimap-key-type-stl-clr.md)