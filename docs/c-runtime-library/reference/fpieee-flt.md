---
title: "_fpieee_flt | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpieee_flt
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
- fpieee_flt
- _fpieee_flt
dev_langs:
- C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c2e9f909f3e7e778845d8fefebe5d8b1604af489
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="fpieeeflt"></a>_fpieee_flt
IEEE 浮動小数点例外用のユーザー定義トラップ ハンドラーを呼び出します。  
  
## <a name="syntax"></a>構文  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `excCode`  
 例外コード。  
  
 `excInfo`  
 Windows NT 例外情報構造体へのポインター。  
  
 `handler`  
 ユーザーの IEEE トラップ ハンドラー ルーチンへのポインター。  
  
## <a name="return-value"></a>戻り値  
 `_fpieee_flt` の戻り値は、`handler` によって返される値です。 そのため、構造化例外処理 (SEH) 機構の except 句で IEEE フィルター ルーチンが使用される場合があります。  
  
## <a name="remarks"></a>コメント  
 `_fpieee_flt` 関数は、IEEE 浮動小数点例外用のユーザー定義トラップ ハンドラーを呼び出し、このハンドラーにすべての関連情報を渡します。 このルーチンは SEH 機構の例外フィルターとして機能し、必要に応じて独自の IEEE 例外ハンドラーが呼び出されます。  
  
 Fpieee.h で定義されている `_FPIEEE_RECORD` 構造体には、IEEE 浮動小数点例外に関する情報が含まれています。 この構造体は、`_fpieee_flt` によってユーザー定義トラップ ハンドラーに渡されます。  
  
|_FPIEEE_RECORD フィールド|説明|  
|----------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|これらのフィールドには、例外発生時の浮動小数点環境に関する情報が含まれています。|  
|`unsigned int Operation`|トラップを発生させた操作の種類を示します。 種類が比較 (`_FpCodeCompare`) の場合は、`_FPIEEE_COMPARE_RESULT` フィールドに特別な `Result.Value` 値 (Fpieee.h 内で定義) のいずれかを指定できます。 変換の種類 (`_FpCodeConvert`) は、浮動小数点変換の操作中にトラップが発生したことを示します。 `Operand1` と `Result` の種類を確認して、試行する変換の種類を決めることができます。|  
|`_FPIEEE_VALUE Operand1`、`_FPIEEE_VALUE Operand2`、`_FPIEEE_VALUE Result`|これらの構造体は、提案された結果とオペランドの型と値を示しています。<br /><br /> `OperandValid` 応答の値が有効であるかどうかを示すフラグ。<br /><br /> `Format` 対応する値のデータ型。 対応する値が有効でなくても、形式の種類が返されることがあります。<br /><br /> `Value` 結果またはオペランドのデータ値。|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`、`_FPIEEE_EXCEPTION_FLAGS Enable`、`_FPIEEE_EXCEPTION_FLAGS Status`|_FPIEEE_EXCEPTION_FLAGS には、浮動小数点例外の種類ごとに 1 つのビット フィールドが含まれています。<br /><br /> これらのフィールドと、[_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) に指定される例外をマスクするために使用される引数との間には対応関係があります。<br /><br /> 各ビットの正確な意味はコンテキストに依存します。<br /><br /> `Cause` 設定されている各ビットは、発生した特定の例外を示します。<br /><br /> `Enable` 設定されている各ビットは、特定の例外が現在はマスクされていないことを示します。<br /><br /> `Status` 設定されている各ビットは、特定の例外が現在は保留中であることを示します。 これには発生しなかった例外が含まれます。それらが `_controlfp` によってマスクされるためです。|  
  
 無効になっている保留中の例外は、有効にされたときに発生します。 このため、`_fpieee_flt` を例外フィルターとして使用した場合に、未定義の動作が生じることがあります。 浮動小数点例外を有効にする前に、必ず [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) を呼び出してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h>|  
  
 互換性について詳しくは、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_fpieee.c  
// This program demonstrates the implementation of  
// a user-defined floating-point exception handler using the  
// _fpieee_flt function.  
  
#include <fpieee.h>  
#include <excpt.h>  
#include <float.h>  
#include <stddef.h>  
  
int fpieee_handler( _FPIEEE_RECORD * );  
  
int fpieee_handler( _FPIEEE_RECORD *pieee )  
{  
   // user-defined ieee trap handler routine:  
   // there is one handler for all   
   // IEEE exceptions  
  
   // Assume the user wants all invalid   
   // operations to return 0.  
  
   if ((pieee->Cause.InvalidOperation) &&   
       (pieee->Result.Format == _FpFormatFp32))   
   {  
        pieee->Result.Value.Fp32Value = 0.0F;  
  
        return EXCEPTION_CONTINUE_EXECUTION;  
   }  
   else  
      return EXCEPTION_EXECUTE_HANDLER;  
}  
  
#define _EXC_MASK    \  
    _EM_UNDERFLOW  + \  
    _EM_OVERFLOW   + \  
    _EM_ZERODIVIDE + \  
    _EM_INEXACT  
  
int main( void )  
{  
   // ...  
  
   __try {  
      // unmask invalid operation exception  
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);   
  
      // code that may generate   
      // fp exceptions goes here  
   }  
   __except ( _fpieee_flt( GetExceptionCode(),  
                GetExceptionInformation(),  
                fpieee_handler ) ){  
  
      // code that gets control   
  
      // if fpieee_handler returns  
      // EXCEPTION_EXECUTE_HANDLER goes here  
  
   }  
  
   // ...  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [_control87、_controlfp、\__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)
