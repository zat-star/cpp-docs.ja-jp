---
title: "_fdopen、_wfdopen | Microsoft ドキュメント"
ms.custom: 
ms.date: 12/12/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
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
dev_langs: C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7108fdedb2698e6065c22ebe6905d897ee389ece
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fdopen-wfdopen"></a>_fdopen、_wfdopen

ストリームを前回下位入出力で開いたファイルに関連付けます。

## <a name="syntax"></a>構文

```c
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>パラメーター

*fd*  
開いているファイルのファイル記述子。

*モード*  
ファイル アクセスの種類。

## <a name="return-value"></a>戻り値

これらの各関数は、開いているストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、`errno` は `EBADF` に設定されて無効なファイル記述子であることを示すか、`EINVAL` に設定されて `mode` が null ポインターだったことを示すかのいずれかになります。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

`_fdopen`関数では関連付けますによって識別されるファイルの I/O ストリーム*fd*、できるので、低レベルの i/o バッファーおよびフォーマットが開かれているファイル。 `_wfdopen`ワイド文字バージョンは、 `_fdopen`;*モード*に渡す引数`_wfdopen`ワイド文字列です。 それ以外では、`_wfdopen` と `_fdopen` の動作は同じです。

ファイル記述子に渡された`_fdopen`が所有するによって、返された`FILE *`ストリーム。 場合`_fdopen`が成功すると、呼び出すことはありません[\_閉じる](../../c-runtime-library/reference/close.md)ファイル記述子。 呼び出す[fclose](../../c-runtime-library/reference/fclose-fcloseall.md)で返された`FILE *`もファイル記述子を閉じます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|\_UNICODE と\_MBCS が定義されていません|\_MBCS の定義|\_UNICODE の定義|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|

*モード*文字の文字列をファイルに、要求のファイル アクセスの種類を指定します。  

`"r"`  
読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、 `fopen` 呼び出しは失敗します。

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

アクセスの種類 `"a"` または `"a+"` を使用してファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。 ファイル ポインターは `fseek` または `rewind` を使用して移動できますが、書き込み操作の前に必ずファイルの末尾に戻されます。したがって、既存のデータは上書きされません。 `"r+"`、`"w+"`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます (ファイルは "更新" モードで開きます)。 ただし、読み取りと書き込みを切り替える場合は、その前に `fflush`、`fsetpos`、`fseek`、または `rewind` のいずれかの操作を実行する必要があります。 必要であれば、`fsetpos` または `fseek` 操作の現在の位置を指定できます。

上記の値に加え、次の文字含めることもできますで*モード*改行文字の変換モードを指定します。

`t`  
ファイルをテキスト (変換) モードで開きます。 このモードでは、復帰と改行 (CR-LF) の組み合わせは入力時に 1 つの改行 (LF) 文字に変換され、LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取りおよび書き込みの両方のモードで開かれたファイルでは、`fopen` がファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、Ctrl + Z で終わるファイルの中身を `fseek` 関数および `ftell` 関数を使用して移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。

`b`  
バイナリ (無変換) モードで開きます。 `t` モードからの変換は何も行われません。

`c`  
関連付けられた `filename` のコミット フラグを有効にして、 `fflush` または `_flushall` のいずれかが呼び出された場合に、ファイル バッファーの内容がディスクに直接書き込まれるようにします。

`n`  
関連付けられた `filename` のコミット フラグを "コミットなし" にリセットします。 既定値です。 プログラムを Commode.obj とリンクする場合は、グローバル コミット フラグもオーバーライドします。プログラムを明示的に Commode.obj とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です。

`t`、 `c`、および`n`*モード*オプションは、Microsoft 拡張機能`fopen`と`_fdopen`です。 ANSI の移植性を維持する場合には使用しないでください。

場合`t`または`b`には、指定しない*モード*、既定の変換モードがグローバル変数によって定義されている[ \_fmode](../../c-runtime-library/fmode.md)です。 場合`t`または`b`は引数の先頭に、その関数は失敗し、NULL を返します。 テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

有効な文字、*モード*で使用される文字列`fopen`と`_fdopen`に対応している*oflag*で使用される引数[\_開く](../../c-runtime-library/reference/open-wopen.md)と[\_sopen](../../c-runtime-library/reference/sopen-wsopen.md)の次の表に示すようにします。

|内の文字*モード*文字列|等価*oflag*値`_open`と`_sopen`|
|---------------------------------|---------------------------------------------------|
|`a`|**\_O\_WRONLY &#124;です。\_O\_APPEND** (通常 **\_O\_WRONLY &#124;です。\_O\_CREAT &#124;です。\_O\_APPEND**)|
|`a+`|**\_O\_RDWR &#124;です。\_O\_APPEND** (通常 **\_O\_RDWR &#124;です。\_O\_APPEND &#124;です。\_O\_CREAT** )|
|`r`|**\_O\_RDONLY**|
|`r+`|**\_O\_RDWR**|
|`w`|**\_O\_WRONLY** (通常 **\_O\_WRONLY &#124;です。\_O\_CREAT &#124;です。\_O\_TRUNC**)|
|`w+`|**\_O\_RDWR** (通常 **\_O\_RDWR &#124;です。\_O\_CREAT &#124;です。\_O\_TRUNC**)|
|`b`|**\_O\_バイナリ**|
|`t`|**\_O\_テキスト**|
|`c`|なし|
|`n`|なし|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|`_fdopen`|\<stdio.h>|
|`_wfdopen`|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```c
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

### <a name="input-crtfdopentxt"></a>入力: crt_fdopen.txt

```
Line one
Line two
```

### <a name="output"></a>出力

```
Lines in file: 2
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
[\_dup、 \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
[fclose、 \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
[fopen、 \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
[freopen、 \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
[\_開くには、 \_wopen](../../c-runtime-library/reference/open-wopen.md)
