---
title: "true (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "true_cpp"
  - "true"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "true キーワード [C++]"
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# true (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
        bool-identifier = true ;  
bool-expression logical-operator true ;  
```  
  
## 解説  
 このキーワードは、[bool](../cpp/bool-cpp.md) 型の変数または条件式で使用する 2 つの値のうちの 1 つです \(現在、条件式は true ブール式です\)。  `i` が `bool` 型の場合、ステートメント `i = true;` は  **に `i`true** を割り当てます。  
  
## 使用例  
  
```  
// bool_true.cpp  
#include <stdio.h>  
int main()  
{  
    bool bb = true;  
    printf_s("%d\n", bb);  
    bb = false;  
    printf_s("%d\n", bb);  
}  
```  
  
  **1**  
**0**   
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)