---
title: "fopen_s、_wfopen_s | Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen_s
- fopen_s
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
- fopen_s
- _tfopen_s
- _wfopen_s
dev_langs:
- C++
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
caps.latest.revision: 41
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 168d1cd797f9f7d6080f2da7aefeb8859c7f2232
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="fopens-wfopens"></a>fopen_s、_wfopen_s
ファイルを開きます。 これらのバージョンの [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。  
  
## <a name="syntax"></a>構文  
  
```  
errno_t fopen_s(   
   FILE** pFile,  
   const char *filename,  
   const char *mode   
);  
errno_t _wfopen_s(  
   FILE** pFile,  
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `pFile`  
 開かれたファイルへのポインターを受け取るファイル ポインターへのポインター。  
  
 [入力] `filename`  
 ファイル名。  
  
 [入力] `mode`  
 アクセス許可の種類。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。 これらのエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。  
  
### <a name="error-conditions"></a>エラー条件  
  
|`pFile`|`filename`|`mode`|戻り値|`pFile` の内容|  
|-------------|----------------|------------|------------------|------------------------|  
|`NULL`|任意|任意|`EINVAL`|変更なし|  
|任意|`NULL`|任意|`EINVAL`|変更なし|  
|任意|任意|NULL|`EINVAL`|変更なし|  
  
## <a name="remarks"></a>コメント  
 `fopen_s` および `_wfopen_s` で開かれたファイルは共有できません。 ファイルを共有する必要がある場合には、適切な共有モード定数 (たとえば、読み取り/書き込み共有の場合は `_SH_DENYNO`) で [_fsopen、_wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md) を使用します。  
  
 `fopen_s` 関数は、`filename` で指定されたファイルを開きます。 `_wfopen_s` は `fopen_s` のワイド文字バージョンであり、`_wfopen_s` の引数はワイド文字列です。 それ以外では、`_wfopen_s` と `fopen_s` の動作は同じです。  
  
 `fopen_s` は、実行時にファイル システムで有効なパスを受け取ります。UNC パス、および割り当てられたネットワーク ドライブを含むパスは、コードを実行するシステムが実行時に共有ネットワーク ドライブまたは割り当てられたネットワーク ドライブにアクセスする限り、`fopen_s` で受け取られます。 `fopen_s` のパスを構築する場合は、実行時環境で使用できるドライブ、パス、またはネットワーク共有に関して推測を使用しないでください。 ディレクトリのパス区切り記号としてスラッシュ (/) または円記号 (\\) のどちらかを使用できます。  
  
 これらの関数では、パラメーターの検証が行われます。 `pFile`、`filename`、または `mode` が null ポインターである場合には、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター例外を生成します。  
  
 ファイルでその他の操作を実行する前には、必ず戻り値をチェックして関数が成功したかどうかを確認します。 エラーが発生すると、エラー コードが返され、グローバル変数 `errno` が設定されます。 詳しくは、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="unicode-support"></a>Unicode のサポート  
 `fopen_s` は Unicode のファイル ストリームをサポートします。 新しいまたは既存の Unicode ファイルを開くには、次のように、目的のエンコーディングを指定する `ccs` フラグを `fopen_s` に渡します。  
  
 `fopen_s(&fp, "newfile.txt", "rw, ccs=`*エンコーディング*`");`  
  
 値を許可*エンコード*は`UNICODE`、 `UTF-8`、および`UTF-16LE`です。 値を指定しない場合の*エンコード*、 `fopen_s` ANSI エンコーディングを使用します。  
  
 既に存在するファイルを読み取り用または追加用に開く場合は、ファイル内にバイト順マーク (BOM: Byte Order Mark) があれば、それによってエンコーディングが決定されます。 BOM エンコーディングは、`ccs` フラグで指定されたエンコーディングよりも優先されます。 `ccs` エンコーディングは、BOM が表示されていない場合またはファイルが新しいファイルの場合にのみ使用されます。  
  
> [!NOTE]
>  BOM 検出は、Unicode モードで (つまり、`ccs` フラグを渡して) 開かれたファイルにのみ適用されます。  
  
 `ccs` に指定される各種の `fopen_s` フラグとファイル内のバイト順マークに応じて、モードを次の表に示します。  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>ccs フラグおよび BOM に基づいて使用されるエンコーディング  
  
|`ccs` フラグ|BOM なし (または新しいファイル)|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 Unicode モードで書き込むように開かれたファイルには、自動的に BOM が書き込まれます。  
  
 場合`mode`は"a、ccs =*エンコード*"、`fopen_s`まず読み取りアクセス権および書き込みアクセスの両方で、ファイルを開こうとします。 成功すると、この関数は BOM を読み取ってファイルのエンコーディングを決定します。失敗した場合は、ファイルに対して既定のエンコーディングを使用します。 どちらの場合も、`fopen_s` は、書き込み専用アクセスでファイルを開き直します。 これは `a` モードにのみ適用され、`a+` の場合は適用されません。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen_s`|`fopen_s`|`fopen_s`|`_wfopen_s`|  
  
 `mode` 文字列では、次のように、ファイルに要求するアクセスの種類を指定します。  
  
 `"r"`  
 読み取り用に開きます。 ファイルが存在しない場合や見つからない場合、`fopen_s` 呼び出しは失敗します。  
  
 `"w"`  
 書き込み用に空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a"`  
 末尾に書き込みができるようにファイルを開きます (追加モード)。EOF マーカーを削除せずにファイルに新しいデータを書き込みます。 ファイルが存在しない場合は、作成します。  
  
 `"r+"`  
 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。  
  
 `"w+"`  
 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a+"`  
 読み取りと追加の両方のモードでファイルを開きます。 追加時には、ファイルに新しいデータを書き込む前に EOF マーカーが削除され、書き込みが終了すると EOF マーカーが復元されます。 ファイルが存在しない場合は、作成します。  
  
 アクセスの種類 `"a"` または `"a+"` を使用してファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。 ファイル ポインターは `fseek` 関数または `rewind` 関数を使用して移動できますが、既存データを上書きしないように書き込み操作の前に必ずファイルの終端に戻されます。  
  
 `"a"` モードでは、ファイルへの追加の前に EOF マーカーは削除されません。 追加が行われても、MS-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。 `"a+"` モードでは、ファイルへの追加の前に EOF マーカーが削除されます。 追加が終了すると、MS-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。 Ctrl + Z EOF マーカーの使用で終了するストリーム ファイルに追加するには、`"a+"` モードを使用する必要があります。  
  
 ときに、 `"r+"`、`"w+",`または`"a+"`アクセスの種類を指定し、読み取りと書き込みの両方を許可します。 (ファイルは "更新" モードで開きます)。ただし、読み取りから書き込みに切り替えると、入力操作は EOF マーカーを検出する必要があります。 EOF がない場合、ファイル ポジショニング関数の中間の呼び出しを使用する必要があります。 ファイル ポジショニング関数は、`fsetpos`、`fseek`、および `rewind` です。 書き込みから読み取りに切り替えると、`fflush` またはファイル ポジショニング関数に中間の呼び出しを使用する必要があります。  
  
 上記の値に加え、`mode` に次の文字を追加すると、改行文字の変換モードを指定できます。  
  
 `t`  
 ファイルをテキスト (変換) モードで開きます。 このモードでは、Ctrl + Z は入力時に EOF (EOF: end-of-file) 文字として解釈されます。 `"a+"` を使用して読み取りおよび書き込みの両方のモードで開かれたファイルでは、`fopen_s` がファイル末尾に Ctrl + Z があるかどうかを確認し、削除できる場合は削除します。 この処理が行われる理由は、CTRL+Z で終わるファイルの中身を `fseek` 関数および `ftell` 関数で移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。  
  
 また、テキスト モードでは、復帰と改行の組み合わせは、入力、1 つの改行に変換し、ライン フィード文字は出力時に復帰と改行の組み合わせに変換します。 Unicode のストリーム入出力関数が既定のテキスト モードで動作すると、入力元または出力先のストリームはマルチバイト文字のシーケンスと仮定されます。 このため、Unicode ストリーム入力関数はマルチバイト文字をワイド文字に変換し、 `mbtowc` 関数を呼び出した場合と同様の効果を得ます。 同様の理由で、Unicode ストリーム出力関数は、 `wctomb` 関数が呼び出されたかのように、ワイド文字をマルチバイト文字に変換します。  
  
 `b`  
 ファイルをバイナリ (無変換) モードで開きます。キャリッジ リターンとライン フィードの変換は行われません。  
  
 `t` または `b` を `mode`に指定しないと、既定の変換モードは [_fmode](../../c-runtime-library/fmode.md)グローバル変数によって定義されます。 `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL`が返されます。  
  
 Unicode およびマルチバイトのストリーム入出力におけるテキスト モードおよびバイナリ モードの使い方の詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[テキスト モードとバイナリ モードの Unicode ストリーム入出力](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」を参照してください。  
  
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
 このファイルに使用するコード化された文字セット (UTF-8、UTF-16LE、および UNICODE) を指定します。 何も指定しない場合は、ANSI エンコーディングが使用されます。  
  
 `fopen_s` および `_fdopen` で使用される `mode` 文字列として有効な文字は、[_open](../../c-runtime-library/reference/open-wopen.md) および [_sopen](../../c-runtime-library/reference/sopen-wsopen.md) で使用される `oflag` 引数と次のように対応しています。  
  
|mode 文字列の文字|`_open`/`_sopen` に相当する `oflag` 値|  
|-------------------------------|----------------------------------------------------|  
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
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 `rb` モードを使用していて、コードを移植する必要がなく、大量のファイルを読み込む予定があり、ネットワーク パフォーマンスを気にする必要がない場合は、Win32 メモリ マップト ファイルも省略できます。  
  
## <a name="requirements"></a>要件  
  
|関数|必須ヘッダー|  
|--------------|---------------------|  
|`fopen_s`|\<stdio.h>|  
|`_wfopen_s`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、概要の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
 `c`、`n`、および `t` `mode` オプションは、`fopen_s` および `_fdopen` の Microsoft 拡張機能です。ANSI 互換が必要な場合は使用しないでください。  
  
## <a name="example"></a>例  
  
```C  
// crt_fopen_s.c  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   errno_t err;  
  
   // Open for read (will fail if file "crt_fopen_s.c" does not exist)  
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );  
   if( err == 0 )  
   {  
      printf( "The file 'crt_fopen_s.c' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'crt_fopen_s.c' was not opened\n" );  
   }  
  
   // Open for write   
   err = fopen_s( &stream2, "data2", "w+" );  
   if( err == 0 )  
   {  
      printf( "The file 'data2' was opened\n" );  
   }  
   else  
   {  
      printf( "The file 'data2' was not opened\n" );  
   }  
  
   // Close stream if it is not NULL   
   if( stream )  
   {  
      err = fclose( stream );  
      if ( err == 0 )  
      {  
         printf( "The file 'crt_fopen_s.c' was closed\n" );  
      }  
      else  
      {  
         printf( "The file 'crt_fopen_s.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:  
   int numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen_s.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="see-also"></a>関連項目  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen、_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen、_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
