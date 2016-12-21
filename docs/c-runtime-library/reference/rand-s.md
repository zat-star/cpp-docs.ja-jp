---
title: "rand_s | Microsoft Docs"
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
  - "rand_s"
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
  - "rand_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "暗号として安全な乱数"
  - "生成 (擬似乱数を)"
  - "数, 生成 (擬似乱数を)"
  - "数, 擬似乱数"
  - "擬似乱数"
  - "rand_s 関数"
  - "乱数, 暗号として安全な"
  - "乱数, 生成"
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rand_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

疑似乱数を生成します。  この関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[rand](../Topic/rand.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## 戻り値  
 正常に終了した場合は 0 を返し、それ以外の場合はエラー コードを返します。  入力ポインター `randomValue` が null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、この関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は `EINVAL` を返し、`errno` を `EINVAL` に設定します。  何らかの理由で関数にエラーが発生すると、\*`randomValue` は 0 に設定されます。  
  
## 解説  
 `rand_s` 関数は、0 ～ `UINT_MAX` の範囲の整数の擬似乱数を入力ポインターに書き込みます。  `rand_s` 関数は、オペレーティング システムを使用して、暗号化によりセキュリティが強化された乱数を生成します。  この関数は [srand](../../c-runtime-library/reference/srand.md) 関数によって生成されるシードを使用しません。また、`rand` によって使用される乱数シーケンスにも影響しません。  
  
 `rand_s` 関数を宣言するためには、インクルード ステートメントの前に定数 `_CRT_RAND_S` を定義する必要があります。たとえば、次の例のようになります。  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` は、その動作を [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694) API に依存しています。この API は、Windows XP 以降でしか利用できません。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`rand_s`|\<stdlib.h\>|  
  
 詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## 出力例  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## 同等の .NET Framework 関数  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)