---
title: "make_pair (STL/CLR) | Microsoft Docs"
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
  - "cliext::make_pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "make_pair 関数 [STL/CLR]"
ms.assetid: 74733f2c-97b0-4d69-b431-5ab8f0de9e3e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# make_pair (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

値のペアから `pair` を作成します。  
  
## 構文  
  
```  
template<typename Value1,  
    typename Value2>  
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);  
```  
  
#### パラメーター  
 Value1  
 最初のラップされた値の型。  
  
 Value2  
 2 番目のラップされた値の型。  
  
 最初  
 ラップする最初の値。  
  
 秒  
 ラップする 2 番目の値です。  
  
## 解説  
 このテンプレート関数は `pair<``Value1``,``Value2``>(``first``,``second``)`を返します。  値のペアの `pair``<``Value1``,``Value2``>` オブジェクトを構築するときに使用します。  
  
## 使用例  
  
```  
// cliext_make_pair.cpp   
// compile with: /clr   
#include <cliext/utility>   
  
int main()   
    {   
    cliext::pair<wchar_t, int> c1(L'x', 3);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
  
    c1 = cliext::make_pair(L'y', 4);   
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);   
    return (0);   
    }  
  
```  
  
  **\[X、3 つ\]**  
**\[y、4\]**   
## 必要条件  
 **ヘッダー:** \<cliext\/ユーティリティ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [range\_adapter](../dotnet/range-adapter-stl-clr.md)