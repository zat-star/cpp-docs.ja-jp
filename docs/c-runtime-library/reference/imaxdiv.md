---
title: "imaxdiv | Microsoft Docs"
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
  - "imaxdiv"
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
  - "imaxdiv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "imaxdiv 関数"
ms.assetid: 7d90126f-fdc2-4986-9cdf-94e4c9123d26
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# imaxdiv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

任意のサイズの 2 つの整数値の商および剰余を単一の操作として計算します。  
  
## 構文  
  
```  
imaxdiv_t imaxdiv(   
   intmax_t numer,  
   intmax_t denom   
);   
```  
  
#### パラメーター  
 `numer`  
 分子。  
  
 `denom`  
 分母。  
  
## 戻り値  
 [intmax\_t](../../c-runtime-library/standard-types.md) 型の引数を使用して呼び出された `imaxdiv` は、商と剰余で構成される [imaxdiv\_t](../../c-runtime-library/standard-types.md) 型の構造を返します。  
  
## 解説  
 `imaxdiv` 関数は `numer` を `denom` で割り、商と剰余を計算します。  `imaxdiv_t` 構造体は商 `intmax_t``quot`、剰余、`intmax_t``rem`が含まれます。  商の符号は、数学的な商の符号と同じです。  この絶対値が最も大きい整数であり、商の絶対値よりも小さくなります。  分母が 0 の場合、プログラムはエラー メッセージにより終了します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`imaxdiv`|\<inttypes.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_imaxdiv.c  
// Build using: cl /W3 /Tc crt_imaxdiv.c  
// This example takes two integers as command-line  
// arguments and calls imaxdiv to divide the first   
// argument by the second, then displays the results.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <inttypes.h>  
  
int main(int argc, char *argv[])  
{  
   intmax_t x,y;  
   imaxdiv_t div_result;  
  
   x = atoll(argv[1]);  
   y = atoll(argv[2]);  
  
   printf("The call to imaxdiv(%lld, %lld)\n", x, y);  
   div_result = imaxdiv(x, y);  
   printf("results in a quotient of %lld, and a remainder of %lld\n\n",  
          div_result.quot, div_result.rem);  
}  
```  
  
 `9460730470000000 8766` のコマンド ライン パラメーターを使用してビルドし、呼び出した場合、コードがその出力を生成します。  
  
  **imaxdiv\(9460730470000000, 8766\) の呼び出し**  
**結果は、商が 1079252848505、剰余が 5170 となります。**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [div](../../c-runtime-library/reference/div.md)   
 [ldiv、lldiv](../Topic/ldiv,%20lldiv.md)