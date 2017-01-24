---
title: "_clear87、_clearfp | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_clearfp"
  - "_clear87"
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
  - "clearfp"
  - "_clearfp"
  - "_clear87"
  - "clear87"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_clear87 関数"
  - "_clearfp 関数"
  - "clear87 関数"
  - "clearfp 関数"
  - "クリア (浮動小数点ステータス ワードを)"
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _clear87、_clearfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

浮動小数点ステータス ワードを取得し、クリアします。  
  
## 構文  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## 戻り値  
 返される値のビットは、`_clear87` または `_clearfp` の呼び出し前の浮動小数点ステータスを示します。  `_clear87` から返されるビットの定義の詳細については、Float.h を参照してください。  多くの数値演算ライブラリ関数は、8087\/80287 ステータス ワードを変更しますが、その結果は予測できません。  浮動小数点ステータス ワードの状態がわかっている範囲で実行される浮動小数点演算が少ないほど、`_clear87` および `_status87` の戻り値の信頼性が高くなります。  
  
## 解説  
 `_clear87` 関数は、浮動小数点ステータス ワードの例外フラグをクリアし、ビジー ビットを 0 に設定し、ステータス ワードを返します。  浮動小数点ステータス ワードは、8087\/80287 ステータス ワードと、8087\/80287 例外ハンドラーによって検出された浮動小数点スタック オーバーフローやアンダーフローなど、ほかの条件との組み合わせです。  
  
 `_clearfp` は、`_clear87` ルーチンの移植性の高いバージョンで、プラットフォームに依存しません。  これは Intel \(x86\) プラットフォームの `_clear87` と同じで、x64 および ARM の各プラットフォームでもサポートされます。  浮動小数点コードを x64 および ARM に対して確実に移植可能にするには、`_clearfp` を使用します。  x86 プラットフォームのみを対象とする場合は、`_clear87` または `_clearfp` を使用します。  
  
 共通言語ランタイムは浮動小数点の既定の精度のみをサポートするので、[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) または `/clr:pure` を使用してコンパイルする場合、これらの関数は使用しないでください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_clear87`|\<float.h\>|  
|`_clearfp`|\<float.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
  **Status: 0000 \- clear**  
**Status: 0003 \- inexact, underflow**  
**Status: 80000 \- denormal**   
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_control87、\_controlfp、\_\_control87\_2](../Topic/_control87,%20_controlfp,%20__control87_2.md)   
 [\_status87、\_statusfp、\_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)