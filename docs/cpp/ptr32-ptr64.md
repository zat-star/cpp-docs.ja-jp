---
title: "_ _ptr32、_ _ptr64 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __ptr32_cpp
- __ptr64_cpp
dev_langs:
- C++
helpviewer_keywords:
- __ptr64 keyword [C++]
- _ptr32 keyword [C++]
- ptr32 keyword [C++]
- ptr64 keyword [C++]
- _ptr64 keyword [C++]
- __ptr32 keyword [C++]
ms.assetid: afb563d8-7458-4fe7-9c30-bd4b5385a59f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e811999bacada521d77bc14b19eb86d660b5901
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ptr32-ptr64"></a>__ptr32、__ptr64
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__ptr32` は 32 ビット システムのネイティブ ポインターを表し、`__ptr64` は、64 ビット システムのネイティブ ポインターを表します。  
  
 次の例は、これらのポインター型のそれぞれを宣言する方法を示します。  
  
```  
int * __ptr32 p32;  
int * __ptr64 p64;  
```  
  
 32 ビット システムでは、`__ptr64` で宣言されたポインターは 32 ビット ポインターに切り詰められます。 64 ビット システムでは、`__ptr32` で宣言されたポインターは 64 ビットのポインター型に変換されます。  
  
> [!NOTE]
>  使用することはできません`__ptr32`または`__ptr64`でコンパイルするときに**/clr: 純粋な**します。 それ以外の場合は、`Compiler Error C2472` が生成されます。 コンパイラ オプションの **/clr:pure** と **/clr:safe** は Visual Studio 2015 で使用されていません。  
  
## <a name="example"></a>例  
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
  
```Output  
32  
64  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [基本型](../cpp/fundamental-types-cpp.md)