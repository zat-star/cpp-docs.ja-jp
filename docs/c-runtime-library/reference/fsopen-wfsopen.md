---
title: "_fsopen、_wfsopen | Microsoft Docs"
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
  - "_wfsopen"
  - "_fsopen"
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
  - "wfsopen"
  - "fsopen"
  - "tfsopen"
  - "_tfsopen"
  - "_wfsopen"
  - "_fsopen"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fsopen 関数"
  - "_tfsopen 関数"
  - "_wfsopen 関数"
  - "ファイルの共有 [C++]"
  - "ファイル [C++], 開く"
  - "fsopen 関数"
  - "開く (ファイルを), ストリーム"
  - "tfsopen 関数"
  - "wfsopen 関数"
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fsopen、_wfsopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイル共有付きでストリームを開きます。  
  
## 構文  
  
```  
FILE *_fsopen(   
   const char *filename,  
   const char *mode,  
   int shflag   
);  
FILE *_wfsopen(   
   const wchar_t *filename,  
   const wchar_t *mode,  
   int shflag   
);  
```  
  
#### パラメーター  
 `filename`  
 開くファイルの名前。  
  
 `mode`  
 アクセス許可の種類。  
  
 `shflag`  
 許可される共有の種類。  
  
## 戻り値  
 これらの各関数は、ストリームへのポインターを返します。  エラーが発生すると、NULL のポインター値を返します。  `filename` または `mode` が `NULL` であるか、空の文字列である場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、これらの関数は無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、これらの関数は `NULL` を返し、`errno` を `EINVAL` に設定します。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_fsopen` 関数は、`filename` で指定されたファイルをストリームとして開き、モードおよび `shflag` 引数による定義に従って、後続の共有の読み取りまたは書き込み用にファイルを準備します。  `_wfsopen` は `_fsopen` のワイド文字バージョンであり、`_wfsopen` に対する `filename` 引数と `mode` 引数はワイド文字列です。  それ以外では、`_wfsopen` と `_fsopen` の動作は同じです。  
  
 文字列 `mode` は、次の表に示すように、ファイルに要求するアクセスの種類を指定します。  
  
|用語|定義|  
|--------|--------|  
|`"r"`|読み取り用に開きます。  ファイルが存在しない場合や見つからない場合、`_fsopen` 呼び出しは失敗します。|  
|`"w"`|書き込み用に空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|  
|`"a"`|ファイルの末尾への書き込み用にファイルを開きます \(追加モード\)。ファイルが存在しない場合は、まず、ファイルを作成します。|  
|`"r+"`|読み取りと書き込みの両方のモードで開きます。  ファイルが存在している必要があります。|  
|`"w+"`|読み取りと書き込みの両方のモードで空のファイルを開きます。  指定したファイルが既に存在すると、そのファイルの内容は破棄されます。|  
|`"a+"`|読み取りおよび追加用にファイルを開きます。ファイルが存在しない場合は、まず、ファイルを作成します。|  
  
 既存のファイルを破棄するため、`"w"` と `"w+"` の型は注意して使用します。  
  
 アクセスの種類 `"a"` または `"a+"` を使用してファイルを開くと、すべての書き込み操作はファイルの末尾から行われます。  ファイル ポインターは `fseek` 関数または `rewind` 関数を使用して移動できますが、書き込み操作の実行前には必ずファイルの終端に戻されます。  したがって、既存のデータは上書きされません。  `"r+"`、`"w+"`、または `"a+"` のいずれかのアクセスの種類を指定すると、読み取りと書き込みの両方を行うことができます \(この場合、ファイルは「更新用に開かれる」と言います\)。  ただし、読み取りと書き込みを切り替える場合は、その前に [fsetpos](../Topic/fsetpos.md)、[fseek](../../c-runtime-library/reference/fseek-fseeki64.md)、または [rewind](../../c-runtime-library/reference/rewind.md) のいずれかの操作を実行する必要があります。  必要に応じて、`fsetpos` 関数または `fseek` 関数には現在位置を指定できます。  上記の値に加え、`mode` に次の文字の 1 つを追加すると、改行の変換モードやファイル管理を指定できます。  
  
|用語|定義|  
|--------|--------|  
|`t`|ファイルをテキスト \(変換\) モードで開きます。  このモードでは、復帰と改行 \(CR\-LF\) の組み合わせは入力時に 1 つの改行 \(LF\) 文字に変換され、LF 文字は出力時に CR\-LF の組み合わせに変換されます。  また、Ctrl \+ Z は入力時に EOF \(end\-of\-file\) 文字として解釈されます。  読み取りまたは読み取り\/書き込み用にファイルを開いた場合、`_fsopen` はファイル末尾に Ctrl \+ Z があるかどうかを確認し、それを削除できる場合は削除します。  この処理が行われる理由は、CTRL \+ Z で終わるファイル内を `fseek` 関数および `ftell` 関数を使用して移動すると、ファイル末尾付近で `fseek` が正しく動作しないことがあるためです。|  
|`b`|ファイルをバイナリ \(無変換\) モードで開き、前述の変換は行いません。|  
|`S`|キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。|  
|`R`|キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。|  
|`T`|ファイルを一時ファイルとして指定します。  可能な場合、ファイルはディスクにフラッシュされません。|  
|`D`|ファイルを一時ファイルとして指定します。  最後のファイル ポインターが閉じられると、ファイルは削除されます。|  
  
 `t` または `b` を `mode` に指定しない場合、変換モードは既定のモード変数 `_fmode` によって定義されます。  `t` または `b` を引数の先頭に指定すると、エラーが発生して `NULL` が返されます。  テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
 引数 `shflag` は、Share.h で定義されている次のマニフェスト定数のいずれかで構成した定数式です。  
  
|用語|定義|  
|--------|--------|  
|`_SH_COMPAT`|16 ビット アプリケーションの互換モードを設定します。|  
|`_SH_DENYNO`|読み取りおよび書き込みアクセスを許可します。|  
|`_SH_DENYRD`|ファイルへの読み取りアクセスを拒否します。|  
|`_SH_DENYRW`|ファイルへの読み取りおよび書き込みアクセスを拒否します。|  
|`_SH_DENYWR`|ファイルへの書き込みアクセスを拒否します。|  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_tfsopen`|`_fsopen`|`_fsopen`|`_wfsopen`|  
  
## 必要条件  
  
|関数|必須ヘッダー|省略可能なヘッダー|  
|--------|------------|---------------|  
|`_fsopen`|\<stdio.h\>|\<share.h\><br /><br /> `shflag` パラメーター用のマニフェスト定数のため。|  
|`_wfsopen`|\<stdio.h\> または \<wchar.h\>|\<share.h\><br /><br /> `shflag` パラメーター用のマニフェスト定数のため。|  
  
## 使用例  
  
```  
// crt_fsopen.c  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
  
   // Open output file for writing. Using _fsopen allows us to  
   // ensure that no one else writes to the file while we are  
   // writing to it.  
    //  
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )  
   {  
      fprintf( stream, "No one else in the network can write "  
                       "to this file until we are done.\n" );  
      fclose( stream );  
   }  
   // Now others can write to the file while we read it.  
   system( "type outfile" );  
}  
```  
  
  **No one else in the network can write to this file until we are done.**   
## 同等の .NET Framework 関数  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [fclose、\_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [\_fileno](../Topic/_fileno.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、\_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [\_sopen、\_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)