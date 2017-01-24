---
title: "__ptr32、__ptr64 | Microsoft Docs"
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
  - "__ptr32_cpp"
  - "__ptr64_cpp"
  - "__ptr32"
  - "__ptr64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__ptr32 キーワード [C++]"
  - "__ptr64 キーワード [C++]"
  - "_ptr32 キーワード [C++]"
  - "_ptr64 キーワード [C++]"
  - "ptr32 キーワード [C++]"
  - "ptr64 キーワード [C++]"
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __ptr32、__ptr64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__ptr32` は 32 ビット システムのネイティブ ポインターを表し、`__ptr64` は、64 ビット システムのネイティブ ポインターを表します。  
  
 次の例は、これらのポインター型のそれぞれを宣言する方法を示します。  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 32 ビット システムでは、`__ptr64` で宣言されたポインターは 32 ビット ポインターに切り詰められます。  64 ビット システムでは、`__ptr32` で宣言されたポインターは 64 ビットのポインター型に変換されます。  
  
> [!NOTE]
>  `__ptr32` によるコンパイル中は、`__ptr64` も **\/clr:pure** も使用できません。  それ以外の場合は、`Compiler Error C2472` が生成されます。  
  
## 使用例  
 次の例は、`__ptr32` キーワードと `__ptr64` キーワードを持つポインターを宣言して割り当てる方法を示します。  
  
```  
#include <cstdlib>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    int * __ptr32 p32;  
    int * __ptr64 p64;  
  
    p32 = (int * __ptr32)malloc(4);  
    *p32 = 32;  
    cout << *p32 << endl;  
  
    p64 = (int * __ptr64)malloc(4);  
    *p64 = 64;  
    cout << *p64 << endl;  
}  
```  
  
  **32**  
**64**   
## END Microsoft 固有の仕様  
  
## 参照  
 [基本型](../cpp/fundamental-types-cpp.md)