---
title: "_snscanf、_snscanf_l、_snwscanf、_snwscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf"
  - "_snscanf_l"
  - "_snscanf"
  - "_snwscanf_l"
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
  - "_snscanf"
  - "_snscanf_l"
  - "_snwscanf"
  - "snscanf_l"
  - "snscanf"
  - "_sntscanf_l"
  - "_sntscanf"
  - "_snwscanf_l"
  - "sntscanf_l"
  - "sntscanf"
  - "snwscanf"
  - "snwscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_snscanf 関数"
  - "_snscanf_l 関数"
  - "_sntscanf 関数"
  - "_sntscanf_l 関数"
  - "_snwscanf 関数"
  - "_snwscanf_l 関数"
  - "読み取り (データを), 文字列"
  - "snscanf 関数"
  - "snscanf_l 関数"
  - "sntscanf 関数"
  - "sntscanf_l 関数"
  - "snwscanf 関数"
  - "snwscanf_l 関数"
  - "文字列 [C++], 読み取り"
  - "文字列 [C++], 読み取り (データを)"
ms.assetid: da1ac890-f905-4cd7-954b-3c90957b5551
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _snscanf、_snscanf_l、_snwscanf、_snwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列から指定された長さの書式付きデータを読み取ります。  これらの関数のセキュリティを強化したバージョンについては、「[\_snscanf\_s、\_snscanf\_s\_l、\_snwscanf\_s、\_snwscanf\_s\_l](../../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)」を参照してください。  
  
## 構文  
  
```  
int __cdecl _snscanf(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   ...  
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
 どちらの関数で正常に変換され、代入されたフィールドの数を返します。; 戻り値は読み取り専用で代入されなかったフィールドは含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生するか、最初の変換前に文字列の終端に達した場合は `EOF` が返されます。  詳細については、「[関数](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)」を参照してください。  
  
 `input` または `format` が `NULL` ポインターである場合、または `length` がゼロ以下の場合、無効なパラメーター ハンドラーが [パラメーターの検証](../../c-runtime-library/parameter-validation.md)"に説明されているように、呼び出されます。  実行の継続が許可された場合、これらの関数は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 この関数は `sscanf` に似ていますが、入力文字列で確認する文字の数を指定できます。  詳細については、「[関数](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)」を参照してください。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_sntscanf`|`_snscanf`|`_snscanf`|`_snwscanf`|  
|`_sntscanf_l`|`_snscanf_l`|`_snscanf_l`|`_snwscanf_l`|  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_snscanf`, `_snscanf_l`|\<stdio.h\>|  
|`_snwscanf`, `_snwscanf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_snscanf.c  
// compile with: /W3  
  
#include <stdio.h>  
int main( )  
{  
   char  str1[] = "15 12 14...";  
   wchar_t  str2[] = L"15 12 14...";  
   char  s1[3];  
   wchar_t  s2[3];  
   int   i;  
   float fp;  
  
   i = _snscanf( str1, 6,  "%s %f", s1, &fp); // C4996  
   // Note: _snscanf is deprecated; consider using _snscanf_s instead  
   printf("_snscanf converted %d fields: ", i);  
   printf("%s and %f\n", s1, fp);  
  
   i = _snwscanf( str2, 6,  L"%s %f", s2, &fp); // C4996  
   // Note: _snwscanf is deprecated; consider using _snwscanf_s instead  
   wprintf(L"_snwscanf converted %d fields: ", i);  
   wprintf(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf は 2 フィールドを変換する: 15 および 12.000000**  
**\_snwscanf は 2 フィールドを変換する: 15 および 12.000000**   
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)