---
title: "_mbsnbset_s、_mbsnbset_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
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
  - "api-ms-win-crt-multibyte-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbsnbset_s"
  - "_mbsnbset_s_l"
  - "_mbsnbset_s"
  - "mbsnbset_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_mbsnbset_s 関数"
  - "_mbsnbset_s_l 関数"
  - "_tcsnset_s 関数"
  - "_tcsnset_s_l 関数"
  - "mbsnbset_s 関数"
  - "mbsnbset_s_l 関数"
  - "tcsnset_s 関数"
  - "tcsnset_s_l 関数"
ms.assetid: 811f92c9-cc31-4bbd-8017-2d1bfc6fb96f
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _mbsnbset_s、_mbsnbset_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された文字にマルチバイト文字列の最初の `n` バイトを設定します。  これらのバージョンの [\_mbsnbset、\_mbsnbset\_l](../../c-runtime-library/reference/mbsnbset-mbsnbset-l.md) は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」にあるとおり、セキュリティが強化されています。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
errno_t _mbsnbset_s(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count   
);  
errno_t _mbsnbset_s_l(  
   unsigned char *str,  
   size_t size,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t _mbsnbset_s(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsnbset_s_l(  
   unsigned char (&str)[size],  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### パラメーター  
 `str`  
 変更対象の文字列。  
  
 `size`  
 文字列バッファーのサイズ。  
  
 `c`  
 1 バイトまたはマルチバイト文字の設定。  
  
 `count`  
 設定対象のバイト数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。  
  
## 解説  
 `_mbsnbset_s` 関数および `_mbsnbset_s_l` 関数は、最長で `count` の最初の `str` バイトを `c` に設定します。  `count` が `str` の長さを超えると、その `str` の長さが `count` の代わりに使用されます。  `c` がマルチバイト文字で、`count` で指定された最後のバイトまでに全体を設定できない場合は、最後のバイトは空白文字で埋められます。  `_mbsnbset_s` と `_mbsnbset_s_l` は、`str` の最後に終端の null を置きません。  
  
 `_mbsnbset_s` と `_mbsnbset_s_l` は `_mbsnset` と似ていますが `c` の `count` 文字ではなく `count` バイトを設定する点が異なります。  
  
 `str` が `NULL` の場合、または `count` が 0 の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター例外を生成します。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  また `c` が有効なマルチバイト文字でない場合、`errno` は `EINVAL` に設定され、代わりに空白が使用されます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  この関数の `_mbsnbset_s` バージョンは、ロケールに依存するこの動作について現在のロケールを使用します。`_mbsnbset_s_l` バージョンは、渡されるロケール パラメーターを代わりに使用することを除いて、同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 C\+\+ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。  詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../Topic/Secure%20Template%20Overloads.md)」を参照してください。  
  
 これらの関数のデバッグ バージョンは、最初にバッファーを 0xFD で埋めます。  この動作を無効にするには、[\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) を使用します。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsnset_s`|`_strnset_s`|`_mbsnbset_s`|`_wcsnset_s`|  
|`_tcsnset_s_l`|`_strnset_s _l`|`_mbsnbset_s_l`|`_wcsnset_s_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbsnbset_s`|\<mbstring.h\>|  
|`_mbsnbset_s_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_mbsnbset_s.c  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset_s( string, sizeof(string), '*', 4 );  
   printf( "After:  %s\n", string );  
}  
```  
  
## 出力  
  **前: これはテストです**  
**後:  \*\*\*\* はテストです**   
## 同等の .NET Framework 関数  
 該当なし。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat、\_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset、\_strnset\_l、\_wcsnset、\_wcsnset\_l、\_mbsnset、\_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)