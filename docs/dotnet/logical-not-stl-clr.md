---
title: "logical_not (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::logical_not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "logical_not 関数 [STL/CLR]"
ms.assetid: 32a2c6e2-1c58-41ac-8827-f3ee5adfe81d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# logical_not (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、いずれかの引数を false としてテストする場合のみ、呼び出されたときに true を返すファンクタを表します。  引数の型を使用して、指定する関数オブジェクトを使用します。  
  
## 構文  
  
```  
template<typename Arg>  
    ref class logical_not  
    { // wrap operator()  
public:  
    typedef Arg argument_type;  
    typedef bool result_type;  
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<  
        argument_type, result_type>  
        delegate_type;  
  
    logical_not();  
    logical_not(logical_not<Arg> %right);  
  
    result_type operator()(argument_type left);  
    operator delegate_type^();  
    };  
```  
  
#### パラメーター  
 引数  
 引数の型。  
  
## メンバー関数  
  
|型定義|説明|  
|---------|--------|  
|argument\_type|ファンクタの引数の型です。|  
|delegate\_type|汎用デリゲートの型。|  
|result\_type|ファンクタの結果の型です。|  
  
|メンバー|説明|  
|----------|--------|  
|logical\_not|ファンクタを構築します。|  
  
|演算子|説明|  
|---------|--------|  
|operator\(\)|必要な関数を計算します。|  
|演算子の delegate\_type^|デリゲートにファンクタをキャストします。|  
  
## 解説  
 このテンプレート クラスは、1 引数のファンクタを表します。  これは、引数が false としてテストする場合のみオブジェクトが関数として呼び出されると、true を返すように `operator()` メンバー演算子を定義します。  
  
 型が `delegate_type^` である適切に変換する関数の引数が、またはオブジェクトを渡すことができます。  
  
## 使用例  
  
```  
// cliext_logical_not.cpp   
// compile with: /clr   
#include <cliext/algorithm>   
#include <cliext/functional>   
#include <cliext/vector>   
  
typedef cliext::vector<int> Myvector;   
int main()   
    {   
    Myvector c1;   
    c1.push_back(4);   
    c1.push_back(0);   
    Myvector c3(2, 0);   
  
// display initial contents " 4 0"   
    for each (int elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// transform and display   
    cliext::transform(c1.begin(), c1.begin() + 2,   
        c3.begin(), cliext::logical_not<int>());   
    for each (int elem in c3)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **4 0**  
 **0 1**   
## 必要条件  
 **ヘッダー:** の \<cliext と機能\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [negate](../Topic/negate%20\(STL-CLR\).md)