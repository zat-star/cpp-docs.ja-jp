---
title: "greater (STL/CLR) | Microsoft Docs"
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
  - "cliext::greater"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "greater 関数 [STL/CLR]"
ms.assetid: a6dfe5e3-b5a5-4ec4-8e53-8dd33a37d10d
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# greater (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、最初の引数が 2 番目のオブジェクトよりも大きい場合にのみ呼び出すと true を返すファンクタを表します。  引数の型を使用して、指定する関数オブジェクトを使用します。  
  
## 構文  
  
```  
template<typename Arg>  
    ref class greater  
    { // wrap operator()  
public:  
    typedef Arg first_argument_type;  
    typedef Arg second_argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<  
        first_argument_type, second_argument_type, result_type>  
        delegate_type;  
  
    greater();  
    greater(greater<Arg>% right);  
  
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
|greater|ファンクタを構築します。|  
  
|演算子|説明|  
|---------|--------|  
|operator\(\)|必要な関数を計算します。|  
|演算子の delegate\_type^|デリゲートにファンクタをキャストします。|  
  
## 解説  
 このテンプレート クラスは、2 引数のファンクタを表します。  これは、最初の引数が 2 番目のオブジェクトよりも大きい場合にのみオブジェクトが関数として呼び出されると、true を返すように `operator()` メンバー演算子を定義します。  
  
 型が `delegate_type^` である適切に変換する関数の引数が、またはオブジェクトを渡すことができます。  
  
## 使用例  
  
```  
// cliext_greater.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(3);   
    Myvector c2;   
    c2.push_back(3);   
    c2.push_back(3);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 3" and " 3 3"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    for each (int elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c2.begin(), c3.begin(), cliext::greater<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 3**  
 **3 3**  
 **1 0**   
## 必要条件  
 **ヘッダー:** の \<cliext と機能\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [less\_equal](../dotnet/less-equal-stl-clr.md)