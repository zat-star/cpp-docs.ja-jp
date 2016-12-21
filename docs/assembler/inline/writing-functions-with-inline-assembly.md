---
title: "インライン アセンブリでの関数の記述 | Microsoft Docs"
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
  - "__asm キーワード [C++], 関数内"
  - "アセンブラー [C++], 書き込み関数"
  - "関数 [C++], インライン アセンブラー"
  - "インライン アセンブラー [C++], 書き込み関数"
ms.assetid: b5df8a04-fdc7-4622-8c9e-e4b618927497
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# インライン アセンブリでの関数の記述
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft 固有の仕様 →  
 インライン アセンブラー コードの関数を作成する場合は引数を関数に渡しそこから値を返すことができます。  次の例ではまず別のアセンブラーで記述されインライン アセンブラーのように書き換える関数を比較します。  `power2` と呼ばれる関数は2 番目2 の累乗で最初のパラメーターを増やす 2 個のパラメーターを受け取ります。  別のアセンブラーで書き込まれました\) と関数は次のような可能性があります :  
  
```  
; POWER.ASM  
; Compute the power of an integer  
;  
       PUBLIC _power2  
_TEXT SEGMENT WORD PUBLIC 'CODE'  
_power2 PROC  
  
        push ebp        ; Save EBP  
        mov ebp, esp    ; Move ESP into EBP so we can refer  
                        ;   to arguments on the stack  
        mov eax, [ebp+4] ; Get first argument  
        mov ecx, [ebp+6] ; Get second argument  
        shl eax, cl     ; EAX = EAX * ( 2 ^ CL )  
        pop ebp         ; Restore EBP  
        ret             ; Return with sum in EAX  
  
_power2 ENDP  
_TEXT   ENDS  
        END  
```  
  
 これはアセンブラーで作成したので関数のソース ファイルとアセンブリとリンクの手順が必要になります。  C および C\+\+ の関数の引数はスタックの場所を `power2` の関数のアクセスのスタックこのバージョンで引数が渡されます。  MASM \(メモ  **モデル**  のディレクティブと使用できるほかにもアセンブラーはスタックの引数とローカル スタック変数を名前でアクセスできます\)。  
  
## 使用例  
 このプログラムはインライン アセンブラー コードの `power2` の関数を作成します :  
  
```  
// Power2_inline_asm.c  
// compile with: /EHsc  
// processor: x86  
  
#include <stdio.h>  
  
int power2( int num, int power );  
  
int main( void )  
{  
    printf_s( "3 times 2 to the power of 5 is %d\n", \  
              power2( 3, 5) );  
}  
int power2( int num, int power )  
{  
   __asm  
   {  
      mov eax, num    ; Get first argument  
      mov ecx, power  ; Get second argument  
      shl eax, cl     ; EAX = EAX * ( 2 to the power of CL )  
   }  
   // Return with result in EAX  
}  
```  
  
 `power2` の関数のインライン バージョンは引数を名前であり同じソース ファイルでのプログラムが表示されます。  このバージョンにはいくつかのアセンブリ命令が必要です。  
  
 `power2` のインライン バージョンは. `return` のステートメントを実行しないので警告レベル 2 またはそれより上でコンパイルすると思われる警告が発生します。  関数は値を返しますがコンパイラは `return` のステートメントが存在しない場合を通知することはできません。  この警告の生成を無効にするに [\#pragma warning](../../preprocessor/warning.md) を使用できます。  
  
 **終了 Microsoft 固有の仕様→**  
  
## 参照  
 [\_\_asm ブロックでの C または C\+\+ の使用](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)