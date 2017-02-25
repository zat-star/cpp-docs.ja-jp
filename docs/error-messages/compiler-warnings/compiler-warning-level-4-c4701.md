---
title: "コンパイラの警告 (レベル 4) C4701 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4701"
ms.assetid: d7c76c66-1f3f-4d3c-abe4-5d94c84a5a1f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラの警告 (レベル 4) C4701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

使用される可能性があり、初期化されていないローカル変数「name」  
  
 ローカル変数 *name* 操作で値が使用されることがあります。  この場合、予期しない結果が生じる可能性があります。  
  
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
 [コンパイラの警告 \(レベル 4\) C4703](../../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md)   
 [警告、\/sdl および改善は変数を検出初期化前の状態に戻しました](http://blogs.msdn.com/b/sdl/archive/2012/06/06/warnings-sdl-and-improving-uninitialized-variable-detection.aspx)