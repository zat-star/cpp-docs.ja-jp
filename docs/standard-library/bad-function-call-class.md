---
title: "bad_function_call クラス | Microsoft Docs"
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
  - "std::tr1::bad_function_call"
  - "functional/std::tr1::bad_function_call"
  - "std.tr1.bad_function_call"
  - "bad_function_call"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_function_call クラス [TR1]"
ms.assetid: b70a0268-43ff-4f3b-a283-faf1cb172d4c
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_function_call クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

無効な関数呼び出しを報告します。  
  
## 構文  
  
```  
class bad_function_call  
    : public std::exception {  
    };  
```  
  
## 解説  
 このクラスは、[function クラス](../standard-library/function-class.md) オブジェクトが空であるために、その `operator()` の呼び出しに失敗したときにスローされる例外を表します。  
  
## 使用例  
  
```  
// std_tr1__functional__bad_function_call.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
typedef double (Fd)(double);   
typedef std::function<Fd> Myfunc;   
  
double square(double x)   
    {   
    return (x * x);   
    }   
  
int main()   
    {   
    Myfunc fd0(square);   
    std::cout << "x * x == " << fd0(3) << std::endl;   
  
    try   
        {   
        Myfunc fd1;   
        std::cout << fd1(3) << std::endl;   
        }   
    catch (const std::bad_function_call&)   
        {   
        std::cout << "bad function call" << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
  **x \* x \=\= 9**  
**無効な関数呼び出し**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std