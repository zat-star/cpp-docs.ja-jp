---
title: "hash_multiset::key_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::key_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_compare メンバー [STL/CLR]"
ms.assetid: 7382d18b-3cac-4a93-98db-fab486a8d275
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# hash_multiset::key_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 種類のキーの順序のデリゲート。  
  
## 構文  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>  
    key_compare;  
```  
  
## 解説  
 型は、Key 引数の順序を決定するデリゲートのシノニムです。  
  
## 使用例  
  
```  
// cliext_hash_multiset_key_compare.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    Myhash_multiset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myhash_multiset c2 = cliext::greater<wchar_t>();   
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
  
  **\(L'a、L'a\) \= True を比較します。**  
**\(L'a、L'b\) \= True を比較します。**  
**\(L'b、L'a\) \= false を比較します。**  
**\(L'a、L'a\) \= false を比較します。**  
**\(L'a、L'b\) \= false を比較します。**  
**\(L'b、L'a\) \= True を比較します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::key\_comp](../dotnet/hash-multiset-key-comp-stl-clr.md)   
 [hash\_multiset::key\_type](../dotnet/hash-multiset-key-type-stl-clr.md)   
 [hash\_multiset::value\_compare](../dotnet/hash-multiset-value-compare-stl-clr.md)