---
title: "freopen_s、_wfreopen_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfreopen_s"
  - "freopen_s"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "freopen_s"
  - "_tfreopen_s"
  - "_wfreopen_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tfreopen_s 関数"
  - "_wfreopen_s 関数"
  - "ファイル ポインター [C++], 再割り当て"
  - "freopen_s 関数"
  - "tfreopen_s 関数"
  - "wfreopen_s 関数"
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# freopen_s、_wfreopen_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル ポインターを再度割り当てます。  これらのバージョンの [freopen、\_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md) は、「[CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)」の説明にあるとおり、セキュリティが強化されたバージョンです。  
  
## 構文  
  
```  
errno_t freopen(   
   FILE** pFile,  
   const char *path,  
   const char *mode,  
   FILE *stream   
);  
errno_t _wfreopen(   
   FILE** pFile,  
   const wchar_t *path,  
   const wchar_t *mode,  
   FILE *stream   
);  
```  
  
#### パラメーター  
 \[出力\] `pFile`  
 呼び出しが提供するファイル ポインターへのポインター。  
  
 \[入力\] `path`  
 新しいファイル パス。  
  
 \[入力\] `mode`  
 アクセス許可の種類。  
  
 \[入力\] `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 これらの関数はエラー コードを返します。  エラーが発生した場合、元のファイルは閉じられます。  
  
## 解説  
 `freopen_s` 関数は、現在 `stream` に関連付けられたファイルを閉じ、`stream` で指定されたファイルに `path.` を再度関連付けます。`_wfreopen_s` は `_freopen_s` のワイド文字バージョンです。 `path` の `mode` 引数と `_wfreopen_s` 引数はワイド文字列です。  それ以外では、`_wfreopen_s` と `_freopen_s` の動作は同じです。  
  
 `pFile`、`path`、`mode`、または `stream` が `NULL` の場合、または、`path` が空の文字列である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `errno` を `EINVAL` に設定し、`EINVAL` を返します。  
  
### 汎用テキスト ルーチンのマップ  
  
|TCHAR.H のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tfreopen_s`|`freopen_s`|`freopen_s`|`_wfreopen_s`|  
  
 `freopen_s` は、通常、既に開いているファイル `stdin`、`stdout`、および `stderr` のユーザーが指定したファイルへのリダイレクトに使用されます。  `stream` に関連付けられている新しいファイルは、ファイルに要求されるアクセスの種類を指定する文字列である `mode`で次のように開かれます。  
  
 `"r"`  
 読み取り用に開きます。  ファイルが存在しない場合や見つからない場合、`freopen_s` 呼び出しは失敗します。  
  
 `"w"`  
 書き込み用に空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a"`  
 末尾に書き込みができるようにファイルを開きます \(追加モード\)。EOF マーカーを削除せずにファイルに新しいデータを書き込みます。ファイルが存在しない場合は、作成します。  
  
 `"r+"`  
 読み取りと書き込みの両方のモードで開きます。  ファイルが存在している必要があります。  
  
 `"w+"`  
 読み取りと書き込みの両方のモードで空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。  
  
 `"a+"`  
 読み取りと追加の両方のモードでファイルを開きます。追加時には、ファイルに新しいデータを書き込む前に EOF マーカーが削除され、書き込みが終了すると EOF マーカーが復元されます。ファイルが存在しない場合は、作成します。  
  
 既存のファイルを破棄するため、`"w"` と `"w+"` の型は注意して使用します。  
  
 アクセスの種類が `"a"` または `"a+"` の場合にファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。  ファイル ポインターは `fseek` 関数または `rewind` 関数を使用して移動できますが、書き込み操作の前に必ずファイルの終端に戻されます。  したがって、既存のデータは上書きされません。  
  
 `"a"` モードでは、ファイルへの追加の前に EOF マーカーは削除されません。  追加が行われても、MS\-DOS TYPE コマンドでは元の EOF マーカーまでのデータしか表示されず、ファイルに追加されたデータは表示されません。  `"a+"` モードでは、ファイルへの追加の前に EOF マーカーが削除されます。  追加が終了すると、MS\-DOS の TYPE コマンドでファイル内すべてのデータが表示されます。  Ctrl \+ Z EOF マーカーで終了するストリーム ファイルに追加するには、`"a+"` モードを使用する必要があります。  
  
 `"r+",`、`"w+",`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます \(この場合、ファイルは「更新用に開かれる」と言います\)。  ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](../Topic/fsetpos.md)、[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)、または [rewind](../../c-runtime-library/reference/rewind.md) のいずれかの関数を実行する必要があります。  必要に応じて、`fsetpos` 関数または `fseek` 関数には現在位置を指定できます。  上記の値に加え、`mode` 文字列に次の文字の 1 つを追加すると、改行の変換モードを指定できます。  
  
 `t`  
 テキスト \(変換\) モードで開きます。復帰と改行 \(CR\-LF\) の組み合わせは入力時に 1 つの改行 \(LF\) 文字に変換され、LF 文字が出力時に CR\-LF の組み合わせに変換されます。  また、Ctrl \+ Z は入力時に EOF \(end\-of\-file\) 文字として解釈されます。  `"a+"` を使用して読み取りモード、または読み取りおよび書き込みの両方のモードで開かれたファイルでは、ランタイム ライブラリがファイル末尾に Ctrl \+ Z があるかどうかを確認し、削除できる場合は削除します。  この処理が行われる理由は、ファイルの中身を `fseek` 関数および `ftell` 関数で移動するとき、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。  `t` オプションは、Microsoft 拡張機能です。ANSI 互換が必要な場合は使用しないでください。  
  
 `b`  
 バイナリ \(未変換\) モードで開き、前述の変換は抑制されます。  
  
 `t` または `b` を `mode` に指定しないと、既定の変換モードは [\_fmode](../../c-runtime-library/fmode.md) グローバル変数によって定義されます。  `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL` が返されます。  
  
 テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`freopen_s`|\<stdio.h\>|  
|`_wfreopen_s`|\<stdio.h\> または \<wchar.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_freopen_s.c  
// This program reassigns stderr to the file  
// named FREOPEN.OUT and writes a line to that file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   errno_t err;  
   // Reassign "stderr" to "freopen.out":   
   err = freopen_s( &stream, "freopen.out", "w", stderr );  
  
   if( err != 0 )  
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
  
  **正常に再割り当てされました**  
**これは freopen.out ファイルに移動します**   
## 同等の .NET Framework 関数  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [freopen、\_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [\_fileno](../Topic/_fileno.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)