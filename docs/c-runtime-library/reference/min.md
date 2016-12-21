---
title: "__min | Microsoft Docs"
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
  - "__min"
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
  - "__min"
  - "min"
  - "_min"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__min マクロ"
  - "__min マクロ"
  - "min マクロ"
  - "最小値マクロ"
ms.assetid: 2037f26c-b48a-4a69-8870-22519f052a3c
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __min
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

値 2 の小さいサイズを返します。  
  
## 構文  
  
```  
type __min(  
   type a,  
   type b   
);  
```  
  
#### パラメーター  
 `type`  
 数値データ型。  
  
 `a, b`  
 比較される数値型の値。  
  
## 戻り値  
 2 個の引数の小さなの。  
  
## 解説  
 `__min` マクロは 2 個の値を比較する、小さいものという値を返します。  引数は、数値データ型または署名されて符号なしです。  引数と戻り値は、同じデータ型である必要があります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`__min`|\<stdlib.h\>|  
  
## 使用例  
  
```  
// crt_minmax.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int a = 10;  
   int b = 21;  
  
   printf( "The larger of %d and %d is %d\n",  a, b, __max( a, b ) );  
   printf( "The smaller of %d and %d is %d\n", a, b, __min( a, b ) );  
}  
```  
  
  **10 と 21 の拡大の 21 です。**  
**10 と 21 の小さいサイズの 10 です。**   
## 同等の .NET Framework 関数  
 [System::Math::Min](https://msdn.microsoft.com/en-us/library/system.math.min.aspx)  
  
## 参照  
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [\_\_max](../../c-runtime-library/reference/max.md)