---
title: "memcpy_s、wmemcpy_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memcpy_s"
  - "wmemcpy_s"
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
  - "wmemcpy_s"
  - "memcpy_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memcpy_s 関数"
  - "wmemcpy_s 関数"
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# memcpy_s、wmemcpy_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファー間でバイトをコピーします。 これらのバージョンは、 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) 」の説明に従って、セキュリティ強化機能を備えた [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)します。  
  
## 構文  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### パラメーター  
 `dest`  
 コピー先のバッファー。  
  
 `destSize`  
 Memcpy\_s、wmemcpy\_s のワイド文字 \(wchar\_t\) のバイト単位でのコピー先バッファーのサイズ。  
  
 `src`  
 コピー元のバッファー。  
  
 `count`  
 コピーする文字数。  
  
## 戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。  
  
### エラー条件  
  
|`dest`|`destSize`|`src`|戻り値|`dest` の内容|  
|------------|----------------|-----------|---------|----------------|  
|`NULL`|任意|任意|`EINVAL`|変更されない|  
|任意|任意|`NULL`|`EINVAL`|`dest` ゼロに設定されます。|  
|任意|\< `count`|任意|`ERANGE`|`dest` ゼロに設定されます。|  
  
## 解説  
 `memcpy_s` は、`count` から `src` に `dest` バイトをコピーし、`wmemcpy_s` は `count` 個のワイド文字 \(2 バイト\) をコピーします。 コピー元とコピー先が重なり合う場合の `memcpy_s` の動作は未定義です。 重なり合う領域を処理するには、`memmove_s` を使用します。  
  
 これらの関数では、パラメーターの検証が行われます。 場合 `dest` または `src` null ポインターまたは `destSize` よりも小さい `count`, 、」の説明に従って、これらの関数が無効なパラメーター ハンドラーを呼び出します [パラメーターの検証](../../c-runtime-library/parameter-validation.md)します。 実行の継続が許可された場合、これらの関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`memcpy_s`|\<memory.h\> または \<string.h\>|  
|`wmemcpy_s`|\<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## 同等の .NET Framework 関数  
 該当しない。 標準 C 関数を呼び出すには、`PInvoke` を使用します。 詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バッファー操作](../Topic/Buffer%20Manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../Topic/memchr,%20wmemchr.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove、wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy、wcscpy、\_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)