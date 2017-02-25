---
title: "_set_printf_count_output | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_set_printf_count_output"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "set_printf_count_output"
  - "_set_printf_count_output"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%n 書式"
  - "_set_printf_count_output 関数"
  - "set_printf_count_output 関数"
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _set_printf_count_output
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[printf、\_printf\_l、wprintf、\_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)の `%n` 形式を有効化または無効化サポート\-ファミリは機能します。  
  
## 構文  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### パラメーター  
 `enable`  
 `%n` サポートを無効にすることを `%n` サポートを有効にする、0 以外の値。  
  
## プロパティ値\/戻り値  
 この関数を呼び出す前に `%n` サポートの状態: 無効になったら `%n` サポートが有効な場合、ゼロ以外の場合は 0。  
  
## 解説  
 セキュリティ上の理由により、`%n` の書式指定子のサポートは `printf` とすべてのバリアントに既定で無効になります。  `%n` が `printf` の書式指定で実行された場合、既定では [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、無効なパラメーター ハンドラーを呼び出します。  ゼロ以外の引数による `_set_printf_count_output` を呼び出すと、`printf`\- [printf 関数の型フィールド文字](../../c-runtime-library/printf-type-field-characters.md)"に説明されているように `%n` を解釈するファミリの関数\) が発生します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_set_printf_count_output`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
## 出力  
  
```  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## 同等の .NET Framework 関数  
 使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [\_get\_printf\_count\_output](../../c-runtime-library/reference/get-printf-count-output.md)