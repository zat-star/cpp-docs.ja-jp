---
title: "_1 オブジェクト | Microsoft Docs"
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
  - "std.tr1._1"
  - "_1"
  - "std::tr1::_1"
  - "functional/std::tr1::_1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_1 オブジェクト [TR1]"
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _1 オブジェクト
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

置き換え可能な引数のプレースホルダーです。  
  
## 構文  
  
```  
namespace placeholders {  
  extern unspecified _1, _2, ... _M  
  } // namespace placeholders (within std)  
```  
  
## 解説  
 `_1, _2, ... _M` の各オブジェクトは、[bind 関数](../Topic/bind%20Function.md) によって返されたオブジェクトに対する関数呼び出しにおいて、それぞれ 1 番目から M 番目の引数を指定するプレースホルダーです。  bind 式が評価されるときに N 番目の引数が挿入される場所を指定するには、`_N` を使用します。  
  
 この実装では、`M` の値は 20 です。  
  
## 使用例  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
  **1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**  
**1\*2 \=\= 2**  
**2\*2 \=\= 4**  
**3\*2 \=\= 6**  
**1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**   
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [bind 関数](../Topic/bind%20Function.md)   
 [is\_placeholder クラス](../Topic/is_placeholder%20Class.md)