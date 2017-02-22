---
title: "atoi、_atoi_l、_wtoi、_wtoi_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wtoi"
  - "_wtoi_l"
  - "atoi"
  - "_atoi_l"
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
  - "_tstoi"
  - "_wtoi"
  - "_ttoi"
  - "atoi"
  - "_atoi_l"
  - "_wtoi_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_atoi_l 関数"
  - "ttoi 関数"
  - "atoi_l 関数"
  - "文字列変換、整数への"
  - "_wtoi 関数"
  - "wtoi_l 関数"
  - "tstoi 関数"
  - "_ttoi 関数"
  - "_tstoi 関数"
  - "_wtoi_l 関数"
  - "atoi 関数"
  - "wtoi 関数"
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# atoi、_atoi_l、_wtoi、_wtoi_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

整数に変換します。  
  
## 構文  
  
```  
int atoi(  
   const char *str   
);  
int _wtoi(  
   const wchar_t *str   
);  
int _atoi_l(  
   const char *str,  
   _locale_t locale  
);  
int _wtoi_l(  
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
 各 `int` 値は数字として入力文字の解釈によって生成された関数の戻り値。  戻り値の型が、その型の値に変換できない場合、`atoi`と `_wtoi`の 0 です。  
  
 大規模負のな整数値でオーバーフローの場合、`LONG_MIN` が返されます。  `atoi` と `_wtoi` はこれらの条件の `INT_MAX` と `INT_MIN` を返します。  範囲外のすべての場合、`errno` は `ERANGE` に設定されます。  渡されるパラメーターが `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## 解説  
 これらの関数は、整数値に変換します。`atoi` と `_wtoi`\)。  入力文字列は、指定された型の数値として解釈できる文字シーケンスです。  関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。  この文字を文字列の末尾を表す null 文字 \(「\\0」または」L」\\0\) である場合もあります。  
  
 `atoi` と `_wtoi` への `str` 引数に次のフォームがあります:  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` はスペースまたはタブで構成され、無視されます。`sign` はプラス \(\+\) またはマイナス \(–\) のいずれかで、`digits` は 1 つ以上の数字です。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstoi`|`atoi`|`atoi`|`_wtoi`|  
|`_ttoi`|`atoi`|`atoi`|`_wtoi`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`atoi`|\<stdlib.h\>|  
|`_atoi_l`, `_wtoi`, `_wtoi_l`|\<stdlib.h\> または \<wchar.h\>|  
  
## 使用例  
 このプログラムは、文字列として格納される数が `atoi` 関数を使用して数値に変換する方法について説明します。  
  
```  
// crt_atoi.c  
// This program shows how numbers   
// stored as strings can be converted to  
// numeric values using the atoi functions.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    int     value = 0;  
  
    // An example of the atoi function.  
    str = "  -2309 ";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function.  
    str = "31412764";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function   
    // with an overflow condition occuring.  
    str = "3336402735171707160320";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **関数: atoi \(「\-2309」\) \= \-2309**  
**関数: atoi \(「31412764 "\) \= 31412764**  
**関数: atoi \(「3336402735171707160320 "\) \= 2147483647**  
**オーバーフローが発生しました。**   
## 同等の .NET Framework 関数  
  
-   [System::Convert::ToInt32](https://msdn.microsoft.com/en-us/library/system.convert.toint32.aspx)  
  
-   [System::Convert::ToUInt32](https://msdn.microsoft.com/en-us/library/system.convert.touint32.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_atodbl、\_atodbl\_l、\_atoldbl、\_atoldbl\_l、\_atoflt、\_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)