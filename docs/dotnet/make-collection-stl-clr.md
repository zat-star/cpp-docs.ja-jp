---
title: "make_collection (STL/CLR) | Microsoft Docs"
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
  - "cliext::make_collection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_collection 関数 [STL/CLR]"
ms.assetid: c25fb0cb-ebd8-4198-a565-bad28d32ee19
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# make_collection (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反復子のペアから `range_adapter` を作成します。  
  
## 構文  
  
```  
template<typename Iter>  
    range_adapter<Iter> make_collection(Iter first, Iter last);  
```  
  
#### パラメーター  
 Iter  
 ラップされた反復子の型。  
  
 最初  
 ラップする最初の反復子。  
  
 last  
 ラップする 2 番目の反復子。  
  
## 解説  
 このテンプレート関数は `gcnew range_adapter<Iter>(``first``,``last``)`を返します。  反復子のペアの `range_adapter``<Iter>` オブジェクトを構築するときに使用します。  
  
## 使用例  
  
```  
// cliext_make_collection.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::deque<wchar_t> Mycont;   
typedef cliext::range_adapter<Mycont::iterator> Myrange;   
int main()   
    {   
    cliext::deque<wchar_t> d1;   
    d1.push_back(L'a');   
    d1.push_back(L'b');   
    d1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in d1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Collections::ICollection^ p1 =   
        cliext::make_collection(d1.begin(), d1.end());   
    System::Console::WriteLine("Count = {0}", p1->Count);   
    System::Console::WriteLine("IsSynchronized = {0}",   
        p1->IsSynchronized);   
    System::Console::WriteLine("SyncRoot not nullptr = {0}",   
        p1->SyncRoot != nullptr);   
  
// copy the sequence   
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);   
  
    a1[0] = L'|';   
    p1->CopyTo(a1, 1);   
    a1[4] = L'|';   
    for each (wchar_t elem in a1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **b c**  
**Count \= 3**  
**IsSynchronized \= false**  
**SyncRoot のない nullptr \= true**  
 **&#124; b c &#124;**   
## 必要条件  
 **ヘッダー:** の \<cliext\/アダプター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)