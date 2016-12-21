---
title: "atol、_atol_l、_wtol、_wtol_l | Microsoft Docs"
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
  - "atol"
  - "_wtol_l"
  - "_wtol"
  - "_atol_l"
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
  - "_atol_l"
  - "_ttol_l"
  - "_tstol_l"
  - "_tstol"
  - "_wtol"
  - "_ttol"
  - "_wtol_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstol 関数"
  - "atol 関数"
  - "ttol 関数"
  - "_atol_l 関数"
  - "_tstol_l 関数"
  - "文字列変換、整数への"
  - "_tstol 関数"
  - "_ttol 関数"
  - "_ttol_l 関数"
  - "atol_l 関数"
  - "wtol_l 関数"
  - "_wtol_l 関数"
  - "wtol 関数"
  - "_wtol 関数"
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atol、_atol_l、_wtol、_wtol_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

長整数に文字列を変換します。  
  
## 構文  
  
```  
long atol(  
   const char *str   
);  
long _atol_l(  
   const char *str,  
   _locale_t locale  
);  
long _wtol(  
   const wchar_t *str   
);  
long _wtol_l(  
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
 各 `long` 値は数字として入力文字の解釈によって生成された関数の戻り値。  戻り値の型が、その型の値に変換できない場合 `atol` の 0L です。  
  
 大きい正の整数値でオーバーフローの場合、`atol` は `LONG_MAX`;を返します 大規模負のな整数値でオーバーフローの場合、`LONG_MIN` が返されます。  範囲外のすべての場合、`errno` は `ERANGE` に設定されます。  渡されるパラメーターが `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## 解説  
 これらの関数は長整数値 \(`atol`\) に文字列を変換します。  
  
 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。  関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。  この文字を文字列の末尾を表す `NULL` の文字 \(「\\0」または」L」\\0\) である場合もあります。  
  
 `atol` の `str` 引数には、次の形式があります。  
  
 \[`whitespace`\] \[`sign`\] \[`digits`\]\]  
  
 `whitespace` はスペースまたはタブで構成され、無視されます。`sign` はプラス \(\+\) またはマイナス \(–\) のいずれかで、`digits` は 1 つ以上の数字です。  
  
 `_wtol` は `atol` と同じですが、ワイド文字列を使用します。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_tstol`|`atol`|`atol`|`_wtol`|  
|`_ttol`|`atol`|`atol`|`_wtol`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`atol`|\<stdlib.h\>|  
|`_atol_l`, `_wtol`, `_wtol_l`|\<stdlib.h と\> wchar.h \<\>|  
  
## 使用例  
 このプログラムは、文字列として格納される数が `atol` 関数を使用して数値に変換する方法について説明します。  
  
```  
// crt_atol.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the atol functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    long    value = 0;  
  
    // An example of the atol function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atol function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = atol( str );  
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **関数: atol \(「\-2309」\) \= \-2309**  
**関数: atol \(「314127.64 "\) \= 314127**  
**関数: atol \(「3336402735171707160320 "\) \= 2147483647**  
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