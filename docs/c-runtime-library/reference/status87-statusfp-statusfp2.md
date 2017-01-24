---
title: "_status87、_statusfp、_statusfp2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_statusfp2"
  - "_statusfp"
  - "_status87"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_statusfp2"
  - "_statusfp"
  - "statusfp2"
  - "_status87"
  - "status87"
  - "statusfp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "浮動小数点関数、取得 (ステータス ワードを)"
  - "浮動小数点数、ステータス ワード"
  - "status87 関数"
  - "ステータス ワード、取得 (浮動小数点を)"
  - "statusfp 関数"
  - "_statusfp 関数"
  - "_statusfp2 関数"
  - "statusfp2 関数"
  - "_status87 関数"
  - "浮動小数点関数"
  - "ステータス ワード"
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _status87、_statusfp、_statusfp2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点ステータス ワードを取得します。  
  
## 構文  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### パラメーター  
 `px86`  
 このアドレスには、x87 浮動小数点ユニットのステータス ワードが格納されます。  
  
 `pSSE2`  
 このアドレスには、SSE2 浮動小数点ユニットのステータス ワードが格納されます。  
  
## 戻り値  
 `_status87` および `_statusfp` の戻り値のビットは浮動小数点のステータスを示します。  `_statusfp` から返されるビットの定義の詳細については、FLOAT.H インクルード ファイルを参照してください。  多くの数値演算ライブラリ関数は、予測できない結果を使用して浮動小数点ステータス ワードを変更します。  最適化では、`_status87`、`_statusfp`、および関連する関数の呼び出しの周囲の浮動小数点演算を順序変更、結合、および除去できます。  浮動小数点演算の順序を変更する最適化を防ぐには、[\/Od \(無効 \(デバッグ\)\)](../../build/reference/od-disable-debug.md) コンパイラ オプションまたは [fenv\_access](../../preprocessor/fenv-access.md) プラグマ ディレクティブを使用します。  浮動小数点ステータス ワードの既知の状態間で浮動小数点演算がほとんど実行されていない場合は、`_clearfp` および `_statusfp` からの戻り値と、`_statusfp2` の戻り値パラメーターの信頼性が高くなります。  
  
## 解説  
 `_statusfp` 関数は浮動小数点ステータス ワードを取得します。  ステータス ワードとは、浮動小数点例外によって検出された浮動小数点プロセッサのステータスやその他の条件 \(浮動小数点スタック オーバーフローおよびアンダーフローなど\) の組み合わせです。  マスクされていない例外は、ステータス ワードのコンテンツが返される前にチェックされます。  これは、呼び出し元に保留中の例外を通知することを意味します。  x86 プラットフォームでは、`_statusfp` は x87 と SSE2 浮動小数点のステータスの組み合わせを返します。  x64 プラットフォームでは、返される状態は、SSE の MXCSR の状態に基づいています。  ARM プラットフォームでは、`_statusfp` は FPSCR レジスタからステータスを返します。  
  
 `_statusfp` は、`_status87` の移植性の高いバージョンで、プラットフォームに依存しません。  これは Intel \(x86\) プラットフォームの `_status87` と同じで、x64 および ARM の各プラットフォームでもサポートされます。  浮動小数点コードをすべてのアーキテクチャに確実に移植するには、`_statusfp` を使用します。  x86 プラットフォームのみを対象とする場合は、`_status87` または `_statusfp` を使用します。  
  
 x87 および SSE2 浮動小数点プロセッサの両方を持つチップ \(Pentium IV など\) には `_statusfp2` をお勧めします。  `_statusfp2` の場合、アドレスは x87 または SSE2 浮動小数点プロセッサの両方に対して浮動小数点ステータス ワードを使用して入力されます。  x87 および SSE2 の各浮動小数点プロセッサをサポートするチップについては、x87 または SSE2 の浮動小数点ステータス ワードを参照している可能性があるため、`_statusfp` または `_controlfp` が使用されていて、操作があいまいな場合は、EM\_AMBIGUOUS が 1 に設定されます。  `_statusfp2` 関数は、x86 プラットフォームでのみサポートされます。  
  
 共通言語ランタイム \(CLR\) は浮動小数点の既定の精度のみをサポートするので、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) または `/clr:pure` を使用してコンパイルする場合、これらの関数は役に立ちません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_status87`, `_statusfp`, `_statusfp2`|\<float.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_statusfp.c  
// Build by using: cl /W4 /Ox /nologo crt_statusfp.c  
// This program creates various floating-point errors and  
// then uses _statusfp to display messages that indicate these problems.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access(on)  
  
double test( void )  
{  
   double a = 1e-40;  
   float b;  
   double c;  
  
   printf("Status = 0x%.8x - clear\n", _statusfp());  
  
   // Assignment into b is inexact & underflows:   
   b = (float)(a + 1e-40);  
   printf("Status = 0x%.8x - inexact, underflow\n", _statusfp());  
  
   // c is denormal:   
   c = b / 2.0;   
   printf("Status = 0x%.8x - inexact, underflow, denormal\n",   
            _statusfp());  
  
   // Clear floating point status:   
   _clearfp();  
   return c;  
}  
  
int main(void)  
{  
   return (int)test();  
}  
```  
  
  **Status \= 0x00000000 \- clear**  
**Status \= 0x00000003 \- inexact, underflow**  
**Status \= 0x00080003 \- inexact, underflow, denormal**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_clear87、\_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)