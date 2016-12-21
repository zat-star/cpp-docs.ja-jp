---
title: "set::key_comp (STL/CLR) | Microsoft Docs"
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
  - "cliext::set::key_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_comp メンバー [STL/CLR]"
ms.assetid: 245db5d0-0610-4c68-a708-9bb99e48325c
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# set::key_comp (STL/CLR)
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
// cliext_set_key_comp.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
int main()   
    {   
    Myset c1;   
    Myset::key_compare^ kcomp = c1.key_comp();   
  
    System::Console::WriteLine("compare(L'a', L'a') = {0}",   
        kcomp(L'a', L'a'));   
    System::Console::WriteLine("compare(L'a', L'b') = {0}",   
        kcomp(L'a', L'b'));   
    System::Console::WriteLine("compare(L'b', L'a') = {0}",   
        kcomp(L'b', L'a'));   
    System::Console::WriteLine();   
  
// test a different ordering rule   
    Myset c2 = cliext::greater<wchar_t>();   
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
 **ヘッダー:** \<cliext および設定\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [設定](../dotnet/set-stl-clr.md)   
 [set::key\_compare](../dotnet/set-key-compare-stl-clr.md)   
 [set::key\_type](../dotnet/set-key-type-stl-clr.md)