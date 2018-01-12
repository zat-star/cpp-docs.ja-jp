---
title: "_memicmp、_memicmp_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _memicmp_l
- _memicmp
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _memicmp
- memicmp_l
- _memicmp_l
dev_langs: C++
helpviewer_keywords:
- memicmp function
- _memicmp function
- memicmp_l function
- _memicmp_l function
ms.assetid: 0a6eb945-4077-4f84-935d-1aaebe8db8cb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adfbab425e5765ce23522612c628b5b83da444b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="memicmp-memicmpl"></a>_memicmp、_memicmp_l
2 つのバッファーの文字を比較します (大文字と小文字を区別しない)。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 `buf1`  
 最初のバッファー。  
  
 `buf2`  
 2 番目のバッファー。  
  
 `count`  
 文字数。  
  
 `locale`  
 使用するロケール。  
  
## <a name="return-value"></a>戻り値  
 戻り値は、バッファー間の関係を示しています。  
  
|戻り値|buf1 と buf2 の最初の count バイトの関係|  
|------------------|--------------------------------------------------------|  
|< 0|`buf1` が `buf2` より小さい。|  
|0|`buf1` が `buf2` と等しい。|  
|> 0|`buf1` が `buf2` より大きい。|  
|`_NLSCMPERROR`|エラーが発生しました。|  
  
## <a name="remarks"></a>コメント  
 `_memicmp` 関数は、2 つのバッファー `buf1` と `buf2` の最初の `count` 文字をバイトごとに比較します。 比較では、大文字と小文字を区別しません。  
  
 `buf1` または `buf2` のいずれかが Null ポインターの場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、関数は `_NLSCMPERROR` を返し、`errno` を `EINVAL` に設定します。  
  
 `_memicmp` は、ロケールに依存する動作に現在のロケールを使用します。`_memicmp_l` は、渡されたロケールを代わりに使用することを除いて同じです。 詳細については、「[ロケール](../../c-runtime-library/locale.md)」をご覧ください。  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`_memicmp`|\<memory.h> または \<string.h>|  
|`_memicmp_l`|\<memory.h> または \<string.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
  
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
  
```Output  
Compare 'Those Who Will Not Learn from' to 'THOSE WHO WILL NOT LEARN FROM'  
First is equal to second.  
```  
  
## <a name="see-also"></a>参照  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)