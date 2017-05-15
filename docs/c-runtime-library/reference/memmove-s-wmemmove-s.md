---
title: "memmove_s、wmemmove_s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wmemmove_s
- memmove_s
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
- wmemmove_s
- memmove_s
dev_langs:
- C++
helpviewer_keywords:
- wmemmove_s function
- memmove_s function
ms.assetid: a17619e4-1307-4bb0-98c6-77f8c68dab2d
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
ms.openlocfilehash: ca9796f61ad5a3d65d0f421c27133cc2b458f588
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="memmoves-wmemmoves"></a>memmove_s、wmemmove_s
バッファーを別のバッファーに移動します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [memmove、wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md) です。  
  
## <a name="syntax"></a>構文  
  
```  
  
      errno_t memmove_s(  
   void *dest,  
   size_t numberOfElements,  
   const void *src,  
   size_t count  
);  
errno_t wmemmove_s(  
   wchar_t *dest,  
   size_t numberOfElements,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dest`  
 コピー先のオブジェクト。  
  
 `numberOfElements`  
 コピー先のバッファーのサイズ。  
  
 `src`  
 コピー元のオブジェクト。  
  
 `count`  
 コピーするバイト数 (`memmove_s`) または文字数 (`wmemmove_s`)。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します  
  
### <a name="error-conditions"></a>エラー条件  
  
|`dest`|`numberOfElements`|`src`|戻り値|`dest` の内容|  
|------------|------------------------|-----------|------------------|------------------------|  
|`NULL`|任意|任意|`EINVAL`|変更されない|  
|任意|任意|`NULL`|`EINVAL`|変更されない|  
|任意|< `count`|任意|`ERANGE`|変更されない|  
  
## <a name="remarks"></a>コメント  
 コピー`count`から文字のバイトを`src`に`dest`です。 コピー元とコピー先の領域の一部が重なり合っている場合、`memmove_s` は重なり合っている領域のコピー元のバイトをコピーした後で上書きします。  
  
 `dest` または `src` が Null ポインターの場合、またはコピー先文字列が小さすぎる場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`memmove_s`|\<string.h>|  
|`wmemmove_s`|\<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_memmove_s.c  
//  
// The program demonstrates the   
// memmove_s function which works as expected  
// for moving overlapping regions.  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   char str[] = "0123456789";  
  
   printf("Before: %s\n", str);  
  
   // Move six bytes from the start of the string  
   // to a new position shifted by one byte. To protect against  
   // buffer overrun, the secure version of memmove requires the  
   // the length of the destination string to be specified.   
  
   memmove_s((str + 1), strnlen(str + 1, 10), str, 6);   
  
   printf_s(" After: %s\n", str);  
}  
```  
  
## <a name="output"></a>出力  
  
```  
Before: 0123456789  
 After: 0012345789  
```  
  
## <a name="see-also"></a>関連項目  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy_s、wcscpy_s、_mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strcpy、wcscpy、_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)
