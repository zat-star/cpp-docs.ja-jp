---
title: "memcpy、wmemcpy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- memcpy
- wmemcpy
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
- wmemcpy
- memcpy
dev_langs:
- C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 415d8d4f604625b8bafbb953d381c2a43e394a3f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="memcpy-wmemcpy"></a>memcpy、wmemcpy
バッファー間でバイトをコピーします。 これらの関数のセキュリティを強化したバージョンについては、「[memcpy_s、wmemcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
void *memcpy(  
   void *dest,  
   const void *src,  
   size_t count   
);  
wchar_t *wmemcpy(  
   wchar_t *dest,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `dest`  
 コピー先のバッファー。  
  
 `src`  
 コピー元のバッファー。  
  
 `count`  
 コピーする文字数。  
  
## <a name="return-value"></a>戻り値  
 `dest` の値。  
  
## <a name="remarks"></a>コメント  
 `memcpy` は、`count` から `src` に `dest` バイトをコピーし、`wmemcpy` は `count` 個のワイド文字 (2 バイト) をコピーします。 コピー元とコピー先が重なり合う場合の `memcpy` の動作は未定義です。 重なり合う領域を処理するには、`memmove` を使用します。  
  
> [!IMPORTANT]
>  コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。 詳しくは、「 [バッファー オーバーランの回避](http://msdn.microsoft.com/library/windows/desktop/ms717795)」をご覧ください。  
  
> [!IMPORTANT]
>  `memcpy` の不適切な使用に由来するバッファー オーバーランと、それに伴う潜在的なセキュリティのぜい弱性が多数生じているため、この関数は、セキュリティ開発ライフ サイクル (SDL) で「禁止」関数に挙げられています。  一部の VC++ ライブラリ クラスが `memcpy` を使用し続けていることにお気付きかもしれません。  さらに、VC++ コンパイラ オプティマイザーが `memcpy` への呼び出しを生成する場合があることにもお気付きかもしれません。  Visual C++ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合、時折、特定のコード パターンが `memcpy` のパターンと同一であると認識されて、この関数の呼び出しに置き換えられることがあります。  そのような場合は、`memcpy` を利用しても、元の手順と比べて安全性は変わらないため、パフォーマンスが調整された `memcpy` 関数の呼び出しを使用するように最適化されます。  「安全」な CRT 関数を使用しても安全性が保証されるわけではない (安全でない状態になりにくいということに過ぎない) ように、「禁止された」関数を使用しても、危険であると保証されるわけではありません (安全性を保障するのに、より大きな監視が必要になるに過ぎません)。  
>   
>  VC++ コンパイラとライブラリによる `memcpy` の使用は注意深く調査されているため、他の面で SDL に準拠しているコード内でその呼び出しを使用することが許可されています。  アプリケーションのソース コードで `memcpy` 呼び出しを使用した場合は、セキュリティの専門家による確認を受けない限り、SDL 準拠になりません。  
  
 `memcpy` 関数と `wmemcpy` 関数が非推奨になるのは、以下の例に示すとおり、インクルード ステートメントの前で `_CRT_SECURE_DEPRECATE_MEMORY` を定義して、これらの関数を非推奨にした場合に限られます。  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <memory.h>  
```  
  
 または  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`memcpy`|\<memory.h> または \<string.h>|  
|`wmemcpy`|\<wchar.h>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「 [互換性](../../c-runtime-library/compatibility.md) 」を参照してください。  
  
## <a name="example"></a>例  
 `memcpy` の使用例については、「[memmove](../../c-runtime-library/reference/memmove-wmemmove.md)」をご覧ください。  
  
## <a name="see-also"></a>参照  
 [バッファー操作](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove、wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy_s、wcscpy_s、_mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy_s、_strncpy_s_l、wcsncpy_s、_wcsncpy_s_l、_mbsncpy_s、_mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)