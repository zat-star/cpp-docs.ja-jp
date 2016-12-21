---
title: "_atoi64、_atoi64_l、_wtoi64、_wtoi64_l | Microsoft Docs"
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
  - "_atoi64_l"
  - "_wtoi64"
  - "_atoi64"
  - "_wtoi64_l"
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
  - "_atoi64"
  - "_tstoi64"
  - "_ttoi64"
  - "wtoi64"
  - "_tstoi64_l"
  - "atoi64"
  - "_wtoi64_l"
  - "_wtoi64"
  - "wtoi64_l"
  - "_atoi64_l"
  - "atoi64_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tstoi64 関数"
  - "wtoi64 関数"
  - "atoi64_l 関数"
  - "_ttoi64 関数"
  - "文字列変換、整数への"
  - "wtoi64_l 関数"
  - "atoi64 関数"
  - "_tstoi64 関数"
  - "_atoi64_l 関数"
  - "_wtoi64_l 関数"
  - "ttoi64 関数"
  - "_wtoi64 関数"
  - "_atoi64 関数"
ms.assetid: 2c3e30fd-545d-4222-8364-0c5905df9526
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _atoi64、_atoi64_l、_wtoi64、_wtoi64_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

64 ビット整数に変換します。  
  
## 構文  
  
```  
__int64 _atoi64(  
   const char *str   
);  
__int64 _wtoi64(  
   const wchar_t *str   
);  
__int64 _atoi64_l(  
   const char *str,  
   _locale_t locale  
);  
__int64 _wtoi64_l(  
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
 各 `__int64` 値は数字として入力文字の解釈によって生成された関数の戻り値。  戻り値の型が、その型の値に変換できない場合 `_atoi64` の 0 です。  
  
 大きい正の整数値でオーバーフローの場合、`_atoi64` は大きく負のな整数値でオーバーフローの場合は `I64_MAX` と `I64_MIN` を返します。  
  
 範囲外のすべての場合、`errno` は `ERANGE` に設定されます。  渡されるパラメーターが `NULL`の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、0 を返します。  
  
## 解説  
 これらの関数は、64 ビットの整数値に変換します。  
  
 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。  関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。  この文字を文字列の末尾を表す null 文字 \(「\\0」または」L」\\0\) である場合もあります。  
  
 `_atoi64` の `str` 引数には、次の形式があります。  
  
```  
[whitespace] [sign] [digits]]  
```  
  
 `whitespace` はスペースまたはタブで構成され、無視されます。`sign` はプラス \(\+\) またはマイナス \(–\) のいずれかで、`digits` は 1 つ以上の数字です。  
  
 `_wtoi64` は、ワイド文字列をパラメーターとして受け取る点を除いて `_atoi64` と同じです。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  詳細については、「[ロケール](../../c-runtime-library/locale.md)」を参照してください。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tstoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
|`_ttoi64`|`_atoi64`|`_atoi64`|`_wtoi64`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_atoi64`, `_atoi64_l`|\<stdlib.h\>|  
|`_wtoi64`, `_wtoi64_l`|\<stdlib.h\> または \<wchar.h\>|  
  
## 使用例  
 このプログラムは、文字列として格納される数が `_atoi64` 関数を使用して数値に変換する方法について説明します。  
  
```  
// crt_atoi64.c  
// This program shows how numbers stored as  
// strings can be converted to numeric values  
// using the _atoi64 functions.  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    __int64 value = 0;  
  
    // An example of the _atoi64 function  
    // with leading and trailing white spaces.  
    str = "  -2309 ";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function   
    // with an arbitrary decimal point.  
    str = "314127.64";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the _atoi64 function  
    // with an overflow condition occurring.  
    str = "3336402735171707160320";  
    value = _atoi64( str );  
    printf( "Function: _atoi64( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
  **関数: \_atoi64 \(「\-2309」\) \= \-2309**  
**関数: \_atoi64 \(「314127.64 "\) \= 314127**  
**関数: \_atoi64 \(「3336402735171707160320 "\) \= \-1**  
**オーバーフローが発生しました。**   
## 同等の .NET Framework 関数  
  
-   [System::Convert::ToInt64](https://msdn.microsoft.com/en-us/library/system.convert.toint64.aspx)  
  
-   [System::Convert::ToUInt64](https://msdn.microsoft.com/en-us/library/system.convert.touint64.aspx)  
  
## 参照  
 [データ変換](../../c-runtime-library/data-conversion.md)   
 [浮動小数点サポート](../../c-runtime-library/floating-point-support.md)   
 [ロケール](../../c-runtime-library/locale.md)   
 [\_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [\_fcvt](../Topic/_fcvt.md)   
 [\_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)   
 [\_atodbl、\_atodbl\_l、\_atoldbl、\_atoldbl\_l、\_atoflt、\_atoflt\_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)