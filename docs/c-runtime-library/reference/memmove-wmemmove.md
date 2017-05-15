---
title: "memmove、wmemmove | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memmove
- wmemmove
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
- ntdll.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- memmove
- wmemmove
dev_langs:
- C++
helpviewer_keywords:
- wmemmove function
- memmove function
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
caps.latest.revision: 21
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
ms.openlocfilehash: 2f8c6199d65c5865110774dcd0d2e5623d515467
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="memmove-wmemmove"></a>memmove、wmemmove
バッファーを別のバッファーに移動します。 これらの関数にはセキュリティを強化したバージョンがあります。「[memmove_s、wmemmove_s](../../c-runtime-library/reference/memmove-s-wmemmove-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
void *memmove(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemmove(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dest`  
 コピー先のオブジェクト。  
  
 `src`  
 コピー元のオブジェクト。  
  
 `count`  
 コピーするバイト数 (`memmove`) または文字数 (`wmemmove`)。  
  
## <a name="return-value"></a>戻り値  
 `dest` の値。  
  
## <a name="remarks"></a>コメント  
 コピー`count`バイト (`memmove`) または文字 (`wmemmove`) から`src`に`dest`です。 コピー元とコピー先の領域の一部が重なり合っている場合、どちらの関数も、重なり合っている領域のコピー元のバイトをコピーした後で上書きします。  
  
 **セキュリティに関するメモ** コピー先のバッファーのサイズがソース バッファー以上であることをご確認ください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
 `memmove` 関数と `wmemmove` 関数が非推奨になるのは、以下の例に示すとおり、インクルード ステートメントの前で `_CRT_SECURE_DEPRECATE_MEMORY` を定義して、これらの関数を非推奨にした場合に限られます。  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <string.h>  
or  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`memmove`|\<string.h>|  
|`wmemmove`|\<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_memcpy.c  
// Illustrate overlapping copy: memmove  
// always handles it correctly; memcpy may handle  
// it correctly.  
//  
  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
  
char str1[7] = "aabbcc";  
  
int main( void )  
{  
   printf( "The string: %s\n", str1 );  
   memcpy( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
  
   strcpy_s( str1, sizeof(str1), "aabbcc" );   // reset string  
  
   printf( "The string: %s\n", str1 );  
   memmove( str1 + 2, str1, 4 );  
   printf( "New string: %s\n", str1 );  
}  
```  
  
```Output  
The string: aabbcc  
New string: aaaabb  
The string: aabbcc  
New string: aaaabb  
```  
  
## <a name="see-also"></a>関連項目  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy、wcscpy、_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy、_strncpy_l、wcsncpy、_wcsncpy_l、_mbsncpy、_mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)
