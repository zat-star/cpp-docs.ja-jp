---
title: "atof、_atof_l、_wtof、_wtof_l | Microsoft Docs"
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
  - "_wtof_l"
  - "atof"
  - "_atof_l"
  - "_wtof"
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
  - "_tstof"
  - "_ttof"
  - "atof"
  - "stdlib/atof"
  - "math/atof"
  - "_atof_l"
  - "stdlib/_atof_l"
  - "math/_atof_l"
  - "_wtof"
  - "corecrt_wstdlib/_wtof"
  - "_wtof_l"
  - "corecrt_wstdlib/_wtof_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstof 関数"
  - "atof_l 関数"
  - "_atof_l 関数"
  - "atof 関数"
  - "_tstof 関数"
  - "_ttof 関数"
  - "wtof 関数"
  - "_wtof_l 関数"
  - "ttof 関数"
  - "wtof_l 関数"
  - "_wtof 関数"
  - "浮動小数点値への文字列の変換"
ms.assetid: eb513241-c9a9-4f5c-b7e7-a49b14abfb75
caps.latest.revision: 26
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atof、_atof_l、_wtof、_wtof_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Double に変換します。  
  
## 構文  
  
```  
double atof(  
   const char *str   
);  
double _atof_l(  
   const char *str,  
   _locale_t locale  
);  
double _wtof(  
   const wchar_t *str   
);  
double _wtof_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### パラメーター  
 `str`  
 変換対象の文字列。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 各 `double` 値は数字として入力文字の解釈によって生成された関数の戻り値。  戻り値の型が、その型の値に変換できない場合は 0.0 です。  
  
 すべての範囲の場合、errno が `ERANGE`に設定されます。  渡されるパラメーターが `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## 解説  
 これらの関数は、倍精度浮動小数点値に変換します。  
  
 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。  関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。  この文字を文字列の末尾を表す null 文字 \(「\\0」または」L」\\0\) である場合もあります。  
  
 `atof` と `_wtof` への `str` 引数に次のフォームがあります:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\] \[`.digits`\] \[ {`d` &#124; `D` &#124; `e` &#124; `E` }\[`sign`\]`digits`\]  
  
 `whitespace` 領域はタブで無視されるか、;構成されます。`sign` はプラス \(\+\) または描画できます– \(\) ; `digits` とは、一つ以上の 10 進数です。  数字は 10 進数の前には、1 個以上の 10 進数の後に置く必要があります。  10 進数の後には指数部の開始文字 \(`d`、`D`、`e`、または `E`\) および必要に応じて符号付き 10 進整数から構成される指数が従うことがあります。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstof`|`atof`|`atof`|`_wtof`|  
|`_ttof`|`atof`|`atof`|`_wtof`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`atof`|\<math.h と\> stdlib.h \<\>|  
|`_atof_l`|\<math.h と\> stdlib.h \<\>|  
|`_wtof`, `_wtof_l`|\<stdlib.h\> または \<wchar.h\>|  
  
## 使用例  
 このプログラムは、文字列として格納される数が `atof` 関数を使用して数値に変換する方法について説明します。  
  
```  
// crt_atof.c  
//  
// This program shows how numbers stored as   
// strings can be converted to numeric  
// values using the atof function.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    double  value = 0;  
  
    // An example of the atof function  
    // using leading and training spaces.  
    str = "  3336402735171707160320 ";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // Another example of the atof function  
    // using the 'd' exponential formatting keyword.  
    str = "3.1412764583d210";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
    // An example of the atof function  
    // using the 'e' exponential formatting keyword.  
    str = "  -2309.12E-15";  
    value = atof( str );  
    printf( "Function: atof( \"%s\" ) = %e\n", str, value );  
  
}  
```  
  
  **関数: atof \(「3336402735171707160320 "\) \= 3.336403e\+021**  
**関数: atof \(「3.1412764583d210」\) \= 3.141276e\+210**  
**関数: atof \(「\-2309.12E\-15」\) \= \-2.309120e\-012**   
## 同等の .NET Framework 関数  
  
-   [System::Convert::ToSingle](https://msdn.microsoft.com/en-us/library/system.convert.tosingle.aspx)  
  
-   [System::Convert::ToDouble](https://msdn.microsoft.com/en-us/library/system.convert.todouble.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_atodbl、\_atodbl\_l、\_atoldbl、\_atoldbl\_l、\_atoflt、\_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)