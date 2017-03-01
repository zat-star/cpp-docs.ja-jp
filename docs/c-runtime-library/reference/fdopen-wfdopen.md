---
title: "_fdopen、_wfdopen | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fdopen
- _wfdopen
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
apitype: DLLExport
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7c55b4d9f7de124e7bbcc89e4c649e09e35efc42
ms.lasthandoff: 02/24/2017

---
# <a name="fdopen-wfdopen"></a>_fdopen、_wfdopen
ストリームを前回下位入出力で開いたファイルに関連付けます。  
  
## <a name="syntax"></a>構文  
  
```  
FILE *_fdopen(    
   int fd,  
   const char *mode   
);  
FILE *_wfdopen(   
   int fd,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `fd`  
 開いているファイルのファイル記述子。  
  
 `mode`  
 ファイル アクセスの種類。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、開いているストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` は `EBADF` に設定されて無効なファイル記述子であることを示すか、`EINVAL` に設定されて `mode` が null ポインターだったことを示すかのいずれかになります。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 `_fdopen` 関数は、`fd` によって識別されるファイルに入出力ストリームを関連付けることにより、下位入出力で開かれているファイルをバッファーおよびフォーマットできるようにします。 `_wfdopen` 関数は、`_fdopen` 関数のワイド文字バージョンです。`mode` 関数の引数 `_wfdopen` は、ワイド文字列です。 それ以外では、`_wfdopen` と `_fdopen` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|  
  
 `mode` 文字列は、ファイルおよびファイル アクセスの種類を指定します。  
  
 文字列 `mode` は、次の表に示すように、ファイルに要求するアクセスの種類を指定します。  
  
 `"r"`  
 読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、`fopen` 呼び出しは失敗します。  
  
 `"w"`  
 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a"`  
 末尾に書き込みができるようにファイルを開きます (追加モード)。 ファイルが存在しない場合は、作成します。  
  
 `"r+"`  
 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。  
  
 `"w+"`  
 読み取りと書き込みの両方のモードで空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a+"`  
 読み取りと追加の両方のモードでファイルを開きます。 ファイルが存在しない場合は、作成します。  
  
 アクセスの種類 `"a"` または `"a+"` を使用してファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。 ファイル ポインターは `fseek` または `rewind` を使用して移動できますが、書き込み操作の前に必ずファイルの末尾に戻されます。 したがって、既存のデータは上書きされません。 `"r+"`、`"w+"`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます (ファイルは "更新" モードで開きます)。 ただし、読み取りと書き込みを切り替える場合は、その前に `fflush`、`fsetpos`、`fseek`、または `rewind` のいずれかの操作を実行する必要があります。 必要であれば、`fsetpos` または `fseek` 操作の現在の位置を指定できます。  
  
 上記の値に加え、`mode` に次の文字を追加して、改行文字の変換モードを指定することもできます。  
  
 `t`  
 ファイルをテキスト (変換) モードで開きます。 このモードでは、復帰と改行 (CR-LF) の組み合わせは入力時に&1; つの改行 (LF) 文字に変換され、LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りおよび書き込みの両方のモードで開かれたファイルでは、`fopen` がファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、Ctrl + Z で終わるファイルの中身を `fseek` 関数および `ftell` 関数を使用して移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。  
  
 `b`  
 バイナリ (無変換) モードで開きます。 `t` モードからの変換は何も行われません。  
  
 `c`  
 関連付けられた `filename` のコミット フラグを有効にして、 `fflush` または `_flushall` のいずれかが呼び出された場合に、ファイル バッファーの内容がディスクに直接書き込まれるようにします。  
  
 `n`  
 関連付けられた `filename` のコミット フラグを "コミットなし" にリセットします。 既定値です。 プログラムを Commode.obj とリンクする場合は、グローバル コミット フラグもオーバーライドします。 プログラムを明示的に Commode.obj とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です。  
  
 `t`、`c`、および `n` `mode` オプションは、`fopen` と `_fdopen` の Microsoft の拡張機能です。 ANSI の移植性を維持する場合には使用しないでください。  
  
 `t` または `b` を `mode`に指定しないと、既定の変換モードは [_fmode](../../c-runtime-library/fmode.md) グローバル変数によって定義されます。 `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL`が返されます。 テキスト モードとバイナリ モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
 `fopen` および `_fdopen` で使用される `mode` 文字列として有効な文字は、[_open](../../c-runtime-library/reference/open-wopen.md) および [_sopen](../../c-runtime-library/reference/sopen-wsopen.md) で使用される引数 `oflag` と次のように対応しています。  
  
|`mode` 文字列の文字|`_open`/`_sopen` に相当する `oflag` 値|  
|---------------------------------|---------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (通常は `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (通常は `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT`)|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (通常は `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (通常は `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|なし|  
|`n`|なし|  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`_fdopen`|\<stdio.h>|  
|`_wfdopen`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="example"></a>例  
  
```  
// crt_fdopen.c  
// This program opens a file by using low-level  
// I/O, then uses _fdopen to switch to stream  
// access. It counts the lines in the file.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  fd, count = 0;  
   char inbuf[128];  
  
   // Open a file.  
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
      exit( 1 );  
  
   // Get stream from file descriptor.  
   if( (stream = _fdopen( fd, "r" )) == NULL )  
      exit( 1 );  
  
   while( fgets( inbuf, 128, stream ) != NULL )  
      count++;  
  
   // After _fdopen, close by using fclose, not _close.  
   fclose( stream );  
   printf( "Lines in file: %d\n", count );  
}  
```  
  
## <a name="input-crtfdopentxt"></a>入力: crt_fdopen.txt  
  
```  
Line one  
Line two  
```  
  
### <a name="output"></a>出力  
  
```  
Lines in file: 2  
```  
  
## <a name="net-framework-equivalent"></a>同等の .NET Framework 関数  
 <xref:System.IO.FileStream.%23ctor%2A>  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [_dup、_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)
