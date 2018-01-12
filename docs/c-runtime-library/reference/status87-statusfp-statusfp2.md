---
title: "_status87、_statusfp、_statusfp2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _statusfp2
- _statusfp
- _status87
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _statusfp2
- _statusfp
- statusfp2
- _status87
- status87
- statusfp
dev_langs: C++
helpviewer_keywords:
- floating-point functions, getting status word
- floating-point numbers, status word
- status87 function
- status word, getting floating point
- statusfp function
- _statusfp function
- _statusfp2 function
- statusfp2 function
- _status87 function
- floating-point functions
- status word
ms.assetid: 7ef963fa-b1fb-429d-94d6-fbf282ab7432
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7124b8236550f9e86e04ac56460426a080f137b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="status87-statusfp-statusfp2"></a>_status87、_statusfp、_statusfp2
浮動小数点ステータス ワードを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _status87( void );  
unsigned int _statusfp( void );  
void _statusfp2(unsigned int *px86, unsigned int *pSSE2)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `px86`  
 このアドレスには、x87 浮動小数点ユニットのステータス ワードが格納されます。  
  
 `pSSE2`  
 このアドレスには、SSE2 浮動小数点ユニットのステータス ワードが格納されます。  
  
## <a name="return-value"></a>戻り値  
 `_status87` および `_statusfp` の戻り値のビットは浮動小数点のステータスを示します。 `_statusfp` から返されるビットの定義の詳細については、FLOAT.H インクルード ファイルを参照してください。 多くの数値演算ライブラリ関数は、予測できない結果を使用して浮動小数点ステータス ワードを変更します。 最適化では、`_status87`、`_statusfp`、および関連する関数の呼び出しの周囲の浮動小数点演算を順序変更、結合、および除去できます。 浮動小数点演算の順序を変更する最適化を防ぐには、[/Od (無効 (デバッグ))](../../build/reference/od-disable-debug.md) コンパイラ オプションまたは [fenv_access](../../preprocessor/fenv-access.md) プラグマ ディレクティブを使用します。 浮動小数点ステータス ワードの既知の状態間で浮動小数点演算がほとんど実行されていない場合は、`_clearfp` および `_statusfp` からの戻り値と、`_statusfp2` の戻り値パラメーターの信頼性が高くなります。  
  
## <a name="remarks"></a>コメント  
 `_statusfp` 関数は浮動小数点ステータス ワードを取得します。 ステータス ワードとは、浮動小数点例外によって検出された浮動小数点プロセッサのステータスやその他の条件 (浮動小数点スタック オーバーフローおよびアンダーフローなど) の組み合わせです。 マスクされていない例外は、ステータス ワードのコンテンツが返される前にチェックされます。 これは、呼び出し元に保留中の例外を通知することを意味します。 x86 プラットフォームでは、`_statusfp` は x87 と SSE2 浮動小数点のステータスの組み合わせを返します。 x64 プラットフォームでは、返される状態は、SSE の MXCSR の状態に基づいています。 ARM プラットフォームでは、`_statusfp` は FPSCR レジスタからステータスを返します。  
  
 `_statusfp` は、`_status87` の移植性の高いバージョンで、プラットフォームに依存しません。 これは Intel (x86) プラットフォームの `_status87` と同じで、x64 および ARM の各プラットフォームでもサポートされます。 浮動小数点コードをすべてのアーキテクチャに確実に移植するには、`_statusfp` を使用します。 x86 プラットフォームのみを対象とする場合は、`_status87` または `_statusfp` を使用します。  
  
 x87 および SSE2 浮動小数点プロセッサの両方を持つチップ (Pentium IV など) には `_statusfp2` をお勧めします。 `_statusfp2` の場合、アドレスは x87 または SSE2 浮動小数点プロセッサの両方に対して浮動小数点ステータス ワードを使用して入力されます。 x87 および SSE2 の各浮動小数点プロセッサをサポートするチップについては、x87 または SSE2 の浮動小数点ステータス ワードを参照している可能性があるため、`_statusfp` または `_controlfp` が使用されていて、操作があいまいな場合は、EM_AMBIGUOUS が 1 に設定されます。 `_statusfp2` 関数は、x86 プラットフォームでのみサポートされます。  
  
 これらの関数に不要な[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) には、既定の浮動小数点精度のみがサポートされるためです。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_status87`、`_statusfp`、`_statusfp2`|\<float.h>|  
  
 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
Status = 0x00000000 - clear  
Status = 0x00000003 - inexact, underflow  
Status = 0x00080003 - inexact, underflow, denormal  
```  
  
## <a name="see-also"></a>参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_clear87、_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)