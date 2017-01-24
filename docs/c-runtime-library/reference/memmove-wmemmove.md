---
title: "memmove、wmemmove | Microsoft Docs"
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
  - "memmove"
  - "wmemmove"
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
  - "memmove"
  - "wmemmove"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "memmove 関数"
  - "wmemmove 関数"
ms.assetid: 3a906114-9cf3-40d7-bd99-ee452004f218
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# memmove、wmemmove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーの内容をほかのバッファーに移動します。  これらの関数のセキュリティを強化したバージョンについては、「[memmove\_s、wmemmove\_s](../../c-runtime-library/reference/memmove-s-wmemmove-s.md)」を参照してください。  
  
## 構文  
  
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
  
#### パラメーター  
 `dest`  
 コピー先のオブジェクト。  
  
 `src`  
 コピー元のオブジェクト。  
  
 `count`  
 コピーするバイト数 \(`memmove`\) または文字数 \(`wmemmove`\)。  
  
## 戻り値  
 `dest`の値*。*  
  
## 解説  
 コピーの `count` バイト \(`memmove`\) または `src` から `dest`への文字 \(`wmemmove`\) *。*ソースとターゲット領域の一部が重複する場合、関数はどちらもいる領域のコピー元のバイトが上書きされる前にコピーされることを確認します。  
  
 **セキュリティに関するメモ** コピー先のバッファーのサイズがコピー元のバッファーのサイズ以上であることを確認してください。  詳細については、「[Avoiding Buffer Overruns](http://msdn.microsoft.com/library/windows/desktop/ms717795)」を参照してください。  
  
 次の例のように、`memmove` 関数および `wmemmove` 関数が使用されなくなるように定数 `_CRT_SECURE_DEPRECATE_MEMORY` をインクルード ステートメントの前で定義すると、これらの関数だけが使用されなくなります。  
  
```  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <string.h>  
or  
#define _CRT_SECURE_DEPRECATE_MEMORY  
#include <wchar.h>  
```  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`memmove`|\<string.h\>|  
|`wmemmove`|\<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
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
  
  **文字列: aabbcc**  
**新しい文字列: aaaabb**  
**文字列: aabbcc**  
**新しい文字列: aaaabb**   
## 同等の .NET Framework 関数  
 [System::Buffer::BlockCopy](https://msdn.microsoft.com/en-us/library/system.buffer.blockcopy.aspx)  
  
## 参照  
 [バッファー操作](../Topic/Buffer%20Manipulation.md)   
 [\_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memcpy、wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)   
 [strcpy、wcscpy、\_mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy、\_strncpy\_l、wcsncpy、\_wcsncpy\_l、\_mbsncpy、\_mbsncpy\_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)