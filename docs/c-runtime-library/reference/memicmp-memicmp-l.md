---
title: "_memicmp、_memicmp_l | Microsoft Docs"
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
  - "_memicmp_l"
  - "_memicmp"
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
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_memicmp"
  - "memicmp_l"
  - "_memicmp_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_memicmp 関数"
  - "_memicmp_l 関数"
  - "memicmp 関数"
  - "memicmp_l 関数"
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _memicmp、_memicmp_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

2 個のバッファー \(大文字と小文字を区別しない\) を比較します。  
  
## 構文  
  
```  
int _memicmp(  
   const void *buf1,  
   const void *buf2,  
   size_t count   
);  
int _memicmp_l(  
   const void *buf1,  
   const void *buf2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `buf1`  
 最初のバッファー。  
  
 `buf2`  
 2 番目のバッファー。  
  
 `count`  
 文字数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 戻り値は、バッファー間の関係を示しています。  
  
|戻り値|buf1 と buf2 の最初のバイト数の関係|  
|---------|-----------------------------|  
|\< 0|`buf1` `buf2`未満。|  
|0|`buf2`と同一の`buf1`。|  
|\> 0|`buf1` は `buf2` より大きい。|  
|`_NLSCMPERROR`|エラーが発生しました。|  
  
## 解説  
 `_memicmp` 関数は、バイト数で 2 個のバッファー `buf1` と `buf2` バイトの `count` の最初の文字を比較します。  比較では、大文字と小文字が区別されません。  
  
 `buf1` または `buf2` が null ポインターの場合、この関数は [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
 `_memicmp` に依存する動作に現在のロケールを使用して; `_memicmp_l` は同じですが、渡されたロケールを代わりに使用します。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_memicmp`|\<memory.h\> または \<string.h\>|  
|`_memicmp_l`|\<memory.h\> または \<string.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_memicmp.c  
// This program uses _memicmp to compare  
// the first 29 letters of the strings named first and  
// second without regard to the case of the letters.  
  
#include <memory.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   int result;  
   char first[] = "Those Who Will Not Learn from History";  
   char second[] = "THOSE WHO WILL NOT LEARN FROM their mistakes";  
   // Note that the 29th character is right here ^  
  
   printf( "Compare '%.29s' to '%.29s'\n", first, second );  
   result = _memicmp( first, second, 29 );  
   if( result < 0 )  
      printf( "First is less than second.\n" );  
   else if( result == 0 )  
      printf( "First is equal to second.\n" );  
   else if( result > 0 )  
      printf( "First is greater than second.\n" );  
}  
```  
  
  **"メンバー" WHO 学ばないから」学ばない個を比較します。**  
**最初に 2 番目のと同じです。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バッファー操作](../Topic/Buffer%20Manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../Topic/memchr,%20wmemchr.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [\_stricmp、\_wcsicmp、\_mbsicmp、\_stricmp\_l、\_wcsicmp\_l、\_mbsicmp\_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [\_strnicmp、\_wcsnicmp、\_mbsnicmp、\_strnicmp\_l、\_wcsnicmp\_l、\_mbsnicmp\_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)