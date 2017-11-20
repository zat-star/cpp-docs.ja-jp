---
title: "freopen、_wfreopen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs: C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f25c4966b567d165be8f33a0c04f58ba0ac611b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="freopen-wfreopen"></a>freopen、_wfreopen
ファイル ポインターを再度割り当てます。 これらの関数にはセキュリティが強化されたバージョンがあります。「[freopen_s、_wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
FILE *freopen(   
   const char *path,  
   const char *mode,  
   FILE *stream   
);  
FILE *_wfreopen(   
   const wchar_t *path,  
   const wchar_t *mode,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `path`  
 新しいファイル パス。  
  
 `mode`  
 アクセス許可の種類。  
  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、新しく開かれたファイルへのポインターを返します。 エラーが発生した場合、元のファイルは閉じられ、関数は `NULL` ポインター値を返します。 `path`、`mode`、または `stream` が null ポインターであるか、`filename` が空の文字列である場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`NULL` を返します。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
## <a name="remarks"></a>コメント  
 これらの関数にはセキュリティが強化されたバージョンがあります。「[freopen_s、_wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md)」を参照してください。  
  
 `freopen`関数が現在関連付けられているファイルを閉じます`stream`し再割り当て`stream`によって指定されたファイルに`path`です。 `_wfreopen` は `_freopen` のワイド文字バージョンであり、`_wfreopen` に対する `path` 引数と `mode` 引数はワイド文字列です。 それ以外では、`_wfreopen` と `_freopen` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen` は、通常、既に開いているファイル `stdin`、`stdout`、および `stderr` のユーザーが指定したファイルへのリダイレクトに使用されます。 関連付けられている新しいファイル`stream`でが開きます。 `mode`、どのファイルは、次のように要求されるアクセスの種類を指定する文字の文字列です。  
  
 `"r"`  
 読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、`freopen` 呼び出しは失敗します。  
  
 `"w"`  
 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a"`  
 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF マーカーを削除せずにファイルに新しいデータを書き込みます。ファイルが存在しない場合は、作成します。  
  
 `"r+"`  
 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。  
  
 `"w+"`  
 読み取りと書き込みの両方のモードで空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a+"`  
 読み取りと追加の両方のモードでファイルを開きます。追加時には、ファイルに新しいデータを書き込む前に EOF マーカーが削除され、書き込みが終了すると EOF マーカーが復元されます。ファイルが存在しない場合は、作成します。  
  
 既存のファイルを破棄するため、`"w"` と `"w+"` の型は注意して使用します。  
  
 アクセスの種類が `"a"` または `"a+"` の場合にファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。 ファイル ポインターは `fseek` 関数または `rewind` 関数を使用して移動できますが、書き込み操作の前に必ずファイルの終端に戻されます。したがって、既存のデータは上書きされません。  
  
 `"a"` モードでは、ファイルへの追加の前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 `"a+"` モードでは、ファイルへの追加の前に EOF マーカーが削除されます。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 Ctrl + Z EOF マーカーで終了するストリーム ファイルに追加するには、`"a+"` モードを使用する必要があります。  
  
 `"r+"`、`"w+"`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます (ファイルは "更新" モードで開きます)。 ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](../../c-runtime-library/reference/fsetpos.md)、[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)、または [rewind](../../c-runtime-library/reference/rewind.md) のいずれかの関数を実行する必要があります。 必要に応じて、`fsetpos` 関数または `fseek` 関数には現在位置を指定できます。 上記の値に加え、`mode` 文字列に次の文字の 1 つを追加すると、改行の変換モードを指定できます。  
  
 `t`  
 テキスト (変換モードで開きます)。復帰と改行 (CR-LF) の組み合わせは入力; 上の 1 つの改行 (LF) 文字に変換します。LF 文字は、出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 `"a+"` を使用して読み取りモード、または読み取りおよび書き込みの両方のモードで開かれたファイルでは、ランタイム ライブラリがファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、ファイルの中身を `fseek` 関数および `ftell` 関数で移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。 `t` オプションは、Microsoft 拡張機能です。ANSI 互換が必要な場合は使用しないでください。  
  
 `b`  
 バイナリ (未変換) モードで開き、前述の変換は抑制されます。  
  
 `t` または `b` を `mode` に指定しないと、既定の変換モードは [_fmode](../../c-runtime-library/fmode.md) グローバル変数によって定義されます。 `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL`が返されます。  
  
 テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`freopen`|\<stdio.h>|  
|`_wfreopen`|\<stdio.h> または \<wchar.h>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。 コンソール (`stdin`、`stdout`、および `stderr`) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// crt_freopen.c  
// compile with: /W3  
// This program reassigns stderr to the file  
// named FREOPEN.OUT and writes a line to that file.  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   // Reassign "stderr" to "freopen.out":   
   stream = freopen( "freopen.out", "w", stderr ); // C4996  
   // Note: freopen is deprecated; consider using freopen_s instead  
  
   if( stream == NULL )  
      fprintf( stdout, "error on freopen\n" );  
   else  
   {  
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );  
      fprintf( stream, "This will go to the file 'freopen.out'\n" );  
      fclose( stream );  
   }  
   system( "type freopen.out" );  
}  
```  
  
```Output  
successfully reassigned  
This will go to the file 'freopen.out'  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen、wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen、_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)