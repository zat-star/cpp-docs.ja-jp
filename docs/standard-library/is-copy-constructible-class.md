---
title: "is_copy_constructible クラス | Microsoft Docs"
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
  - "is_copy_constructible"
  - "std.is_copy_constructible"
  - "std::is_copy_constructible"
  - "type_traits/std::is_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_copy_constructible"
ms.assetid: d8db9d4c-21ed-4884-bead-0b0b562de007
caps.latest.revision: 13
caps.handback.revision: 1
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# is_copy_constructible クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

型にコピー コンストラクターが存在するかどうかをテストします。  
  
## 構文  
  
```  
template<class Ty>  
    struct is_copy_constructible;  
```  
  
#### パラメーター  
 `Ty`  
 照会する型。  
  
## 解説  
 型 `Ty` がコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。  
  
## 使用例  
  
```  
#include <type_traits>   
#include <iostream>   
  
struct Copyable  
{  
    int val;  
};  
  
struct NotCopyable  
{  
   NotCopyable(const NotCopyable&) = delete;  
   int val;  
  
};  
  
int main()  
{  
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha  
        << std::is_copy_constructible<Copyable>::value << std::endl;  
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha  
        << std::is_copy_constructible<NotCopyable>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
  **is\_copy\_constructible\<Copyable\> \=\= true**  
**is\_copy\_constructible\<NotCopyable \> \=\= false**   
## 必要条件  
 **ヘッダー:** \<type\_traits\>  
  
 **名前空間:** std  
  
## 参照  
 [\<type\_traits\>](../standard-library/type-traits.md)