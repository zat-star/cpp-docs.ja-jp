---
title: "_control87、_controlfp、__control87_2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _control87
- _controlfp
- __control87_2
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
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
dev_langs:
- C++
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
caps.latest.revision: 34
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
ms.openlocfilehash: 25dfd357f0b3385f1e9bdcc4249ad3cf4399e0b6
ms.contentlocale: ja-jp
ms.lasthandoff: 02/28/2017

---
# <a name="control87-controlfp-control872"></a>_control87、_controlfp、__control87_2
浮動小数点制御ワードの取得および設定を行います。 `_controlfp` のセキュリティが強化されたバージョンについては、「[_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned int _control87(   
   unsigned int new,  
   unsigned int mask   
);  
unsigned int _controlfp(   
   unsigned int new,  
   unsigned int mask   
);  
int __control87_2(  
   unsigned int new,  
   unsigned int mask,  
   unsigned int* x86_cw,  
   unsigned int* sse2_cw  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `new`  
 新しい制御ワードのビット値。  
  
 `mask`  
 新しく設定する制御ワード ビットのマスク。  
  
 `x86_cw`  
 x87 浮動小数点ユニットの制御ワードが格納されます。 SSE2 制御ワードのみを設定する場合は、0 (`NULL`) を渡します。  
  
 `sse2_cw`  
 SSE 浮動小数点ユニットの制御ワード。 x87 制御ワードのみを設定する場合は、0 (`NULL`) を渡します。  
  
## <a name="return-value"></a>戻り値  
 `_control87` と `_controlfp` の戻り値のビットは浮動小数点のコントロールの状態を示します。 `_control87` から返されるビットの定義の詳細については、FLOAT.H を参照してください。  
  
 `__control87_2` では、戻り値 1 は成功したことを意味します。  
  
## <a name="remarks"></a>コメント  
 `_control87` 関数は、浮動小数点制御ワードの取得と設定を行います。 浮動小数点制御ワードを使用すると、プログラムで使用する浮動小数点演算パッケージの精度、丸め、および無限大の各モードをプラットフォームに応じて変更できます。 `_control87` を使用して、浮動小数点例外のマスクの設定および解除を行うこともできます。 `mask` の値を 0 にすると、`_control87` は浮動小数点制御ワードを取得します。 `mask` の値を 0 以外にすると、制御ワードに新しい値が設定されます。`mask` でオン (つまり 1) のビットについては、`new` の対応するビットが制御ワードの更新に使用されます。 つまり、`fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) で、`fpcntrl` は浮動小数点制御ワードです。  
  
> [!NOTE]
>  既定では、ランタイム ライブラリは、すべての浮動小数点例外をマスクします。  
  
 `_controlfp` は、`_control87` の移植性の高いバージョンで、プラットフォームに依存しません。 この関数は、Intel (x86)、`_control87`、および ARM の各プラットフォームでは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 関数とほぼ同じです。 x86、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、または ARM の各プラットフォームを対象とする場合は、`_control87` または `_controlfp` を使用します。  
  
 `_control87` と `_controlfp` の違いは、DENORMAL 値の処理方法にあります。 Intel (x86)、[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]、および ARM の各プラットフォームでは、`_control87` を使用して DENORMAL OPERAND 例外マスクを設定および解除できます。 `_controlfp` は DENORMAL OPERAND 例外マスクを変更しません。 次の例に、この違いを示します。  
  
```  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call  
_controlfp( _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged  
```  
  
 マスク定数の対象となる値 (`mask`) および新しい制御値 (`new`) を以下の「16 進数の値」の表に示します。 2 つの関数の引数には、16 進数値を明示的に指定せずに、表に示すような移植性の高い定数 (`_MCW_EM`、`_EM_INVALID` など) を使用します。  
  
 Intel (x86) から派生したプラットフォームでは、DENORMAL 入出力値がハードウェアでサポートされています。 x86 では DENORMAL 値を保持するように動作します。 SSE2 をサポートしている ARM プラットフォームと [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームでは、DENORMAL オペランドと結果をフラッシュするか、強制的にゼロにすることができます。 `_controlfp` 関数と `_control87` 関数は、この動作を変更するマスクを使用します。 このマスクの使用例を次に示します。  
  
```  
_controlfp(_DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp(_DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM プラットフォームでは、`_control87` 関数と `_controlfp` 関数は FPSCR レジスタに適用されます。 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャでは、MXCSR レジスタに格納されている SSE2 制御ワードだけに影響します。 Intel (x86) プラットフォームでは、`_control87` と `_controlfp` は、存在する場合は x87 と SSE2 両方の制御ワードに影響します。 `__control87_2` 関数では、x87 と SSE2 の両方の浮動小数点ユニットを一緒に制御することも、個別に制御することもできます。 両方のユニットに影響を与える場合は、`x86_cw` と `sse2_cw` に対して 2 つの整数アドレスを渡します。 1 つのユニットにのみ影響を与えるには、影響を与えるパラメーターにはアドレスを渡し、他方には 0 (NULL) を渡します。 いずれかのパラメーターに対して 0 が渡されると、関数はその浮動小数点ユニットには影響しません。 この機能は、コードの一部では x87 浮動小数点ユニットを使用し、別の部分では SSE2 浮動小数点ユニットを使用する場合に役立ちます。 `__control87_2` 関数をプログラムの一部で使用し、さまざまな値を浮動小数点制御ワードに設定した後、さらに制御ワードを操作するために `_control87` 関数または `_controlfp` 関数を使用すると、`_control87` と `_controlfp` は両方の浮動小数点ユニットの状態を表す単一の制御ワードを返すことができない場合があります。 このような場合、これらの関数は `EM_AMBIGUOUS` フラグを整数の戻り値に設定し、2 つの制御ワードの間に矛盾があることを示します。 これは、返された制御ワードが両方の浮動小数点制御ワードの状態を正確に表していない可能性があるという警告です。  
  
 ARM アーキテクチャと [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャでは、無限大モードまたは浮動小数点の精度の変更はサポートされていません。 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] プラットフォームで精度の制御マスクが使用されている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、アサーションと無効なパラメーター ハンドラーが呼び出されます。  
  
> [!NOTE]
>  `__control87_2` は、ARM アーキテクチャまたは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャではサポートされていません。 `__control87_2` を使用して、ARM アーキテクチャまたは [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] アーキテクチャのプログラムをコンパイルした場合、コンパイラでエラーが生成されます。  
  
 使用すると、これらの関数は無視されます[/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)共通言語ランタイム (CLR) では、既定の浮動小数点精度のみがサポートするため、コンパイルします。  
  
 **16 進数の値**  
  
 `_MCW_EM` マスクに関しては、マスクを解除すると例外が設定されてハードウェア例外が許可されます。マスクを設定すると例外は無効になります。 `_EM_UNDERFLOW` または `_EM_OVERFLOW` が発生した場合は、次回の浮動小数点命令が実行されるまで、ハードウェア例外はスローされません。 `_EM_UNDERFLOW` または `_EM_OVERFLOW` の発生後すぐにハードウェア例外を生成するには、`FWAIT` MASM 命令を呼び出します。  
  
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
|`_control87`、`_controlfp`、`_control87_2`|\<float.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```C  
// crt_cntrl87.c  
// processor: x86  
// This program uses __control87_2 to output the x87 control   
// word, set the precision to 24 bits, and reset the status to   
// the default.  
  
#include <stdio.h>  
#include <float.h>  
#pragma fenv_access (on)  
  
int main( void )  
{  
    double a = 0.1;  
    unsigned int control_word_x87;  
  
    // Show original x87 control word and do calculation.  
    control_word_x87 = __control87_2(0, 0,  
                                     &control_word_x87, 0);  
    printf( "Original: 0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Set precision to 24 bits and recalculate.  
    control_word_x87 = __control87_2(_PC_24, MCW_PC,  
                                     &control_word_x87, 0);  
    printf( "24-bit:   0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
  
    // Restore default precision-control bits and recalculate.  
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,   
                                     &control_word_x87, 0 );  
    printf( "Default:  0x%.4x\n", control_word_x87 );  
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );  
}  
```  
  
```Output  
Original: 0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
24-bit:   0x0001  
0.1 * 0.1 = 9.999999776482582e-003  
Default:  0x0001  
0.1 * 0.1 = 1.000000000000000e-002  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_clear87、_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87、_statusfp、_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)
