---
title: "_mbsnbset、_mbsnbset_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_mbsnbset"
  - "_mbsnbset_l"
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
  - "mbsnbset"
  - "mbsnbset_l"
  - "_mbsnbset"
  - "_mbsnbset_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbsnbset 関数"
  - "_mbsnbset_l 関数"
  - "_tcsnset 関数"
  - "_tcsnset_l 関数"
  - "mbsnbset 関数"
  - "mbsnbset_l 関数"
  - "tcsnset 関数"
  - "tcsnset_l 関数"
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mbsnbset、_mbsnbset_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された文字にマルチバイト文字列の最初の `n` バイトを設定します。  これらの関数のセキュリティを強化したバージョンについては、「[\_mbsnbset\_s、\_mbsnbset\_s\_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md)」を参照してください。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 変更対象の文字列。  
  
 `c`  
 1 バイトまたはマルチバイト文字の設定。  
  
 `count`  
 設定対象のバイト数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 `_mbsnbset` は変更された文字列へのポインターを返します。  
  
## 解説  
 `_mbsnbset` 関数および `_mbsnbset_l` 関数は、最長で `str` の最初の `count` バイトを `c` に設定します。  `count` が `str` の長さを超えると、その `str` の長さが `count` の代わりに使用されます。  `c` がマルチバイト文字で、`count` で指定された最後のバイトに完全に設定できない場合は、最後のバイトは空白文字で埋められます。  `_mbsnbset` と `_mbsnbset_l`は`str`の最後に終端の NULL はありません。  
  
 `_mbsnbset` と `_mbsnbset_l`は`_mbsnset`に似ていますが、`c`の `count` の文字ではなく `count` バイトを設定します。  
  
 `str` が `NULL` の場合、または `count` が 0 の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター例外を生成します。  実行の継続が許可された場合、`errno` が `EINVAL` に設定され、関数から `NULL` が返されます。  また `c` が有効なマルチバイト文字でない場合、`errno` は `EINVAL` に設定され、代わりに空白が使用されます。  
  
 出力値は、ロケールの `LC_CTYPE` カテゴリの設定で決まります。詳細については、「[setlocale](../Topic/setlocale,%20_wsetlocale.md)」を参照してください。  この関数 `_mbsnbset` バージョンは、このロケールに依存する動作に現在のロケールを使用します。`_mbsnbset_l` バージョンは、代わりに渡されるロケール パラメーターを使用することを除いて、同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
 **セキュリティに関するメモ** この API は、バッファー オーバーランが原因で発生する可能性のある問題の影響を受けます。  バッファー オーバーランは、システムを攻撃するときによく使用される方法であり、その結果、認められていない権限が昇格されます。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_mbsnbset`|\<mbstring.h\>|  
|`_mbsnbset_l`|\<mbstring.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## 出力  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [文字列操作](../../c-runtime-library/string-manipulation-crt.md)   
 [\_mbsnbcat、\_mbsnbcat\_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [\_strnset、\_strnset\_l、\_wcsnset、\_wcsnset\_l、\_mbsnset、\_mbsnset\_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [\_strset、\_strset\_l、\_wcsset、\_wcsset\_l、\_mbsset、\_mbsset\_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)