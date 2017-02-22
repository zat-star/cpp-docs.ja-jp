---
title: "_gcvt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_gcvt"
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
  - "_gcvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CVTBUFSIZE"
  - "_gcvt 関数"
  - "変換, 浮動小数点から文字列へ"
  - "CVTBUFSIZE"
  - "浮動小数点関数, 変換 (数値を文字列に)"
  - "gcvt 関数"
  - "数, 変換 (文字列に)"
  - "文字列 [C++], 変換 (浮動小数点型から)"
ms.assetid: 5761411e-c06b-409a-912f-810fe7f4bcb5
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# _gcvt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バッファーに格納された文字列に浮動小数点値を変換します。  この関数のセキュリティが強化されたバージョンを使用できる; [\_gcvt\_s](../../c-runtime-library/reference/gcvt-s.md)を参照してください。  
  
## 構文  
  
```  
char *_gcvt(   
   double value,  
   int digits,  
   char *buffer   
);  
```  
  
#### パラメーター  
 `value`  
 変換される数値。  
  
 `digits`  
 格納されている有効桁数。  
  
 `buffer`  
 結果の格納場所。  
  
## 戻り値  
 `_gcvt` は 文字列へのポインターを返します。  
  
## 解説  
 `_gcvt` 関数 \(小数点記号と可能なバイトを含む\) に浮動小数点 `value` を文字列に変換し、`buffer`で文字列を格納します。  `buffer` は自動的に付けられた終端の null 文字に変換後の値を格納するのに十分な大きさが必要です。  `digits` のバッファー サイズが \+ 1 を使用すると、関数では、バッファーの末尾を上書きします。  これは、変換される文字列に小数点が含まれ、記号、指数情報を含めることができるためです。  オーバーフローのプロビジョニングはありません。  `_gcvt` は 10 進形式で `digits` の数字を生成しようとします。  できない場合、指数形式の `digits` の数字を生成します。  後続のゼロは変換に制約される場合があります。  
  
 長さ `_CVTBUFSIZE` の `buffer` は、浮動小数点値で十分です。  
  
 この関数は、パラメーターを検証します。  `buffer` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、この関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_gcvt`|\<stdlib.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_gcvt.c  
// compile with: /W3  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
  
int main( void )  
{  
   char buffer[_CVTBUFSIZE];  
   double value = -1234567890.123;  
   printf( "The following numbers were converted by _gcvt(value,12,buffer):\n" );  
   _gcvt( value, 12, buffer ); // C4996  
   // Note: _gcvt is deprecated; consider using _gcvt_s instead  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value *= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
  
   printf( "\n" );  
   value = -12.34567890123;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
   value /= 10;  
   _gcvt( value, 12, buffer ); // C4996  
   printf( "buffer: '%s' (%d chars)\n", buffer, strlen(buffer) );  
}  
```  
  
  **次の数は\_gcvt \(値、12 のバッファー\) によって変換されました:**  
**バッファー: 「\- 1234567890.12 " \(14 文字\)**   
**バッファー: 「\- 12345678901.2 " \(14 文字\)**   
**バッファー: 「\- 123456789012 " \(13 文字\)**   
**バッファー: 「\- 1.23456789012e\+012」 \(19 文字\)**   
**バッファー: 「\- 12.3456789012 " \(14 文字\)**   
**バッファー: 「\- 1.23456789012 " \(14 文字\)**   
**バッファー: 「\- 0.123456789012 " \(15 文字\)**   
**バッファー: 「\- 1.23456789012e\-002」 \(19 文字\)**    
## 同等の .NET Framework 関数  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [atof、\_atof\_l、\_wtof、\_wtof\_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)