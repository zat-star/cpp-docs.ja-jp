---
title: "コンパイラの警告 (レベル 3) C4995 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4995"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4995"
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 3) C4995
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 名前が避けられた \#pragma として記述されています。  
  
 [deprecated](../Topic/deprecated%20\(C-C++\).md) プラグマでマークされている関数が見つかりました。  この関数は、将来のリリースではサポートされなくなる可能性があります。  この警告は、[warning](../../preprocessor/warning.md) プラグマを使用するとオフにできます。以下の例を参照してください。  
  
## 使用例  
 次の例では警告 C4995 が生成されます。  
  
```  
// C4995.cpp  
// compile with: /W3  
#include <stdio.h>  
  
// #pragma warning(disable : 4995)  
void func1(void)  
{  
    printf("\nIn func1");  
}  
  
int main()   
{  
    func1();  
    #pragma deprecated(func1)  
    func1();   // C4995  
}  
```