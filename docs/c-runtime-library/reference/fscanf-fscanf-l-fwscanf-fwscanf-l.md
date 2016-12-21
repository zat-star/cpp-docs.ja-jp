---
title: "fscanf、_fscanf_l、fwscanf、_fwscanf_l | Microsoft Docs"
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
  - "fscanf"
  - "_fwscanf_l"
  - "_fscanf_l"
  - "fwscanf"
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
  - "fscanf"
  - "fwscanf"
  - "_ftscanf_l"
  - "_fwscanf_l"
  - "_ftscanf"
  - "_fscanf_l"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fscanf_l 関数"
  - "_ftscanf 関数"
  - "_ftscanf_l 関数"
  - "_fwscanf_l 関数"
  - "データ [CRT], 読み取り (ストリームから)"
  - "書式付きデータ [C++], 読み取り (ストリームから)"
  - "fscanf 関数"
  - "fscanf_l 関数"
  - "ftscanf 関数"
  - "ftscanf_l 関数"
  - "fwscanf 関数"
  - "fwscanf_l 関数"
  - "ストリーム [C++], 読み取り (書式付きデータを)"
ms.assetid: 9004e978-6c5f-4bb2-98fd-51e5948933f2
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fscanf、_fscanf_l、fwscanf、_fwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリームから書式化されたデータを読み出します。  これらの関数のセキュリティを強化したバージョンについては、「[fscanf\_s、\_fscanf\_s\_l、fwscanf\_s、\_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)」を参照してください。  
  
## 構文  
  
```  
int fscanf(   
   FILE *stream,  
   const char *format [,  
   argument ]...   
);  
int _fscanf_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...   
);  
int fwscanf(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...   
);  
int _fwscanf_l(   
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
 これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。  戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。  エラーが発生した場合や、最初の変換の前にファイル ストリームの終端を検出した場合、`fscanf` および `fwscanf` は `EOF` を返します。  
  
 これらの関数では、パラメーターの検証が行われます。  `stream` または `format` が null ポインターの場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続が許可された場合、これらの関数は `EOF` を返し、`errno` を `EINVAL` に設定します。  
  
## 解説  
 `fscanf` 関数は、`stream` の現在位置から `argument` \(ある場合\) で指定された位置にデータを読み込みます。  各 `argument` は、`format` の型指定子に対応する型の変数へのポインターにする必要があります。  `format` は、入力フィールドの解釈を制御し、`scanf`の `format` の引数と同じフォームと関数がある; `format`の説明の [scanf 関数](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) を参照してください*。*  
  
 `fwscanf` 関数は、`fscanf` 関数のワイド文字バージョンです。`fwscanf` の format 引数は、ワイド文字列です。  ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。  `fscanf` では、UNICODE ストリームからの入力はサポートされていません。  
  
 `_l` サフィックスが付いているこれらの関数の各バージョンは、現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE & \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|--------------------------------|-----------------------|--------------------------|  
|`_ftscanf`|`fscanf`|`fscanf`|`fwscanf`|  
|`_ftscanf_l`|`_fscanf_l`|`_fscanf_l`|`_fwscanf_l`|  
  
 詳細については、「[scanf 関数と wscanf 関数の書式指定フィールド](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fscanf`, `_fscanf_l`|\<stdio.h\>|  
|`fwscanf`, `_fwscanf_l`|\<stdio.h\> または \<wchar.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_fscanf.c  
// compile with: /W3  
// This program writes formatted  
// data to a file. It then uses fscanf to  
// read the various data back from the file.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long l;  
   float fp;  
   char s[81];  
   char c;  
  
   if( fopen_s( &stream, "fscanf.out", "w+" ) != 0 )  
      printf( "The file fscanf.out was not opened\n" );  
   else  
   {  
      fprintf( stream, "%s %ld %f%c", "a-string",   
               65000, 3.14159, 'x' );  
      // Security caution!  
      // Beware loading data from a file without confirming its size,  
      // as it may lead to a buffer overrun situation.  
  
      // Set pointer to beginning of file:  
      fseek( stream, 0L, SEEK_SET );  
  
      // Read data back from file:  
      fscanf( stream, "%s", s );   // C4996  
      fscanf( stream, "%ld", &l ); // C4996  
  
      fscanf( stream, "%f", &fp ); // C4996  
      fscanf( stream, "%c", &c );  // C4996  
      // Note: fscanf is deprecated; consider using fscanf_s instead  
  
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
 [\_cscanf、\_cscanf\_l、\_cwscanf、\_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [fprintf、\_fprintf\_l、fwprintf、\_fwprintf\_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf、\_scanf\_l、wscanf、\_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sscanf、\_sscanf\_l、swscanf、\_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)   
 [fscanf\_s、\_fscanf\_s\_l、fwscanf\_s、\_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)