---
title: "ungetc、ungetwc | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
dev_langs:
- C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d65453f1254e4c42658ef6f27d7c90d2ad0022b9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="ungetc-ungetwc"></a>ungetc、ungetwc
ストリームに文字をプッシュ バックします。  
  
## <a name="syntax"></a>構文  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `c`  
 プッシュする文字。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功すると、これらの各関数は引数を返します文字`c`です。 
          `c` がプッシュ バックできない場合、または文字が読まれなかった場合は、入力ストリームは変更されず、`ungetc` は `EOF` を返します。`ungetwc` は、`WEOF` を返します。 `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`EOF` または `WEOF` が返され、`errno` が `EINVAL` に設定されます。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `ungetc` 関数は `c` に文字 `stream` をプッシュ バックし、EOF インジケーターをクリアします。 ストリームは、読み取り用に開かれている必要があります。 それ以降の読み取り操作`stream`で始まる`c`です。 
          `EOF` を使用してストリームに `ungetc` をプッシュする操作は無視されます。  
  
 `ungetc` がストリームに入れた文字は、その文字をストリームから読み取る前に `fflush`、`fseek`、`fsetpos`、または `rewind` が呼び出されると削除されることがあります。 ファイル位置インジケーターの値は、文字がプッシュ バックされる前のファイル位置インジケーターの値になります。 ストリームに対応する外部のストレージは変更されません。 テキスト ストリームに対する `ungetc` の正常な呼び出しでは、プッシュ バックされたすべての文字が読み取りまたは破棄されるまで、ファイル位置インジケーターは未指定です。 バイナリ ストリームに対する `ungetc` の正常な呼び出しでは、ファイル位置インジケーターがデクリメントされます。呼び出し前の値が 0 の場合、呼び出しの後の値は未定義です。  
  
 `ungetc` を 2 回の呼び出したときに、呼び出しの間に読み取りまたはファイル位置の操作をしなかった場合は、結果は予測できません。 `fscanf` の呼び出し後に、他の読み取り操作 (`ungetc` など) が行われない場合は、`getc` の呼び出しが失敗する可能性があります。 これは `fscanf` 自体が `ungetc` を呼び出すためです。  
  
 `ungetwc` 関数は、`ungetc` 関数のワイド文字バージョンです。 しかし、テキスト ストリームまたはバイナリ ストリームに対する `ungetwc` の正常な呼び出しでは、プッシュ バックされたすべての文字が読み取りまたは破棄されるまで、ファイル位置インジケーターの値は未指定です。  
  
 これらの関数はスレッド セーフであり、実行時に重要情報をロックします。 ロックしないバージョンについては、「[_ungetc_nolock、_ungetwc_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md)」をご覧ください。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## <a name="requirements"></a>必要条件  
  
|ルーチンによって返される値|必須ヘッダー|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h>|  
|`ungetwc`|\<stdio.h> または \<wchar.h>|  
  
コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル`stdin`、 `stdout`、および`stderr`、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。
  
## <a name="example"></a>例  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
```Output  
  
      521aNumber = 521  
Next character in stream = 'a'  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [getc、getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)