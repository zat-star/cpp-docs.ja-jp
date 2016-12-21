---
title: "bad_weak_ptr クラス | Microsoft Docs"
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
  - "memory/std::tr1::bad_weak_ptr"
  - "std::tr1::bad_weak_ptr"
  - "bad_weak_ptr"
  - "tr1::bad_weak_ptr"
  - "tr1.bad_weak_ptr"
  - "std.tr1.bad_weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_weak_ptr クラス"
  - "bad_weak_ptr クラス [TR1]"
ms.assetid: a09336d5-7237-4480-ab6b-3787e0e6025e
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# bad_weak_ptr クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

weak\_ptr が無効であることを示す例外を報告します。  
  
## 構文  
  
```  
class bad_weak_ptr  
    : public std::exception {  
public:  
    bad_weak_ptr();  
    const char *what() throw();  
    };  
```  
  
## 解説  
 このクラスは、型 [weak\_ptr クラス](../standard-library/weak-ptr-class.md) の引数を取る [shared\_ptr クラス](../standard-library/shared-ptr-class.md) コンストラクターからスローされる可能性がある例外について記述します。  メンバー関数 `what` は、`"bad_weak_ptr"` を返します。  
  
## 使用例  
  
```  
// std_tr1__memory__bad_weak_ptr.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::weak_ptr<int> wp;   
  
     {   
    std::shared_ptr<int> sp(new int);   
    wp = sp;   
     }   
  
    try   
        {   
        std::shared_ptr<int> sp1(wp); // weak_ptr has expired   
        }   
    catch (const std::bad_weak_ptr&)   
        {   
        std::cout << "bad weak pointer" << std::endl;   
        }   
    catch (...)   
        {   
        std::cout << "unknown exception" << std::endl;   
        }   
  
    return (0);   
    }  
  
```  
  
  **不適切なウィーク ポインター**   
## 必要条件  
 **ヘッダー:** \<memory\>  
  
 **名前空間:** std  
  
## 参照  
 [weak\_ptr クラス](../standard-library/weak-ptr-class.md)