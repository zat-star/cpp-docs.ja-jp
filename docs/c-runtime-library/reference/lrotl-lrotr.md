---
title: "_lrotl、_lrotr | Microsoft Docs"
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
  - "_lrotl"
  - "_lrotr"
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
  - "lrotr"
  - "lrotl"
  - "_lrotr"
  - "_lrotl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_lrotl 関数"
  - "_lrotr 関数"
  - "ビット"
  - "ビット, 回転"
  - "lrotl 関数"
  - "lrotr 関数"
  - "回転 (ビットを)"
ms.assetid: d42f295b-35f9-49d2-9ee4-c66896ffe68e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _lrotl、_lrotr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ビットの並びを左方向 \(`_lrotl` 関数\) または右方向 \(`_lrotr` 関数\) に回転します。  
  
## 構文  
  
```  
  
      unsigned long _lrotl(  
   unsigned long value,  
   int shift   
);  
unsigned long _lrotr(  
   unsigned long value,  
   int shift   
);  
```  
  
#### パラメーター  
 *value*  
 ビットを回転する値。  
  
 `shift`  
 *値を*シフトされるビット数。  
  
## 戻り値  
 関数は、回転後の値を返します。  エラーの戻り値はありません。  
  
## 解説  
 `_lrotl` と `_lrotr` 関数は `shift` ビットで *値を* 切り替えます。  `_lrotl` は値を左に回転します。  `_lrotr` は値を右に回転します。  いずれの関数も、*value* の一方の端からあふれたビットを他方の端から取り込みます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_lrotl`|\<stdlib.h\>|  
|`_lrotr`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_lrot.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned long val = 0x0fac35791;  
  
   printf( "0x%8.8lx rotated left eight times is 0x%8.8lx\n",   
            val, _lrotl( val, 8 ) );  
   printf( "0x%8.8lx rotated right four times is 0x%8.8lx\n",   
            val, _lrotr( val, 4 ) );  
}  
```  
  
## 出力  
  
```  
0xfac35791 rotated left eight times is 0xc35791fa  
0xfac35791 rotated right four times is 0x1fac3579  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_rotl、\_rotl64、\_rotr、\_rotr64](../../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)