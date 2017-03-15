---
title: "_itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_itow"
  - "_i64tow"
  - "_itoa"
  - "_i64toa"
  - "_ui64toa"
  - "_ui64tow"
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
  - "_i64tow"
  - "ui64toa"
  - "ui64tow"
  - "itot"
  - "_itot"
  - "_i64toa"
  - "_itoa"
  - "_itow"
  - "_ui64tow"
  - "i64toa"
  - "i64tow"
  - "itow"
  - "_ui64toa"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_i64toa 関数"
  - "_i64tow 関数"
  - "_itoa 関数"
  - "_itot 関数"
  - "_itow 関数"
  - "_ui64toa 関数"
  - "_ui64tow 関数"
  - "変換 (整数を)"
  - "変換 (数値の), 文字列への"
  - "i64toa 関数"
  - "i64tow 関数"
  - "整数, 変換"
  - "itoa 関数"
  - "itot 関数"
  - "itow 関数"
  - "ui64toa 関数"
  - "ui64tow 関数"
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _itoa、_i64toa、_ui64toa、_itow、_i64tow、_ui64tow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数を文字列に変換します。  これらの関数のセキュリティを強化したバージョンについては、「[\_itoa\_s、\_i64toa\_s、\_ui64toa\_s、\_itow\_s、\_i64tow\_s、\_ui64tow\_s](../../c-runtime-library/reference/itoa-s-i64toa-s-ui64toa-s-itow-s-i64tow-s-ui64tow-s.md)」を参照してください。  
  
## 構文  
  
```  
char *_itoa(  
   int value,  
   char *str,  
   int radix   
);  
char *_i64toa(  
   __int64 value,  
   char *str,  
   int radix   
);  
char * _ui64toa(  
   unsigned _int64 value,  
   char *str,  
   int radix   
);  
wchar_t * _itow(  
   int value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t *str,  
   int radix   
);  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t *str,  
   int radix   
);  
template <size_t size>  
char *_itoa(  
   int value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char *_i64toa(  
   __int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
char * _ui64toa(  
   unsigned _int64 value,  
   char (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _itow(  
   int value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _i64tow(  
   __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
template <size_t size>  
wchar_t * _ui64tow(  
   unsigned __int64 value,  
   wchar_t (&str)[size],  
   int radix   
); // C++ only  
```  
  
#### パラメーター  
 `value`  
 変換される数値。  
  
 `str`  
 結果の文字列。  
  
 `radix`  
 `value` の基数。2 ～ 36 の範囲で指定する必要があります。  
  
## 戻り値  
 これらの各関数は、`str` へのポインターを返します。  エラーの戻り値はありません。  
  
## 解説  
 `_itoa`、`_i64toa`、および `_ui64toa` の各関数は、指定された `value` 引数の数字を null で終了する文字列に変換し、その結果 \(`_itoa` の場合最大 33 文字、`_i64toa` および `_ui64toa` の場合最大 65 文字\) を `str` に保存します。  `radix` が 10 で、`value` が負の場合は、保存される文字列の最初の文字は負符号 \( `–`\) になります。  `_itow`、`_i64tow`、および `_ui64tow` は、それぞれ `_itoa`、`_i64toa`、および `_ui64toa` のワイド文字バージョンです。  
  
> [!IMPORTANT]
>  バッファー オーバーランを回避するには、`str` のバッファーを、変換された数字、末尾の null 文字、および符号文字を保持できるよう十分に大きくします。  
  
 C\+\+ では、これらの関数にテンプレートのオーバーロードがあります。このオーバーロードは、これらの関数に対応するセキュリティで保護された新しい関数を呼び出します。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_itot`|`_itoa`|`_itoa`|`_itow`|  
|`_i64tot`|`_i64toa`|`_i64toa`|`_i64tow`|  
|`_ui64tot`|`_ui64toa`|`_ui64toa`|`_ui64tow`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_itoa`|\<stdlib.h\>|  
|`_i64toa`|\<stdlib.h\>|  
|`_ui64toa`|\<stdlib.h\>|  
|`_itow`|\<stdlib.h\>|  
|`_i64tow`|\<stdlib.h\>|  
|`_ui64tow`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_itoa.c  
// compile with: /W3  
// This program makes use of the _itoa functions  
// in various examples.  
  
#include <string.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[65];  
   int r;  
   for( r=10; r>=2; --r )  
   {  
     _itoa( -1, buffer, r ); // C4996  
     // Note: _itoa is deprecated; consider using _itoa_s instead  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _i64toa( -1L, buffer, r ); // C4996  
     // Note: _i64toa is deprecated; consider using _i64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
   printf( "\n" );  
   for( r=10; r>=2; --r )  
   {  
     _ui64toa( 0xffffffffffffffffL, buffer, r ); // C4996  
     // Note: _ui64toa is deprecated; consider using _ui64toa_s  
     printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
   }  
}  
```  
  
  **base 10: \-1 \(2 chars\)**  
**base 9: 12068657453 \(11 chars\)**  
**base 8: 37777777777 \(11 chars\)**  
**base 7: 211301422353 \(12 chars\)**  
**base 6: 1550104015503 \(13 chars\)**  
**base 5: 32244002423140 \(14 chars\)**  
**base 4: 3333333333333333 \(16 chars\)**  
**base 3: 102002022201221111210 \(21 chars\)**  
**base 2: 11111111111111111111111111111111 \(32 chars\)**  
**base 10: \-1 \(2 chars\)**  
**base 9: 145808576354216723756 \(21 chars\)**  
**base 8: 1777777777777777777777 \(22 chars\)**  
**base 7: 45012021522523134134601 \(23 chars\)**  
**base 6: 3520522010102100444244423 \(25 chars\)**  
**base 5: 2214220303114400424121122430 \(28 chars\)**  
**base 4: 33333333333333333333333333333333 \(32 chars\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 chars\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 chars\)**  
**base 10: 18446744073709551615 \(20 chars\)**  
**base 9: 145808576354216723756 \(21 chars\)**  
**base 8: 1777777777777777777777 \(22 chars\)**  
**base 7: 45012021522523134134601 \(23 chars\)**  
**base 6: 3520522010102100444244423 \(25 chars\)**  
**base 5: 2214220303114400424121122430 \(28 chars\)**  
**base 4: 33333333333333333333333333333333 \(32 chars\)**  
**base 3: 11112220022122120101211020120210210211220 \(41 chars\)**  
**base 2: 1111111111111111111111111111111111111111111111111111111111111111 \(64 chars\)**   
## 同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [\_ltoa、\_ltow](../Topic/_ltoa,%20_ltow.md)   
 [\_ltoa\_s、\_ltow\_s](../../c-runtime-library/reference/ltoa-s-ltow-s.md)   
 [\_ultoa、\_ultow](../../c-runtime-library/reference/ultoa-ultow.md)   
 [\_ultoa\_s、\_ultow\_s](../Topic/_ultoa_s,%20_ultow_s.md)