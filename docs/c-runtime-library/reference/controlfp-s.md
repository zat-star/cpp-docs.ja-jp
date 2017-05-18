---
title: _controlfp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _controlfp_s
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
- controlfp_s
- _controlfp_s
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: 28
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 4345539f7ecd836280bed94c4bb2b125dfa08107
ms.contentlocale: ja-jp
ms.lasthandoff: 02/28/2017

---
# <a name="controlfps"></a>_controlfp_s
浮動小数点制御ワードの取得および設定を行います。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `currentControl`  
 現在の制御ワードのビット値。  
  
 `newControl`  
 新しい制御ワードのビット値。  
  
 `mask`  
 新しく設定する制御ワード ビットのマスク。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返し、失敗した場合は `errno` 値のエラー コードを返します。  
  
## <a name="remarks"></a>コメント  
 `_controlfp_s` 関数は、`_control87` 関数のセキュリティが強化された、プラットフォームに依存しないバージョンであり、浮動小数点制御ワードを取得して `currentControl` に格納されたアドレスに格納し、`newControl` を使用して浮動小数点制御ワードを設定します。 この値のビットは、浮動小数点のコントロールの状態を示します。 浮動小数点のコントロールの状態を使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 `_controlfp_s` を使用して、浮動小数点例外のマスクの設定および解除を行うこともできます。  
  
 `mask` の値を 0 にすると、`_controlfp_s` は浮動小数点制御ワードを取得し、その取得した値を `currentControl` に格納します。  
  
 `mask` の値を 0 以外にすると、制御ワードに新しい値が設定されます。`mask` のビットのいずれかを設定 (つまり 1 に) すると、`new` の対応するビットが制御ワードの更新に使用されます。 つまり、`fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) で、`fpcntrl` は浮動小数点制御ワードです。 この場合、変更が完了してから `currentControl` に値が設定されるため、古い制御ワードのビット値ではありません。  
  
> [!NOTE]
>  既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。  
  
 `_controlfp_s` は、Intel (x86)、`_control87`、および ARM のプラットフォームでは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 関数とほぼ同じです。 x86、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、または ARM プラットフォームを対象とする場合は、`_control87` 関数、または `_controlfp_s` 関数を使用します。  
  
 `_control87` と `_controlfp_s` との違いは、`DENORMAL` 値の処理方法にあります。 Intel (x86)、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、および ARM の各プラットフォームでは、`_control87` を使用して DENORMAL OPERAND 例外マスクを設定および解除できます。 `_controlfp_s` は DENORMAL OPERAND 例外マスクを変更しません。 次の例に、この違いを示します。  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 マスク定数の対象となる値 (`mask`) および新しい制御値 (`newControl`) を以下の「16 進数の値」の表に示します。 2 つの関数の引数には、16 進数値を明示的に指定せずに、表に示すような移植性の高い定数 (`_MCW_EM`、`_EM_INVALID` など) を使用します。  
  
 Intel (x86) から派生したプラットフォームでは、DENORMAL 入出力値がハードウェアでサポートされています。 x86 では DENORMAL 値を保持するように動作します。 SSE2 をサポートしている ARM プラットフォームと [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームでは、DENORMAL オペランドと結果をフラッシュするか、強制的にゼロにすることができます。 `_controlfp_s` 関数、`_controlfp` 関数、および `_control87` 関数は、この動作を変更するマスクを使用します。 このマスクの使用例を次に示します。  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM のプラットフォームでは、`_controlfp_s` 関数は FPSCR の登録に適用されます。 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャでは、MXCSR レジスタに格納されている SSE2 制御ワードだけに影響します。 Intel (x86) プラットフォームでは、`_controlfp_s` 関数は、存在する場合は x87 と SSE2 の両方の制御ワードに影響します。 直前の [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) 呼び出しなどにより、2 つの制御ワードが食い違ってしまう可能性もあります。2 つの制御ワード間で不整合が生じた場合、`_controlfp_s` により、`currentControl` に `EM_AMBIGUOUS` フラグが設定されます。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。  
  
 ARM アーキテクチャと [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャでは、無限大モードまたは浮動小数点の精度の変更はサポートされていません。 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームで精度の制御マスクが使用されている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、アサーションと無効なパラメーター ハンドラーが呼び出されます。  
  
 マスクが正しく設定されていないと、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーターの例外を生成します。 実行の継続が許可された場合、この関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
 使用する場合、この関数は無視されます[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) では、既定の浮動小数点精度のみがサポートするため、コンパイルします。  
  
### <a name="mask-constants-and-values"></a>マスク定数と値  
  
 `_MCW_EM` マスクに関しては、マスクを解除すると例外が設定されてハードウェア例外が許可されます。マスクを設定すると例外は無効になります。 `_EM_UNDERFLOW` または `_EM_OVERFLOW` が発生した場合は、次回の浮動小数点命令が実行されるまで、ハードウェア例外はスローされません。 `_EM_UNDERFLOW` または `_EM_OVERFLOW` の発生後すぐにハードウェア例外を生成するには、FWAIT MASM 命令を呼び出します。  
  
|マスク|16 進値|定数|16 進値|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN` (DENORMAL 制御)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM` (割り込み例外マスク)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC` (無限制御)<br /><br /> (ARM プラットフォームまたは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームではサポートされていません。)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC` (丸め制御)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC` (精度制御)<br /><br /> (ARM プラットフォームまたは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームではサポートされていません。)|0x00030000|`_PC_24` (24 ビット)<br /><br /> `_PC_53` (53 ビット)<br /><br /> `_PC_64` (64 ビット)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_controlfp_s`|\<float.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```C  
// crt_contrlfp_s.c  
// processor: x86  
// This program uses _controlfp_s to output the FP control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word;  
    int err;  
  
    // Show original FP control word and do calculation.  
    err = _controlfp_s(&control_word, 0, 0);  
    if ( err ) /* handle error here */;  
  
    printf( "Original: 0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "24-bit:   0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);  
    if ( err ) /* handle error here */;  
  
    printf( "Default:  0x%.4x\n", control_word );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0xa001f  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x9001f  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_clear87、_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87、_statusfp、_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)
