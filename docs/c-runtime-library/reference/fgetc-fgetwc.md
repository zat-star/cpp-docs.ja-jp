---
title: "fgetc、fgetwc | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetwc
- fgetc
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fgettc
- fgetwc
- fgetc
dev_langs:
- C++
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 5a0a697a4ba7cfea7c24809796179861fccc2f68
ms.contentlocale: ja-jp
ms.lasthandoff: 03/29/2017

---
# <a name="fgetc-fgetwc"></a>fgetc、fgetwc
ストリームから単一の文字を読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
int fgetc(   
   FILE *stream   
);  
wint_t fgetwc(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 `fgetc` は、読み込まれた文字を `int` として返すか、エラーまたはファイルの末尾を示す `EOF` を返します。 `fgetwc` は、読み込まれた文字に相当するワイド文字を [wint_t](../../c-runtime-library/standard-types.md) として返すか、エラーまたはファイルの末尾を示す `WEOF` を返します。 両方の関数に対して、エラーと、ファイルの末尾の条件を識別するため `feof` または `ferror` を使用します。 読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、`fgetc` と `fgetwc` によって無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EOF` を返します。  
  
## <a name="remarks"></a>コメント  
 これらの各関数は、`stream` に関連付けられているファイルの現在の位置から 1 文字を読み取ります。 関数は、次の文字 (定義されている場合) を指すように、関連ファイルのポインターをインクリメントします。 ストリームがファイルの末尾にある場合、ストリームのファイルの末尾を示すインジケーターが設定されます。  
  
 `fgetc` は `getc` と同じですが、関数とマクロではなく関数としてのみ実装されています。  
  
 `fgetwc` は `fgetc` のワイド文字バージョンです。`stream` がテキスト モードとバイナリ モードのどちらで開かれるかに従って、マルチバイト文字またはワイド文字として `c` が読み取られます。  
  
 `_nolock` サフィックス付きのバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。  
  
 テキスト モードとバイナリ モードのワイド文字とマルチバイト文字の処理の詳細については、「[Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」 (テキスト モードとバイナリ モードの Unicode ストリーム入出力) を参照してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fgettc`|`fgetc`|`fgetc`|`fgetwc`|  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fgetc`|\<stdio.h>|  
|`fgetwc`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_fgetc.c  
// This program uses getc to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   FILE *stream;  
   char buffer[81];  
   int  i, ch;  
  
   // Open file to read line from:  
   fopen_s( &stream, "crt_fgetc.txt", "r" );  
   if( stream == NULL )  
      exit( 0 );  
  
   // Read in first 80 characters and place them in "buffer":   
   ch = fgetc( stream );  
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = fgetc( stream );  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetctxt"></a>入力: crt_fgetc.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>出力  
  
```  
Line one.  
Line two.  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)
