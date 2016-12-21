---
title: "_rotl、_rotl64、_rotr、_rotr64 | Microsoft Docs"
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
  - "_rotr64"
  - "_rotl"
  - "_rotr"
  - "_rotl64"
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
  - "_rotr64"
  - "rotl64"
  - "_rotl64"
  - "rotr64"
  - "rotr"
  - "_rotr"
  - "_rotl"
  - "rotl"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_rotl 関数"
  - "_rotl64 関数"
  - "_rotr 関数"
  - "_rotr64 関数"
  - "ビット, 回転"
  - "回転 (ビットを)"
  - "rotl 関数"
  - "rotl64 関数"
  - "rotr 関数"
  - "rotr64 関数"
ms.assetid: cfce439b-366f-4584-8ab1-d527b13fcfc6
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _rotl、_rotl64、_rotr、_rotr64
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ビットの並びを左方向 \(`_rotl` 関数\) または右方向 \(`_rotr` 関数\) に回転します。  
  
## 構文  
  
```  
  
      unsigned int _rotl(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotl64(  
   unsigned __int64 value,   
   int shift  
);  
unsigned int _rotr(  
   unsigned int value,  
   int shift   
);  
unsigned __int64 _rotr64(  
   unsigned __int64 value,  
   int shift  
);  
```  
  
#### パラメーター  
 *value*  
 ビットを回転する値。  
  
 `shift`  
 回転するビット数。  
  
## 戻り値  
 回転後の値を返します。  エラーの戻り値はありません。  
  
## 解説  
 `_rotl` 関数と `_rotr` 関数は、`shift` ビットで符号なしの値を回転します。  `_rotl` は値を左に回転します。  `_rotr` は値を右に回転します。  いずれの関数も、*value* の一方の端からあふれたビットを他方の端から取り込みます。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|**\_rotl、\_rotl64**|\<stdlib.h\>|  
|**\_rotr、\_rotr64**|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_rot.c  
/* This program shifts values to rotate an integer.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   unsigned val = 0x0fd93;  
   __int64 val2 = 0x0101010101010101;  
  
   printf( "0x%4.4x rotated left three times is 0x%4.4x\n",   
           val, _rotl( val, 3 ) );  
   printf( "0x%4.4x rotated right four times is 0x%4.4x\n",   
           val, _rotr( val, 4 ) );  
  
   printf( "%I64x rotated left three times is %I64x\n",  
           val2, _rotl64( val2, 3 ) );  
   printf( "%I64x rotated right four times is %I64x\n",   
           val2, _rotr64( val2, 4 ) );  
}  
```  
  
## 出力  
  
```  
0xfd93 rotated left three times is 0x7ec98  
0xfd93 rotated right four times is 0x30000fd9  
101010101010101 rotated left three times is 808080808080808  
101010101010101 rotated right four times is 1010101010101010  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_lrotl、\_lrotr](../../c-runtime-library/reference/lrotl-lrotr.md)