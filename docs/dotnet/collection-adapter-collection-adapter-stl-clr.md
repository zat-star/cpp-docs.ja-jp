---
title: "collection_adapter::collection_adapter (STL/CLR) | Microsoft Docs"
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
  - "cliext::collection_adapter"
  - "cliext::collection_adapter::collection_adapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collection_adapter メンバー [STL/CLR]"
ms.assetid: 7e2bb75b-d735-4135-9523-719683e06fe9
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# collection_adapter::collection_adapter (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アダプター オブジェクトを構築します。  
  
## 構文  
  
```  
collection_adapter();  
collection_adapter(collection_adapter<Coll>% right);  
collection_adapter(collection_adapter<Coll>^ right);  
collection_adapter(Coll^ collection);  
```  
  
#### パラメーター  
 コレクション  
 ラップする必要 BCL のハンドル。  
  
 \[right\]  
 コピーするオブジェクト。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `collection_adapter();`  
  
 `nullptr`の格納されているハンドルを初期化します。  
  
 次のコンストラクターを見てください。  
  
 `collection_adapter(collection_adapter<Coll>% right);`  
  
 `right` `.` [collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md) `()`の格納されているハンドルを初期化します。  
  
 次のコンストラクターを見てください。  
  
 `collection_adapter(collection_adapter<Coll>^ right);`  
  
 `right` `->` [collection\_adapter::base](../dotnet/collection-adapter-base-stl-clr.md) `()`の格納されているハンドルを初期化します。  
  
 次のコンストラクターを見てください。  
  
 `collection_adapter(Coll^ collection);`  
  
 `collection`の格納されているハンドルを初期化します。  
  
## 使用例  
  
```  
// cliext_collection_adapter_construct.cpp   
// compile with: /clr   
#include <cliext/adapter>   
#include <cliext/deque>   
  
typedef cliext::collection_adapter<   
    System::Collections::ICollection> Mycoll;   
int main()   
    {   
    cliext::deque<wchar_t> d6x(6, L'x');   
  
// construct an empty container   
    Mycoll c1;   
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);   
  
// construct with a handle   
    Mycoll c2(%d6x);   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying another container   
    Mycoll c3(c2);   
    for each (wchar_t elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// construct by copying a container handle   
    Mycoll c4(%c3);   
    for each (wchar_t elem in c4)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    return (0);   
    }  
  
```  
  
  **base\(\) の 空白 \= true**  
 **X x x x x X**  
 **X x x x x X**  
 **X x x x x X**   
## 必要条件  
 **ヘッダー:** の \<cliext\/アダプター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [collection\_adapter](../Topic/collection_adapter%20\(STL-CLR\).md)   
 [collection\_adapter::operator\=](../dotnet/collection-adapter-operator-assign-stl-clr.md)