---
title: "pair::pair (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::pair::pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair メンバー [STL/CLR]"
ms.assetid: 188035f3-bd37-4b46-96dd-5ceb9a16df79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# pair::pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

pair オブジェクトを構築します。  
  
## 構文  
  
```  
pair();  
pair(pair<Coll>% right);  
pair(pair<Coll>^ right);  
pair(Value1 val1, Value2 val2);  
```  
  
#### パラメーター  
 \[right\]  
 保存するペア。  
  
 val1  
 保存する初期値。  
  
 val2  
 保存する 2 番目の値。  
  
## 解説  
 次のコンストラクターを見てください。  
  
 `pair();`  
  
 既定で構築されている値のペアを初期化します。  
  
 次のコンストラクターを見てください。  
  
 `pair(pair<Value1, Value2>% right);`  
  
 `right` `.` [pair::first](../dotnet/pair-first-stl-clr.md) と `right``.`[pair::second](../dotnet/pair-second-stl-clr.md)に保存したペアを初期化します。  
  
 `pair(pair<Value1, Value2>^ right);`  
  
 `right` `->` [pair::first](../dotnet/pair-first-stl-clr.md) と `right``>`[pair::second](../dotnet/pair-second-stl-clr.md)に保存したペアを初期化します。  
  
 次のコンストラクターを見てください。  
  
 `pair(Value1 val1, Value2 val2);`  
  
 `val1` と `val2`に保存したペアを初期化します。  
  
## 使用例  
  
```  
// cliext_pair_construct.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
// construct an empty container   
    cliext::pair<wchar_t, int> c1;   
    System::Console::WriteLine("[{0}, {1}]",   
        c1.first == L'\0' ? "\\0" : "??", c1.second);   
  
// construct with a pair of values   
    cliext::pair<wchar_t, int> c2(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);   
  
// construct by copying another pair   
    cliext::pair<wchar_t, int> c3(c2);   
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);   
  
// construct by copying a pair handle   
    cliext::pair<wchar_t, int> c4(%c3);   
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);   
  
    return (0);   
    }  
  
```  
  
  **\[\\0, 0\]**  
**\[X、3 つ\]**  
**\[X、3 つ\]**  
**\[X、3 つ\]**   
## 必要条件  
 **ヘッダー:** \<cliext\/ユーティリティ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [pair](../dotnet/pair-stl-clr.md)