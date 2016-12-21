---
title: "memcpy、wmemcpy | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "memcpy"
  - "wmemcpy"
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
apitype: "DLLExport"
f1_keywords: 
  - "wmemcpy"
  - "memcpy"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memcpy 関数"
  - "wmemcpy 関数"
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memcpy、wmemcpy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファー間でバイトをコピーします。  これらの関数のセキュリティを強化したバージョンについては、「[memcpy\_s、wmemcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 `dest`  
 コピー先のバッファー。  
  
 `src`  
 コピー元のバッファー。  
  
 `count`  
 コピーする文字数。  
  
## 戻り値  
 `dest` の値。  
  
## 解説  
 `memcpy` は、`count` から `src` に `dest` バイトをコピーし、`wmemcpy` は `count` 個のワイド文字 \(2 バイト\) をコピーします。  コピー元とコピー先が重なり合う場合の `memcpy` の動作は未定義です。  重なり合う領域を処理するには、`memmove` を使用します。  
  
> [!IMPORTANT]
>  コピー先のバッファーが、ソース バッファーと同じサイズ、または大きいサイズであることを確認してください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
> [!IMPORTANT]
>  `memcpy` の不適切な使用に由来するバッファー オーバーランと、それに伴う潜在的なセキュリティのぜい弱性が多数生じているため、この関数は、セキュリティ開発ライフ サイクル \(SDL\) で「禁止」関数に挙げられています。  一部の VC\+\+ ライブラリ クラスが `memcpy` を使用し続けていることにお気付きかもしれません。  さらに、VC\+\+ コンパイラ オプティマイザーが `memcpy` への呼び出しを生成する場合があることにもお気付きかもしれません。  Visual C\+\+ 製品は SDL のプロセスに従って開発されているため、この禁止関数の利用は綿密に評価されてきました。  ライブラリがこれを使用する場合、これらの呼び出しによってバッファー オーバーランが許可されないよう、慎重に調査されてきました。  コンパイラの場合、時折、特定のコード パターンが `memcpy` のパターンと同一であると認識されて、この関数の呼び出しに置き換えられることがあります。  そのような場合は、`memcpy` を利用しても、元の手順と比べて安全性は変わらないため、パフォーマンスが調整された `memcpy` 関数の呼び出しを使用するように最適化されます。  「安全」な CRT 関数を使用しても安全性が保証されるわけではない \(安全でない状態になりにくいということに過ぎない\) ように、「禁止された」関数を使用しても、危険であると保証されるわけではありません \(安全性を保障するのに、より大きな監視が必要になるに過ぎません\)。  
>   
>  VC\+\+ コンパイラとライブラリによる `memcpy` の使用は注意深く調査されているため、他の面で SDL に準拠しているコード内でその呼び出しを使用することが許可されています。  アプリケーションのソース コードで `memcpy` 呼び出しを使用した場合は、セキュリティの専門家による確認を受けない限り、SDL 準拠になりません。  
  
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
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`memcpy`|\<memory.h\> または \<string.h\>|  
|`wmemcpy`|\<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md) の使用例については、「`memcpy`」を参照してください。  
  
## 参照  
 [バッファー操作](../Topic/Buffer%20Manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr、wmemchr](../Topic/memchr,%20wmemchr.md)   
 [memcmp、wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove、wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset、wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy\_s、wcscpy\_s、\_mbscpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncpy\_s、\_strncpy\_s\_l、wcsncpy\_s、\_wcsncpy\_s\_l、\_mbsncpy\_s、\_mbsncpy\_s\_l](../Topic/strncpy_s,%20_strncpy_s_l,%20wcsncpy_s,%20_wcsncpy_s_l,%20_mbsncpy_s,%20_mbsncpy_s_l.md)