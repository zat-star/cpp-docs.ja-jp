---
title: "sscanf、_sscanf_l、swscanf、_swscanf_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- swscanf
- sscanf
- _sscanf_l
- _swscanf_l
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
apitype: DLLExport
f1_keywords:
- _sscanf_l
- _stscanf
- swscanf
- _stscanf_l
- sscanf
- _swscanf_l
dev_langs:
- C++
helpviewer_keywords:
- swscanf function
- _stscanf function
- sscanf function
- _stscanf_l function
- _sscanf_l function
- _swscanf_l function
- swscanf_l function
- strings [C++], reading data from
- stscanf function
- reading data, strings
- strings [C++], reading
- sscanf_l function
- stscanf_l function
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: b124ba5aa0fef8efd6d44b405fbc608709e05d72
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="sscanf-sscanfl-swscanf-swscanfl"></a>sscanf、_sscanf_l、swscanf、_swscanf_l
文字列から書式付きデータを読み出します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `buffer`  
 格納されるデータ。  
  
 `format`  
 書式指定文字列。 詳細については、[書式の指定](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)に関する記事をご覧ください。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 エラーが発生するか、最初の変換前に文字列の終端に達した場合は `EOF` が返されます。  
  
 `buffer` または `format` が `NULL` ポインターである場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は -1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `sscanf` 関数は、`buffer` からのデータを各 `argument` で指定した位置に読み込みます。 各 `argument` は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。 引数 `format` は、入力フィールドの解釈を制御し、`format` 関数の引数 `scanf` と同じ形式と機能を持ちます。 重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `sscanf` の文字列を読み取るときは、`%s` の書式向けに幅を必ず指定します (たとえば、`"%32s"` の代わりに `"%s"`)。それ以外の場合は、不適切な書式を入力するとバッファー オーバーランが発生しやすくなる場合があります。  
  
 `swscanf` は `sscanf` のワイド文字バージョンであり、`swscanf` の引数はワイド文字列です。 `sscanf` は、マルチバイトの 16 進文字を処理しません。 `swscanf` は、Unicode の全角 16 進文字や "互換区域" の文字は処理しません。 それ以外では、`swscanf` と `sscanf` の動作は同じです。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`sscanf`, `_sscanf_l`|\<stdio.h>|  
|`swscanf`, `_swscanf_l`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
}  
```  
  
```Output  
String    = 15  
Character = 1  
Integer:  = 15  
Real:     = 15.000000  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fscanf、_fscanf_l、fwscanf、_fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf、_scanf_l、wscanf、_wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf、_snprintf、_snprintf_l、_snwprintf、_snwprintf_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)
