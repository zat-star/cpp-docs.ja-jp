---
title: "_snscanf_s、_snscanf_s_l、_snwscanf_s、_snwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf_s_l"
  - "_snwscanf_s"
  - "_snscanf_s"
  - "_snscanf_s_l"
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
  - "_sntscanf_s"
  - "snscanf_s"
  - "_snwscanf_s_l"
  - "sntscanf_s_l"
  - "snwscanf_s_l"
  - "snwscanf_s"
  - "_snscanf_s"
  - "_snwscanf_s"
  - "snscanf_s_l"
  - "_sntscanf_s_l"
  - "_snscanf_s_l"
  - "sntscanf_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_snscanf_s 関数"
  - "_snscanf_s_l 関数"
  - "_sntscanf_s 関数"
  - "_sntscanf_s_l 関数"
  - "_snwscanf_s 関数"
  - "_snwscanf_s_l 関数"
  - "読み取り (データを), 文字列"
  - "snscanf_s 関数"
  - "snscanf_s_l 関数"
  - "sntscanf_s 関数"
  - "sntscanf_s_l 関数"
  - "snwscanf_s 関数"
  - "snwscanf_s_l 関数"
  - "文字列 [C++], 読み取り"
  - "文字列 [C++], 読み取り (データを)"
ms.assetid: 72356653-7362-461a-af73-597b9c0a8094
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _snscanf_s、_snscanf_s_l、_snwscanf_s、_snwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列から指定された長さの書式付きデータを読み取ります。  これらの関数は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、[\_snscanf、\_snscanf\_l、\_snwscanf、\_snwscanf\_l](../../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md) のセキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
int __cdecl _snscanf_s(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_s_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf_s(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_s_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   …  
);  
```  
  
#### パラメーター  
 `input`  
 チェックする入力文字列。  
  
 `length`  
 `input`でチェックする文字数。  
  
 `format`  
 一つ以上の書式指定子。  
  
 `... (optional)`  
 値を格納するために使用される変数は `format`の書式指定子で入力文字列から取得された。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 どちらの関数で正常に変換され、代入されたフィールドの数を返します。; 戻り値は読み取り専用で代入されなかったフィールドは含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生するか、最初の変換前に文字列の終端に達した場合は `EOF` が返されます。  詳細については、「[sscanf\_s、\_sscanf\_s\_l、swscanf\_s、\_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)」を参照してください。  
  
 `input` または `format` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 この関数は `sscanf_s` に似ていますが、入力文字列で確認する文字の数を指定できます。  詳細については、「[sscanf\_s、\_sscanf\_s\_l、swscanf\_s、\_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)」を参照してください。  
  
 バッファー サイズ パラメーターは型フィールド文字 `c`、`C`、`s`、`S`と `[`に必要です。  詳細については、「[scanf 関数の型フィールド文字](../../c-runtime-library/scanf-type-field-characters.md)」を参照してください。  
  
> [!NOTE]
>  サイズ パラメーターは `size_t` 型ではなく、`unsigned` 型です。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_sntscanf_s`|`_snscanf_s`|`_snscanf_s`|`_snwscanf_s`|  
|`_sntscanf_s_l`|`_snscanf_s_l`|`_snscanf_s_l`|`_snwscanf_s_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_snscanf_s`, \_`snscanf_s_l`|\<stdio.h\>|  
|`_snwscanf_s`, `_snwscanf_s_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_snscanf_s.c  
// This example scans a string of   
// numbers, using both the character  
// and wide character secure versions  
// of the snscanf function.  
  
#include <stdio.h>  
  
int main( )  
{  
    char        str1[] = "15 12 14...";  
    wchar_t     str2[] = L"15 12 14...";  
    char        s1[3];  
    wchar_t     s2[3];  
    int         i;  
    float       fp;  
  
    i = _snscanf_s( str1, 6,  "%s %f", s1, 3, &fp);  
    printf_s("_snscanf_s converted %d fields: ", i);  
    printf_s("%s and %f\n", s1, fp);  
  
    i = _snwscanf_s( str2, 6,  L"%s %f", s2, 3, &fp);  
    wprintf_s(L"_snwscanf_s converted %d fields: ", i);  
    wprintf_s(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf\_s は 2 フィールドを変換する: 15 および 12.000000**  
**\_snwscanf\_s は 2 フィールドを変換する: 15 および 12.000000**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)