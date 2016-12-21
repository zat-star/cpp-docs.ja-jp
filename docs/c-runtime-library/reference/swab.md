---
title: "_swab | Microsoft Docs"
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
  - "_swab"
  - "stdlib/_swab"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_swab"
  - "stdlib/_swab"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_swab 関数"
  - "バイト, スワップ"
  - "swab 関数"
  - "スワップ (バイトを)"
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: 18
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _swab
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バイトを交換します。  
  
## 構文  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
#### パラメーター  
 `src`  
 コピーされ、交換されるデータ。  
  
 `dest`  
 交換されるデータの格納場所。  
  
 `n`  
 コピーされ、交換されるバイト数。  
  
## 解説  
 `n` が偶数の場合 `_swab` 関数は `src`から `n` バイト数をコピーし、隣接するバイトの各ペアを交換し、`dest`に結果を保存します。  `n` が奇数の場合、`_swab` は `src`の `n-1` 最初のバイトをコピーし、交換します。  `_swab` は通常、別のバイト順を使用するマシンに転送するためにバイナリ データを準備するために使用されます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_swab`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "..........................";  
  
int main()  
{  
    printf( "Before: %s\n        %s\n\n", from, to );  
    _swab( from, to, sizeof( from ) );  
    printf( "After:  %s\n        %s\n\n", from, to );  
}  
```  
  
  **前へ: BADCFEHGJILKNMPORQTSVUXWZY**  
 **..........................**  
**後:  BADCFEHGJILKNMPORQTSVUXWZY**  
 **ABCDEFGHIJKLMNOPQRSTUVWXYZ**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [バッファー操作](../Topic/Buffer%20Manipulation.md)