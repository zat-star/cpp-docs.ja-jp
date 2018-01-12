---
title: "_atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _atoldbl
- _atoldbl_l
- _atodbl
- _atoflt
- _atoflt_l
- _atodbl_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _atoflt
- _atoflt_l
- atodbl_l
- atoflt_l
- _atoldbl
- _atoldbl_l
- atodbl
- _atodbl_l
- atoldbl
- atoflt
- atoldbl_l
- _atodbl
dev_langs: C++
helpviewer_keywords:
- _atodbl function
- _atoldbl_l function
- atoflt function
- atoflt_l function
- atoldbl function
- _atoldbl function
- atodbl_l function
- _atoflt_l function
- atoldbl_l function
- atodbl function
- string conversion, to floating point values
- _atoflt function
- _atodbl_l function
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea51455d2b02c651aeb8e7bb599cbc3133585c15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atodbl-atodbll-atoldbl-atoldbll-atoflt-atofltl"></a>_atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l
文字列を double (`_atodbl`)、long double (`_atoldbl`)、または float (`_atoflt`) に変換します。  
  
## <a name="syntax"></a>構文  
  
```  
int _atodbl(  
   _CRT_DOUBLE * value,  
   char * str  
);  
int _atodbl_l (  
   _CRT_DOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoldbl(  
   _LDOUBLE * value,  
   char * str  
);  
int _atoldbl_l (  
   _LDOUBLE * value,  
   char * str,  
   locale_t locale  
);  
int _atoflt(  
   _CRT_FLOAT * value,  
   const char * str  
);  
int _atoflt_l(  
   _CRT_FLOAT * value,  
   const char * str,  
   locale_t locale  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `value`  
 文字列を浮動小数点値に変換することで生成される double 型、long double 型、または float 型の値。 これらの値は構造体でラップされます。  
  
 `str`  
 浮動小数点値に変換するために解析する文字列。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 処理が正常に終了した場合は 0 を返します。 発生する可能性のあるエラー コードは、`_UNDERFLOW` または `_OVERFLOW` で、Math.h ヘッダー ファイルで定義されています。  
  
## <a name="remarks"></a>コメント  
 これらの関数は、文字列を浮動小数点値に変換します。 これらの関数と `atof` ファミリの関数の違いは、これらの関数では、浮動小数点コードを生成せず、ハードウェア例外が発生しない点です。 代わりに、エラー状態がエラー コードとして報告されます。  
  
 文字列に浮動小数点値として有効な解釈がない場合、`value` は 0 に設定され、戻り値は 0 になります。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスが付かないバージョンと同じです。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチン|必須ヘッダー|  
|--------------|---------------------|  
|`_atodbl`、`_atoldbl`、`_atoflt`<br /><br /> `_atodbl_l`、`_atoldbl_l`、`_atoflt_l`|\<stdlib.h>|  
  
## <a name="example"></a>例  
  
```  
// crt_atodbl.c  
// Uses _atodbl to convert a string to a double precision  
// floating point value.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main()  
{  
   char str1[256] = "3.141592654";  
   char abc[256] = "abc";  
   char oflow[256] = "1.0E+5000";  
   _CRT_DOUBLE dblval;  
   _CRT_FLOAT fltval;  
   int retval;  
  
   retval = _atodbl(&dblval, str1);  
  
   printf("Double value: %lf\n", dblval.x);  
   printf("Return value: %d\n\n", retval);  
  
   retval = _atoflt(&fltval, str1);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // A non-floating point value: returns 0.  
   retval = _atoflt(&fltval, abc);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   // Overflow.  
   retval = _atoflt(&fltval, oflow);  
   printf("Float value: %f\n", fltval.f);  
   printf("Return value: %d\n\n", retval);  
  
   return 0;  
}  
```  
  
```Output  
Double value: 3.141593  
Return value: 0  
  
Float value: 3.141593  
Return value: 0  
  
Float value: 0.000000  
Return value: 0  
  
Float value: 1.#INF00  
Return value: 3  
```  
  
## <a name="see-also"></a>参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)