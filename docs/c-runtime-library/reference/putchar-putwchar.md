---
title: "putchar、putwchar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- putchar
- putwchar
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
- putchar
- putwchar
- _puttchar
dev_langs: C++
helpviewer_keywords:
- putchar function
- _puttchar function
- characters, writing
- standard output, writing to
- putwchar function
ms.assetid: 93657c7f-cca1-4032-8e3a-cd6ab6193748
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f3320f40f822c9559b411144ecc621824eedbd3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="putchar-putwchar"></a>putchar、putwchar
**stdout** に文字を出力します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      int putchar(  
   int c   
);  
wint_t putwchar(  
   wchar_t c   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 書き込む文字。  
  
## <a name="return-value"></a>戻り値  
 書き込まれた文字を返します。 エラーまたはファイルの終端状態を示すには、`putc` と `putchar` は `EOF` を返します。`putwc` と `putwchar` は **WEOF** を返します。 4 つすべてのルーチンで、[ferror](../../c-runtime-library/reference/ferror.md) または [feof](../../c-runtime-library/reference/feof.md) を使用して、エラーまたはファイルの終端を確認します。 `stream` に Null ポインターが渡された場合には、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーターの例外を生成します。 実行の継続が許可された場合、これらは `EOF` または **WEOF** を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `putc` ルーチンは、出力 `c` の現在位置に 1 つの文字 `stream` を書き込みます。 任意の整数を `putc` に渡すことができますが、下位 8 ビットのみが書き込まれます。 `putchar` ルーチンは **putc(** `c`**, stdout )** と同じです。 各ルーチンでは、読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 `putc` と `putchar` はそれぞれ、`fputc` と `_fputchar` に似ていますが、関数およびマクロとして実装されます (「[関数とマクロの使い分け](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照)。 `putwc`、および `putwchar` は、それぞれ、`putc`、および `putchar` のワイド文字バージョンです。  
  
 **_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 他のスレッドをロックアウトするオーバーヘッドが発生しないため、処理が速くなる場合があります。 これらの関数は、シングルスレッド アプリケーション、呼び出し元のスコープで既にスレッド分離を処理している場合などのスレッドセーフなコンテキストでのみ使用してください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttchar`|`putchar`|`putchar`|**putwchar**|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`putchar`|\<stdio.h>|  
|`putwchar`|\<stdio.h> または \<wchar.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_putchar.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putchar( *p );  
}  
```  
  
## <a name="output"></a>出力  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fputc、fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)