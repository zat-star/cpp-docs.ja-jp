---
title: "vsscanf、vswscanf | Microsoft Docs"
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
  - "vsscanf"
  - "vswscanf"
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
  - "_vstscanf"
  - "vsscanf"
  - "vswscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vsscanf 関数"
  - "vswscanf 関数"
ms.assetid: e96180f2-df46-423d-b4eb-0a49ab819bde
caps.latest.revision: 9
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vsscanf、vswscanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列から書式付きデータを読み込みます。  これらの関数のセキュリティを強化したバージョンについては、「[vsscanf\_s、vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)」を参照してください。  
  
## 構文  
  
```  
int vsscanf(  
   const char *buffer,  
   const char *format,  
   va_list arglist  
);  
int vswscanf(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   va_list arglist  
);  
```  
  
#### パラメーター  
 `buffer`  
 格納されるデータ。  
  
 `format`  
 書式指定文字列。  詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。  
  
 `arglist`  
 可変個引数リスト。  
  
## 戻り値  
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生するか、最初の変換前に文字列の終端に達した場合は `EOF` が返されます。  
  
 `buffer` または `format` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `vsscanf` 関数は、`arglist` 引数リストで各引数によって指定された位置に `buffer` を読み込みます。  リストの各引数は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。  引数 `format` は、入力フィールドの解釈を制御し、`scanf` 関数の引数 `format` と同じ形式と機能を持ちます。  重なり合う文字列間でコピーした場合の動作は未定義です。  
  
> [!IMPORTANT]
>  `vsscanf` を使用して文字列を読み取るときは、`%s` の書式向けに幅を必ず指定します \(たとえば、`"%s"` の代わりに `"%32s"`\)。それ以外の場合は、不適切な書式を入力するとバッファー オーバーランが発生しやすくなる場合があります。  
  
 `vswscanf` は `vsscanf` のワイド文字バージョンであり、`vswscanf` の引数はワイド文字列です。  `vsscanf` は、マルチバイトの 16 進文字を処理しません。  `vswscanf` は、Unicode の全角 16 進文字や "互換区域" の文字は処理しません。  それ以外では、`vswscanf` と `vsscanf` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_vstscanf`|`vsscanf`|`vsscanf`|`vswscanf`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`vsscanf`|\<stdio.h\>|  
|`vswscanf`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_vsscanf.c  
// compile with: /W3  
// This program uses vsscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
#include <stdarg.h>  
  
int call_vsscanf(char *tokenstring, char *format, ...)  
{  
    int result;  
    va_list arglist;  
    va_start(arglist, format);  
    result = vsscanf(tokenstring, format, arglist);  
    va_end(arglist);  
    return result;  
}  
  
int main( void )  
{  
    char  tokenstring[] = "15 12 14...";  
    char  s[81];  
    char  c;  
    int   i;  
    float fp;  
  
    // Input various data from tokenstring:  
    // max 80 character string:  
    call_vsscanf(tokenstring, "%80s", s);  
    call_vsscanf(tokenstring, "%c", &c);  
    call_vsscanf(tokenstring, "%d", &i);  
    call_vsscanf(tokenstring, "%f", &fp);  
  
    // Output the data read  
    printf("String    = %s\n", s);  
    printf("Character = %c\n", c);  
    printf("Integer:  = %d\n", i);  
    printf("Real:     = %f\n", fp);  
}  
```  
  
  **文字列    \= 15**  
**文字 \= 1**  
**整数:  \= 15**  
**実数:     \= 15.000000**   
## 同等の .NET Framework 関数  
 [System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx) などの `Parse` メソッドを参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [sprintf、\_sprintf\_l、swprintf、\_swprintf\_l、\_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vsscanf\_s、vswscanf\_s](../../c-runtime-library/reference/vsscanf-s-vswscanf-s.md)