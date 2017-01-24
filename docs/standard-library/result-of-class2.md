---
title: "result_of クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "functional/std::tr1::result_of"
  - "std::tr1::result_of"
  - "result_of"
  - "std.tr1.result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of クラス [TR1]"
ms.assetid: 14ec0040-07f1-45a5-80b5-d0c9f9b00c8f
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ラップされた呼び出し可能オブジェクトの戻り値の型です。  
  
## 構文  
  
```  
template<class Ty>  
    struct result_of {  
    typedef T0 type;  
    };  
```  
  
#### パラメーター  
 `Ty`  
 関数呼び出しの記述 \(「解説」を参照\)。  
  
## 解説  
 このテンプレート クラスでは、そのメンバー `type` は、そのテンプレートの引数 `Ty` で表される関数呼び出しの戻り値の型のシノニムとして定義されます。  テンプレートの引数は、`Fty(T1, T2, ..., TN)` という形式である必要があります \(`Fty` は呼び出し可能型\)。  テンプレートは、戻り値の型を、次の順序で最初に該当した規則に従って決定します。  
  
-   `Fty` が関数の型 `R(*)(U1, U2, ..., UN)` へのポインターである場合、戻り値の型は `R` になります。  
  
-   `Fty` が関数の型 `R(&)(U1, U2, ..., UN)` への参照である場合、戻り値の型は `R` になります。  
  
-   `Fty` がメンバー関数の型 `R(U1::*)(U2, ..., UN)` へのポインターである場合、戻り値の型は `R` になります。  
  
-   `Fty` がデータ メンバーの型 `R U1::*` へのポインターである場合、戻り値の型は `R` になります。  
  
-   `Fty` が、`result_type` というメンバー typedef を持つクラスである場合、戻り値の型は `Fty::result_type` になります。  
  
-   `N` が 0 の場合 \(つまり、`Ty` が `Fty()` 形式の場合\)、戻り値の型は `void` になります。  
  
-   `Fty` が、`result` という名前のメンバー テンプレートを持つクラスである場合、戻り値の型は `Fty::result<T1, T2, ..., TN>::type` になります。  
  
-   それ以外の場合は、すべてエラーになります。  
  
## 使用例  
  
```  
// std_tr1__functional__result_of.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
template<class Fun,   
    class Arg>   
    void test_result(const Fun& fun, Arg arg)   
    {   
    typename std::result_of<Fun(Arg)>::type val = fun(arg);   
    std::cout << "val == " << val << std::endl;   
    }   
  
int main()   
    {   
    test_result(&square, 3.0);   
  
    return (0);   
    }  
  
```  
  
  **val \=\= 9**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std