---
title: "_clear87、_clearfp | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _clearfp
- _clear87
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
- clearfp
- _clearfp
- _clear87
- clear87
dev_langs:
- C++
helpviewer_keywords:
- clearing floating point status word
- clearfp function
- _clear87 function
- _clearfp function
- clear87 function
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 7c7659bb52594678538ea2701174c070ace41d70
ms.lasthandoff: 02/24/2017

---
# <a name="clear87-clearfp"></a>_clear87、_clearfp
浮動小数点ステータス ワードを取得し、クリアします。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## <a name="return-value"></a>戻り値  
 返される値のビットは、`_clear87` または `_clearfp` の呼び出し前の浮動小数点ステータスを示します。 `_clear87` から返されるビットの定義の詳細については、Float.h を参照してください。 多くの数値演算ライブラリ関数は、8087/80287 ステータス ワードを変更しますが、その結果は予測できません。 浮動小数点ステータス ワードの状態がわかっている範囲で実行される浮動小数点演算が少ないほど、`_clear87` および `_status87` の戻り値の信頼性が高くなります。  
  
## <a name="remarks"></a>コメント  
 `_clear87` 関数は、浮動小数点ステータス ワードの例外フラグをクリアし、ビジー ビットを 0 に設定し、ステータス ワードを返します。 浮動小数点ステータス ワードは、8087/80287 ステータス ワードと、8087/80287 例外ハンドラーによって検出された浮動小数点スタック オーバーフローやアンダーフローなど、ほかの条件との組み合わせです。  
  
 `_clearfp` は、`_clear87` ルーチンの移植性の高いバージョンで、プラットフォームに依存しません。 これは Intel (x86) プラットフォームの `_clear87` と同じで、x64 および ARM の各プラットフォームでもサポートされます。 浮動小数点コードを x64 および ARM に対して確実に移植可能にするには、`_clearfp` を使用します。 x86 プラットフォームのみを対象とする場合は、`_clear87` または `_clearfp` を使用します。  
  
 コンパイルすると、これらの関数は使用されなくなりました。 [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md) 、共通言語ランタイムでは、浮動小数点の既定の精度のみがサポートされるためです。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_clear87`|\<float.h>|  
|`_clearfp`|\<float.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
Status: 0000 - clear  
Status: 0003 - inexact, underflow  
Status: 80000 - denormal  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 該当なし。 標準 C 関数を呼び出すには、 `PInvoke`を使用します。 詳細については、「[プラットフォーム呼び出しの例](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f)」をご覧ください。  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_status87、_statusfp、_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)
