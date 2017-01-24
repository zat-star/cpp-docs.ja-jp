---
title: "コンパイラの警告 (レベル 4) C4703 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4703"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4703"
ms.assetid: 5dad454e-69e3-4931-9168-050a861c05f8
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 4) C4703
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用される可能性があり、初期化されていないローカル ポインター変数「name」  
  
 ローカル ポインター変数 *name* 操作で値が使用されることがあります。  この場合、予期しない結果が生じる可能性があります。  
  
## 使用例  
 次のコードは、C4703 C4701 が生成されます。  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr) // C4701 and C4703  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
  **c:\\src\\test.cpp\(10\) : 警告 C4701: 使用される可能性があり、初期化されていないローカル変数" p」**  
 **c:\\src\\test.cpp\(10\) : 警告 C4703: 使用される可能性があり、初期化されていないローカル ポインター変数「p」** この警告を解決するには、この例に示すように、変数を初期化してください:  
  
```cpp  
#include <malloc.h>  
  
void func(int size)  
{  
    void* p = nullptr;  
    if (size < 256) {  
        p = malloc(size);  
    }  
  
    if (p != nullptr)  
        free(p);  
}  
  
void main()  
{  
    func(9);  
}  
```  
  
## 参照  
 [コンパイラの警告 \(レベル 4\) C4701](../../error-messages/compiler-warnings/compiler-warning-level-4-c4701.md)   
 [警告、\/sdl、初期化されていない変数検出が向上します。](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)