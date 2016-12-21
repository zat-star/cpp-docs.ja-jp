---
title: "_atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_atoldbl"
  - "_atoldbl_l"
  - "_atodbl"
  - "_atoflt"
  - "_atoflt_l"
  - "_atodbl_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_atoflt"
  - "_atoflt_l"
  - "atodbl_l"
  - "atoflt_l"
  - "_atoldbl"
  - "_atoldbl_l"
  - "atodbl"
  - "_atodbl_l"
  - "atoldbl"
  - "atoflt"
  - "atoldbl_l"
  - "_atodbl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_atodbl 関数"
  - "_atoldbl_l 関数"
  - "atoflt 関数"
  - "atoflt_l 関数"
  - "atoldbl 関数"
  - "_atoldbl 関数"
  - "atodbl_l 関数"
  - "_atoflt_l 関数"
  - "atoldbl_l 関数"
  - "atodbl 関数"
  - "浮動小数点値への文字列の変換"
  - "_atoflt 関数"
  - "_atodbl_l 関数"
ms.assetid: 2d2530f4-4bd4-42e3-8083-f2d2fbc8432a
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列を double \(`_atodbl`\)、long double \(`_atoldbl`\)、または float \(`_atoflt`\) に変換します。  
  
## 構文  
  
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
  
#### パラメーター  
 `value`  
 文字列を浮動小数点値に変換することで生成される double 型、long double 型、または float 型の値。  これらの値は構造体でラップされます。  
  
 `str`  
 浮動小数点値に変換するために解析する文字列。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 処理が正常に終了した場合は 0 を返します。  発生する可能性のあるエラー コードは、`_UNDERFLOW` または `_OVERFLOW` で、Math.h ヘッダー ファイルで定義されています。  
  
## 解説  
 これらの関数は、文字列を浮動小数点値に変換します。  これらの関数と `atof` ファミリの関数の違いは、これらの関数では、浮動小数点コードを生成せず、ハードウェア例外が発生しない点です。  代わりに、エラー状態がエラー コードとして報告されます。  
  
 文字列に浮動小数点値として有効な解釈がない場合、`value` は 0 に設定され、戻り値は 0 になります。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスが付かないバージョンと同じです。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_atodbl`, `_atoldbl`, `_atoflt`<br /><br /> `_atodbl_l`, `_atoldbl_l`, `_atoflt_l`|\<stdlib.h\>|  
  
## 使用例  
  
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
  
  **double 値: 3.141593**  
**戻り値: 0**  
**浮動小数点値: 3.141593**  
**戻り値: 0**  
**浮動小数点値: 0.000000**  
**戻り値: 0**  
**浮動小数点値: 1.\#INF00**  
**戻り値: 3**   
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)