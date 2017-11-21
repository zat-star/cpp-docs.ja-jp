---
title: "インライン アセンブリでは関数を呼び出して C |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- function calls, C functions
- function calls, in inline assembly
- functions [C], calling in inline assembly
- Visual C, functions
- inline assembly, calling functions
- __asm keyword [C++], calling functions
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3cd162026792bf8458c3725011b583d1eeb00772
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="calling-c-functions-in-inline-assembly"></a>インライン アセンブリでの C 関数の呼び出し
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 `__asm`ブロックは、C のライブラリ ルーチンを含む、C 関数を呼び出すことができます。 次の例では、`printf`ライブラリ ルーチン。  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 単に必要な引数をプッシュする関数の引数はスタックで渡される、ため — 文字列ポインターは、前の例で、関数を呼び出す前にします。 引数は、目的の順序でスタックから送られてきたので逆の順序では、プッシュされます。 C ステートメントをエミュレートするために  
  
```  
printf( format, hello, world );  
```  
  
 例では、プッシュへのポインター `world`、 `hello`、および`format`、その順序、および呼び出し`printf`です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)