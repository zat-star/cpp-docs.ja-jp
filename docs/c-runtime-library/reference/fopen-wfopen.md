---
title: "fopen、_wfopen | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen
- fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
dev_langs: C++
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
caps.latest.revision: "56"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01558dfa6b28f10746c1487384bad44768b5877e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fopen-wfopen"></a>fopen、_wfopen
ファイルを開きます。 追加のパラメーター検証を実行してエラー コードを返す、セキュリティが強化されたバージョンの機能が使用できます。「[fopen_s、_wfopen_s](../../c-runtime-library/reference/fopen-s-wfopen-s.md)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```  
FILE *fopen(   
   const char *filename,  
   const char *mode   
);  
FILE *_wfopen(   
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `filename`  
 ファイル名。  
  
 `mode`  
 有効なアクセス種類。  
  
## <a name="return-value"></a>戻り値  
 これらの各関数は、開いているファイルへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 `filename` または `mode` が `NULL` または空の文字列の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効パラメーター ハンドラーを呼び出します。 実行の継続が許可された場合、これらの関数は `NULL` を返し、 `errno` を `EINVAL`に設定します。  
  
 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `fopen` 関数は、 `filename`で指定されたファイルを開きます。 既定では、幅の狭い `filename` 文字列は、ANSI コード ページ (CP_ACP) を使用して解釈されます。 Windows デスクトップ アプリケーションでは、 [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx) 関数を使用して、これを OEM コード ページ (CP_OEMCP) に変更できます。 [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx) 関数を使用して、 `filename` が ANSI またはシステムの既定の OEM コード ページのいずれを使用して解釈されるかを決定できます。 `_wfopen` は `fopen`のワイド文字バージョンであり、 `_wfopen` の引数はワイド文字列です。 それ以外では、 `_wfopen` と `fopen` の動作は同じです。 単に `_wfopen` を使用する場合、ファイル ストリームで使用されるコード化文字セットには影響しません。  
  
 `fopen` は、実行時にファイル システムで有効なパスを受け取ります。 `fopen` は、コードを実行するシステムが実行時に共有ネットワーク ドライブまたは割り当てられたネットワーク ドライブにアクセスする限り、UNC パスおよび割り当てられたネットワーク ドライブを含むパスを受け取ります。 `fopen`のパスを構築する場合は、ドライブ、パス、またはネットワーク共有が実行時環境で使用できることを確認してください。 ディレクトリのパス区切り記号としてスラッシュ (/) または円記号 (\\) のどちらかを使用できます。  
  
 ファイルでその他の操作を実行する前には、必ず戻り値をチェックしてポインターが NULL かどうかを確認します。 エラーが発生した場合、 `errno` グローバル変数が設定され、特定のエラー情報を取得するために使用されることがあります。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="unicode-support"></a>Unicode のサポート  
 `fopen` は Unicode のファイル ストリームをサポートします。 Unicode ファイルを開くには、次のように、目的のエンコーディングを指定する `ccs` フラグを `fopen`に渡します。  
  
 `FILE *fp = fopen("newfile.txt", "rt+, ccs=encoding");`  
  
 `encoding` に指定できる値は、 `UNICODE`、 `UTF-8`、および `UTF-16LE`です。  
  
 ファイルが Unicode モードで開かれると、Input 関数によって、ファイルから読み取られたデータは `wchar_t`型として格納された UTF-16 データに変換されます。 Unicode モードで開かれたファイルに書き込む関数は、 `wchar_t`型として格納された UTF-16 データがバッファーに含まれていると想定します。 ファイルが UTF-8 としてエンコードされている場合、UTF-16 データは書き込まれるときに UTF-8 に変換され、ファイルの UTF-8 でエンコードされた内容は読み取られるときに UTF-16 に変換されます。 Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、 [パラメーター検証](../../c-runtime-library/parameter-validation.md) エラーが発生します。 UTF-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。 必要なエンコード変換は各自が行う必要があります。  
  
 既に存在するファイルを読み取り用または追加用に開く場合は、ファイル内にバイト順マーク (BOM: Byte Order Mark) があれば、それによってエンコーディングが決定されます。 BOM エンコーディングは、 `ccs` フラグで指定されたエンコーディングよりも優先されます。 `ccs` エンコーディングは、BOM が表示されていない場合またはファイルが新しいファイルの場合にのみ使用されます。  
  
> [!NOTE]
>  BOM 検出は、Unicode モードで (つまり、 `ccs` フラグを渡して) 開かれたファイルにのみ適用されます。  
  
 `ccs` に指定される各種の `fopen` フラグとファイル内のバイト順マークに応じて、使用されるモードを次の表に示します。  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs フラグおよび BOM に基づいて使用されるエンコーディング  
  
|`ccs` フラグ|BOM なし (または新しいファイル)|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 Unicode モードで書き込むように開かれたファイルには、自動的に BOM が書き込まれます。  
  
 `mode` が「`a, ccs=<encoding>`」の場合、 `fopen` は、まず読み取りアクセスと書き込みアクセスの両方を使用してファイルを開こうとします。 成功すると、この関数は BOM を読み取ってファイルのエンコーディングを決定します。失敗した場合は、ファイルに対して既定のエンコーディングを使用します。 どちらの場合も、 `fopen` は、書き込み専用アクセスを使用してファイルを開き直します。 これは `a` モードにのみ適用され、 `a+` モードには適用されません。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen`|`fopen`|`fopen`|`_wfopen`|  
  
 `mode` 文字列では、次のように、ファイルに要求するアクセスの種類を指定します。  
  
 `"r"`  
 読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、 `fopen` 呼び出しは失敗します。  
  
 `"w"`  
 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a"`  
 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF (end-of-file) マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。  
  
 `"r+"`  
 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。  
  
 `"w+"`  
 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a+"`  
 読み取りと追加の両方のモードでファイルを開きます。 追加操作には、新しいデータをファイルに書き込む前に EOF マーカーを削除することが含まれます。 書き込みの完了後に、EOF マーカーは復元されません。 ファイルが存在しない場合は、作成します。  
  
 アクセスの種類 `"a"` またはアクセス種類 `"a+"` を使用してファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。 ファイル ポインターは `fseek` 関数または `rewind`関数を使用して移動できますが、書き込み操作が実行される前に必ずファイルの終端に戻されます。 したがって、既存のデータは上書きされません。  
  
 `"a"` モードでは、ファイルへの追加の前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 `"a+"` モードでは、ファイルへの追加の前に EOF マーカーは削除されます。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 Ctrl + Z EOF マーカーで終了するストリーム ファイルに追加するには、 `"a+"` モードを使用する必要があります。  
  
 `"r+"`、 `"w+"`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます (ファイルは「更新」モードで開きます)。 ただし、読み取りから書き込みに切り替えると、入力操作は EOF マーカーを検出する必要があります。 EOF がない場合、ファイル ポジショニング関数の中間の呼び出しを使用する必要があります。 ファイル ポジショニング関数は、 `fsetpos`、 `fseek`、および `rewind`です。 書き込みから読み取りに切り替えると、 `fflush` またはファイル ポジショニング関数に中間の呼び出しを使用する必要があります。  
  
 上記の値に加え、 `mode` に次の文字を追加すると、改行文字の変換モードを指定できます。  
  
 `t`  
 ファイルをテキスト (変換) モードで開きます。 このモードでは、Ctrl + Z は入力時に EOF 文字として解釈されます。 `"a+"`を使用して読み取りおよび書き込みの両方のモードで開かれたファイルでは、 `fopen` がファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、Ctrl +Z で終わるファイルの中身を `fseek` 関数および `ftell` 関数で移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。  
  
 テキスト モードでは、復帰と改行の組み合わせは、入力、1 つの改行に変換し、ライン フィード文字は出力時に復帰と改行の組み合わせに変換します。 Unicode のストリーム入出力関数が既定のテキスト モードで動作すると、入力元または出力先のストリームはマルチバイト文字のシーケンスと仮定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、 `mbtowc` 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 `wctomb` 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。  
  
 `b`  
 ファイルをバイナリ (無変換) モードで開きます。キャリッジ リターンとライン フィードの変換は行われません。  
  
 `t` または `b` を `mode`に指定しないと、既定の変換モードは [_fmode](../../c-runtime-library/fmode.md)グローバル変数によって定義されます。 `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL`が返されます。  
  
 Unicode およびマルチバイトのストリーム入出力でテキスト モードとバイナリ モードを使用する方法について詳しくは、「 [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 」および「 [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」をご覧ください。  
  
 `c`  
 関連付けられた `filename` のコミット フラグを有効にして、 `fflush` または `_flushall` のいずれかが呼び出された場合に、ファイル バッファーの内容がディスクに直接書き込まれるようにします。  
  
 `n`  
 関連付けられた `filename` のコミット フラグを "コミットなし" にリセットします。 既定値です。 プログラムを COMMODE.OBJ とリンクする場合は、グローバル コミット フラグもオーバーライドします。 プログラムを明示的に COMMODE.OBJ とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です (「 [Link Options](../../c-runtime-library/link-options.md)」をご覧ください)。  
  
 `N`  
 ファイルが子プロセスによって継承されないように指定します。  
  
 `S`  
 キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。  
  
 `R`  
 キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。  
  
 `T`  
 ファイルを一時ファイルとして指定します。 可能な場合、ファイルはディスクにフラッシュされません。  
  
 `D`  
 ファイルを一時ファイルとして指定します。 最後のファイル ポインターが閉じられると、ファイルは削除されます。  
  
 `ccs=ENCODING`  
 このファイルに使用するコード化された文字セット (`UTF-8`、 `UTF-16LE`、または `UNICODE`) を指定します。 何も指定しない場合は、ANSI エンコーディングが使用されます。  
  
 `mode` および `fopen` で使用される `_fdopen` 文字列として有効な文字は、 `oflag` および [_open](../../c-runtime-library/reference/open-wopen.md) で使用される [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)引数と次のように対応しています。  
  
|mode 文字列の文字|`_open`/`_sopen` に相当する `oflag` 値|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (通常は `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (通常は `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (通常は `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (通常は `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|なし|  
|`n`|なし|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 `rb` モードを使用していて、コードを移植する必要がなく、大量のファイルを読み込む予定があり、ネットワーク パフォーマンスを気にする必要がない場合は、Win32 メモリ マップト ファイルもオプションとして検討できます。  
  
## <a name="requirements"></a>必要条件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fopen`|\<stdio.h>|  
|`_wfopen`|\<stdio.h> または \<wchar.h>|  
  
 `_wfopen` は Microsoft 拡張機能です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
 `c`、 `n`、 `t`、 `S`、 `R`、 `T`、および `D` `mode` オプションは、 `fopen` と `_fdopen` と should not be used where ANSI portability is desired.  
  
## <a name="example"></a>例  
 次のプログラムは 2 ファイルを開きます。  このプログラムでは、 `fclose` 関数を使用して最初のファイルを閉じ、 `_fcloseall` 関数を使用して残りのすべてのファイルを閉じます。  
  
```C  
// crt_fopen.c  
// compile with: /W3  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   int numclosed;  
  
   // Open for read (will fail if file "crt_fopen.c" does not exist)  
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996  
   // Note: fopen is deprecated; consider using fopen_s instead  
      printf( "The file 'crt_fopen.c' was not opened\n" );  
   else  
      printf( "The file 'crt_fopen.c' was opened\n" );  
  
   // Open for write   
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996  
      printf( "The file 'data2' was not opened\n" );  
   else  
      printf( "The file 'data2' was opened\n" );  
  
   // Close stream if it is not NULL   
   if( stream)  
   {  
      if ( fclose( stream ) )  
      {  
         printf( "The file 'crt_fopen.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:   
   numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="example"></a>例  
 次のプログラムでは、Unicode エンコーディングのテキスト モードで、ファイルを作成します (ファイルが存在する場合は上書きします)。  その後、2 つの文字列をファイルに書き込み、ファイルを閉じます。 _wfopen_test.xml というファイルが出力されます。このファイルには、出力セクションのデータが格納されます。  
  
```C  
// crt__wfopen.c  
// compile with: /W3  
// This program creates a file (or overwrites one if  
// it exists), in text mode using Unicode encoding.  
// It then writes two strings into the file  
// and then closes the file.  
  
#include <stdio.h>  
#include <stddef.h>  
#include <stdlib.h>  
#include <wchar.h>  
  
#define BUFFER_SIZE 50  
  
int main(int argc, char** argv)  
{  
    wchar_t str[BUFFER_SIZE];  
    size_t  strSize;  
    FILE*   fileHandle;  
  
    // Create an the xml file in text and Unicode encoding mode.  
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996  
    // Note: _wfopen is deprecated; consider using _wfopen_s instead  
    {  
        wprintf(L"_wfopen failed!\n");  
        return(0);  
    }  
  
    // Write a string into the file.  
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");  
    strSize = wcslen(str);  
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)  
    {  
        wprintf(L"fwrite failed!\n");  
    }  
  
    // Write a string into the file.  
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");  
    strSize = wcslen(str);  
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)  
    {  
        wprintf(L"fwrite failed!\n");  
    }  
  
    // Close the file.  
    if (fclose(fileHandle))  
    {  
        wprintf(L"fclose failed!\n");  
    }  
    return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen、_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen、_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen、_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)