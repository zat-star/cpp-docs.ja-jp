---
title: _ _sptr、_ _uptr |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- __uptr_cpp
- __sptr_cpp
dev_langs:
- C++
helpviewer_keywords:
- __sptr modifier
- __uptr modifier
ms.assetid: c7f5f3b2-9106-4a0b-a6de-d1588ab153ed
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: daa431204c66def272d07fc0b670dc279e1569ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sptr-uptr"></a>__sptr、__uptr
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 コンパイラが 32 ビット ポインターを 64 ビット ポインターへどのように変換するかを指定するには、32 ビット ポインター宣言で `__sptr` または `__uptr` 修飾子を使用します。 たとえば、32 ビット ポインターが 64 ビット ポインター変数に割り当てられたときや、64 ビット プラットフォーム上で 32 ビット ポインターが逆参照される場合などに変換が必要になります。  
  
 64 ビット プラットフォームをサポートする Microsoft のドキュメントでは、32 ビット ポインターの最上位ビットを符号ビットと呼んでいる場合があります。 既定では、コンパイラは符号拡張を使用して 32 ビット ポインターを 64 ビット ポインターに変換します。 つまり、64 ビット ポインターの下位 32 ビットに 32 ビット ポインターの値が設定され、上位 32 ビットに 32 ビット ポインターの符号ビットの値が設定されます。 符号ビットが 0 の場合はこの変換で正しい結果が得られますが、符号ビットが 1 の場合は正しい結果が得られません。 たとえば、32 ビット アドレス 0x7FFFFFFF はこれと同等の 64 ビットアドレス 0x000000007FFFFFFF になりますが、32 ビット アドレス 0x80000000 は誤って 0xFFFFFFFF80000000 に変換されます。  
  
 `__sptr` (符号付きポインター) 修飾子を指定すると、ポインター変換で 64 ビット ポインターの上位ビットが 32 ビット ポインターの符号ビットに設定されます。 `__uptr` (符号なしポインター) 修飾子を指定すると、上位ビットが 0 に変換されます。 次の宣言のスライド ショー、`__sptr`と`__uptr`で修飾されていない 2 つのポインターと共に使用する修飾子は、2 つのポインターを修飾、 [_ _ptr32](../cpp/ptr32-ptr64.md)型、および関数のパラメーターです。  
  
```  
int * __sptr psp;  
int * __uptr pup;  
int * __ptr32 __sptr psp32;  
int * __ptr32 __uptr pup32;  
void MyFunction(char * __uptr __ptr32 myValue);  
```  
  
 `__sptr` 修飾子と `__uptr` 修飾子はポインター宣言で使用します。 位置に、修飾子を使用して、[ポインター型修飾子](../c-language/pointer-declarations.md)、つまり、修飾子は、アスタリスクを従う必要があります。 これらの修飾子を使用することはできません[メンバーへのポインター](../cpp/pointers-to-members.md)です。 これらの修飾子は、ポインター以外の宣言には影響を与えません。  
  
## <a name="example"></a>例  
 次の例では、`__sptr` 修飾子と `__uptr` 修飾子を使用する 32 ビット ポインターを宣言しています。各 32 ビット ポインターが 64 ビット ポインター変数に代入され、各 64 ビット ポインターの 16 進値が表示されます。 この例はネイティブの 64 ビット コンパイラでコンパイルされ、64 ビット プラットフォームで実行されます。  
  
```cpp  
// sptr_uptr.cpp  
// processor: x64  
#include "stdio.h"  
  
int main()  
{  
    void *        __ptr64 p64;  
    void *        __ptr32 p32d; //default signed pointer  
    void * __sptr __ptr32 p32s; //explicit signed pointer  
    void * __uptr __ptr32 p32u; //explicit unsigned pointer  
  
// Set the 32-bit pointers to a value whose sign bit is 1.  
    p32d = reinterpret_cast<void *>(0x87654321);  
    p32s = p32d;  
    p32u = p32d;  
  
// The printf() function automatically displays leading zeroes with each 32-bit pointer. These are unrelated   
// to the __sptr and __uptr modifiers.   
    printf("Display each 32-bit pointer (as an unsigned 64-bit pointer):\n");  
    printf("p32d:       %p\n", p32d);   
    printf("p32s:       %p\n", p32s);  
    printf("p32u:       %p\n", p32u);  
  
    printf("\nDisplay the 64-bit pointer created from each 32-bit pointer:\n");  
    p64 = p32d;   
    printf("p32d: p64 = %p\n", p64);  
    p64 = p32s;  
    printf("p32s: p64 = %p\n", p64);  
    p64 = p32u;  
    printf("p32u: p64 = %p\n", p64);  
    return 0;  
}  
```  
  
```Output  
Display each 32-bit pointer (as an unsigned 64-bit pointer):  
p32d:       0000000087654321  
p32s:       0000000087654321  
p32u:       0000000087654321  
  
Display the 64-bit pointer created from each 32-bit pointer:  
p32d: p64 = FFFFFFFF87654321  
p32s: p64 = FFFFFFFF87654321  
p32u: p64 = 0000000087654321  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [Microsoft 固有の修飾子](../cpp/microsoft-specific-modifiers.md)