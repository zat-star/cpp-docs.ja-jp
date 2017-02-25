---
title: "logical_and (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::logical_and"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_and 関数 [STL/CLR]"
ms.assetid: ae103802-11e0-4060-a4f3-4f6fdc209e7c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# logical_and (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、呼び出されたときに true に場合にのみ true を最初の引数と 2 番目のテストも返すファンクタを表します。  引数の型を使用して、指定する関数オブジェクトを使用します。  
  
## 構文  
  
```  
template<typename Arg>  
    ref class logical_and  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    logical_and();  
    logical_and(logical_and<Arg>% right);  
  
    result_type operator()(first_argument_type left,  
        second_argument_type right);  
    operator delegate_type^();  
    };  
```  
  
#### パラメーター  
 引数  
 引数の型。  
  
## メンバー関数  
  
|型定義|説明|  
|---------|--------|  
|delegate\_type|汎用デリゲートの型。|  
|first\_argument\_type|ファンクタの最初の引数の型。|  
|result\_type|ファンクタの結果の型です。|  
|second\_argument\_type|ファンクタ 2 番目の引数の型です。|  
  
|メンバー|説明|  
|----------|--------|  
|logical\_and|ファンクタを構築します。|  
  
|演算子|説明|  
|---------|--------|  
|operator\(\)|必要な関数を計算します。|  
|演算子の delegate\_type^|デリゲートにファンクタをキャストします。|  
  
## 解説  
 このテンプレート クラスは、2 引数のファンクタを表します。  そのオブジェクトが関数として呼び出されると、True に場合にのみ true を最初の引数と 2 番目のテストの両方で返そうメンバー演算子を定義します `operator()`。  
  
 型が `delegate_type^` である適切に変換する関数の引数が、またはオブジェクトを渡すことができます。  
  
## 使用例  
  
```  
// cliext_logical_and.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(2);   
    c1.push_back(0);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 1 0" and " 1 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::logical_and<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **2 0**  
 **3 0**  
 **1 0**   
## 必要条件  
 **ヘッダー:** の \<cliext と機能\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [logical\_or](../Topic/logical_or%20\(STL-CLR\).md)