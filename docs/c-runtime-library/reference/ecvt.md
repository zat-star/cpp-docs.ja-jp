---
title: "ecvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_ecvt"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "ecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ecvt 関数"
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _ecvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`double` の文字列に数値を変換します。  この関数のセキュリティが強化されたバージョンについては、「[\_ecvt\_s](../Topic/_ecvt_s.md)」を参照してください。  
  
## 構文  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### パラメーター  
 `value`  
 変換される数値。  
  
 `count`  
 保存する桁数。  
  
 `dec`  
 保存された小数点位置。  
  
 `sign`  
 変換された数値とします。  
  
## 戻り値  
 `_ecvt` は 文字列へのポインターを返します。; エラーが発生した場合は NULL。  
  
## 解説  
 `_ecvt` 関数は、文字列、浮動小数点数に変換します。  `value` パラメーターは、変換する浮動小数点数です。  この関数は、文字列として `count` まで `value` の数値を格納し、null 文字 \(「\\0」\) を付けます。  `value` の桁数が `count`を超えた場合、下位数字は丸められます。  `count` の数値より少なくがある場合は、文字列をゼロで埋められます。  
  
 `_ecvt` によって返される数字の数。`_CVTBUFSIZE`を超えないようにします。  
  
 数値を文字列に保存されます。  小数点の位置と `value` の符号は呼び出しの後に `dec` と `sign` から取得できます。  `dec` パラメーターは文字列の先頭に関して小数点の位置を示す整数値を指します。  0 または負の整数値は整数部の桁目の左側にあることを示します。  `sign` パラメーターは、変換された数値の符号を表す整数を指定します。  整数値が 0 の場合は、正の数です。  そうしないと、番号が負のです。  
  
 `_ecvt` と `_fcvt` の違いは `count` パラメーターの解釈にあります。  `_ecvt` は 出力文字列の桁数として `_fcvt` が小数点以下の桁数として `count` を解釈する場合、`count` を復号化します。  
  
 `_ecvt` と `_fcvt` は変換に単一の静的に割り当てたバッファーを使用します。  これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。  
  
 この関数は、パラメーターを検証します。  `dec` または `sign` が null であるか、または `count` が 0 の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続 `errno` は `EINVAL` に設定され、NULL が返されます。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`_ecvt`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
  **ソース: 3.1415926535:バッファー 「3141592654 " decimal: 1 種類の符号: 0**   
## 同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)