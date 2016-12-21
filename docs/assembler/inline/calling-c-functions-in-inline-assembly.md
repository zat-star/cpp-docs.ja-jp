---
title: "インライン アセンブリでの C 関数の呼び出し | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm キーワード [C++], 呼び出し (関数を)"
  - "関数呼び出し, C 関数"
  - "関数呼び出し, インライン アセンブラー内"
  - "関数 [C], インライン アセンブラー内での呼び出し"
  - "インライン アセンブラー, 呼び出し (関数を)"
  - "Visual C, 関数"
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリでの C 関数の呼び出し
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 `__asm` ブロックは C ライブラリ ルーチンを含めて C 関数を呼び出すことができます。  次の例では `printf` ライブラリ ルーチンを呼び出します :  
  
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
  
 関数の引数がスタックに渡されるため\) は関数を呼び出す前に必要な引数 \(上の例の文字列ポインター単にキーを押します。  引数は逆順にプッシュされます。したがって指定した順序でスタックから取れます。  C のステートメントをエミュレートします。  
  
```  
printf( format, hello, world );  
```  
  
 `world` 例では`hello` と `format` へのポインターをこの順序で押してから`printf` を呼び出します。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [インライン アセンブラー](../../assembler/inline/inline-assembler.md)