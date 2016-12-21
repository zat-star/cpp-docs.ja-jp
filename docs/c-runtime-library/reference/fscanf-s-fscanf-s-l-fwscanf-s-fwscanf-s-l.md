---
title: "fscanf_s、_fscanf_s_l、fwscanf_s、_fwscanf_s_l | Microsoft Docs"
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
  - "fwscanf_s"
  - "_fscanf_s_l"
  - "_fwscanf_s_l"
  - "fscanf_s"
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
  - "_fwscanf_s_l"
  - "_fscanf_s_l"
  - "fscanf_s"
  - "_ftscanf_s_l"
  - "_ftscanf_s"
  - "fwscanf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fscanf_s_l 関数"
  - "_ftscanf_s 関数"
  - "_ftscanf_s_l 関数"
  - "_fwscanf_s_l 関数"
  - "データ [CRT], 読み取り (ストリームから)"
  - "書式付きデータ [C++], 読み取り (ストリームから)"
  - "fscanf_s 関数"
  - "fscanf_s_l 関数"
  - "ftscanf_s 関数"
  - "ftscanf_s_l 関数"
  - "fwscanf_s 関数"
  - "fwscanf_s_l 関数"
  - "ストリーム [C++], 読み取り (書式付きデータを)"
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fscanf_s、_fscanf_s_l、fwscanf_s、_fwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームから書式化されたデータを読み出します。  [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md) のこれらのバージョンは、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」に説明されているように、セキュリティが強化されています。  
  
## 構文  
  
```  
int fscanf_s(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_s_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf_s(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_s_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...   
);  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
 `format`  
 書式指定文字列。  
  
 `argument`  
 省略可能な引数。  
  
 `locale`  
 使用するロケール。  
  
## 戻り値  
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生した場合や、最初の変換の前にファイル ストリームの終端を検出した場合、`fscanf_s` および `fwscanf_s` は `EOF` を返します。  
  
 これらの関数では、パラメーターの検証が行われます。  `stream` が無効なファイル ポインターの場合、または `format` が null ポインターの場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 `fscanf_s` 関数は、`stream` の現在位置から `argument` \(ある場合\) で指定された位置にデータを読み込みます。  各 `argument` は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。  `format` は入力フィールドの解釈を制御し、`scanf_s` 関数の `format` 引数と同じ形式と機能を持ちます。`format` の詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。`fwscanf_s` は `fscanf_s` のワイド文字バージョンであり、`fwscanf_s` の引数 format はワイド文字列です。  ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。  `fscanf_s` では、UNICODE ストリームからの入力はサポートされていません。  
  
 セキュリティが強化された関数 \(`_s` サフィックス付き\) とその他のバージョンの関数との主な違いは、セキュリティが強化された関数では、`c`、`C`、`s`、`S`、および `[` の各型フィールドを使用するとき、引数として、それぞれの変数の直後にフィールドのサイズを渡す必要がある点です。  詳細については、「[scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)」および「[scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)」を参照してください。  
  
> [!NOTE]
>  サイズ パラメーターは `size_t` 型ではなく、`unsigned` 型です。  
  
 これらの関数のうち `_l` サフィックスが付けられたバージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ftscanf_s`|`fscanf_s`|`fscanf_s`|`fwscanf_s`|  
|`_ftscanf_s_l`|`_fscanf_s_l`|`_fscanf_s_l`|`_fwscanf_s_l`|  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fscanf_s`, `_fscanf_s_l`|\<stdio.h\>|  
|`fwscanf_s`, `_fwscanf_s_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fscanf_s.c  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );  
   if( err )  
      printf_s( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf_s( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf_s( stream, "%s", s, _countof(s) );  
      fscanf_s( stream, "%ld", &l );  
  
      fscanf_s( stream, "%f", &fp );  
      fscanf_s( stream, "%c", &c, 1 );  
  
      // Output data read:  
      printf( "%s\n", s );  
      printf( "%ld\n", l );  
      printf( "%f\n", fp );  
      printf( "%c\n", c );  
  
      fclose( stream );  
   }  
}  
```  
  
  **a\-string**  
**65000**  
**3.141590**  
**x**   
## 同等の .NET Framework 関数  
 [System::IO::StreamReader::ReadLine](https://msdn.microsoft.com/en-us/library/system.io.streamreader.readline.aspx).[System::Double::Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx) などの `Parse` メソッドも参照してください。  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_cscanf\_s、\_cscanf\_s\_l、\_cwscanf\_s、\_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)   
 [fprintf\_s、\_fprintf\_s\_l、fwprintf\_s、\_fwprintf\_s\_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)   
 [scanf\_s、\_scanf\_s\_l、wscanf\_s、\_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s、\_sscanf\_s\_l、swscanf\_s、\_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)   
 [fscanf、\_fscanf\_l、fwscanf、\_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)