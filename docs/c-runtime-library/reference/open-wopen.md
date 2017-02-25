---
title: "_open、_wopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_open"
  - "_wopen"
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
  - "_wopen"
  - "_topen"
  - "_open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_open 関数"
  - "_topen 関数"
  - "_wopen 関数"
  - "ファイル [C++], 開く"
  - "open 関数"
  - "開く (ファイルを), ファイル I/O"
  - "topen 関数"
  - "wopen 関数"
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
caps.latest.revision: 31
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 31
---
# _open、_wopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルを開きます。  セキュリティが強化されたバージョンを使用できるようになったため、これらの関数は推奨されていません。「[\_sopen\_s、\_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md)」を参照してください。  
  
## 構文  
  
```  
int _open(  
   const char *filename,  
   int oflag [,  
   int pmode]   
);  
int _wopen(  
   const wchar_t *filename,  
   int oflag [,  
   int pmode]   
);  
```  
  
#### パラメーター  
 `filename`  
 ファイル名。  
  
 `oflag`  
 許可される操作の種類。  
  
 `pmode`  
 アクセス許可モード。  
  
## 戻り値  
 これらの各関数は、開かれたファイルのファイル記述子を返します。  戻り値 \-1 はエラーを示します。その場合、`errno` は次の値のいずれかに設定されます。  
  
 `EACCES`  
 読み取り専用ファイルを書き込み用に開こうとしたか、指定された操作がファイルの共有モードで許可されていないか、指定されたパスがディレクトリです。  
  
 `EEXIST`  
 `_O_CREAT` および `_O_EXCL` フラグが指定されましたが、`filename` が既に存在します。  
  
 `EINVAL`  
 `oflag` または `pmode` 引数が無効です。  
  
 `EMFILE`  
 ファイル記述子をこれ以上使用できません \(開かれているファイルが多すぎます\)。  
  
 `ENOENT`  
 ファイルまたはパスが見つかりません。  
  
 リターン コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_open` 関数は、`filename` で指定されたファイルを開き、`oflag` で指定されたように読み取りまたは書き込み用にファイルを準備します。  `_wopen` 関数は、`_open` 関数のワイド文字バージョンです。`filename` 関数の引数 `_wopen` は、ワイド文字列です。  それ以外では、`_wopen` と `_open` の動作は同じです。  
  
### 汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|\_UNICODE および \_MBCS が未定義の場合|\_MBCS が定義されている場合|\_UNICODE が定義されている場合|  
|-------------------|----------------------------------|-----------------------|--------------------------|  
|`_topen`|`_open`|`_open`|`_wopen`|  
  
 `oflag` は、\<fcntl.h\> で定義されている次のマニフェスト定数または定数の組み合わせの 1 つ以上で構成される整数式です。  
  
 `_O_APPEND`  
 書き込み操作の前に、毎回、ファイル ポインターをファイルの末尾に移動します。  
  
 `_O_BINARY`  
 ファイルをバイナリ \(無変換\) モードで開きます。  \(バイナリ モードの詳細については、「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」を参照してください\)。  
  
 `_O_CREAT`  
 ファイルを作成し、書き込み用に開きます。  `filename` で指定されたファイルが存在する場合は無効です。  `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT` &#124; `_O_SHORT_LIVED`  
 ファイルを一時ファイルとして作成し、可能な場合は、ディスクにフラッシュしません。  `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT` &#124; `_O_TEMPORARY`  
 ファイルを一時ファイルとして作成します。最後のファイル記述子が閉じられると、ファイルは削除されます。  `pmode` が指定された場合は `_O_CREAT` 引数が必要です。  
  
 `_O_CREAT` &#124; `_O_EXCL`  
 `filename` で指定されたファイルが存在する場合、エラー値を返します。  `_O_CREAT` と共に使用された場合にのみ適用されます。  
  
 `_O_NOINHERIT`  
 共有ファイル記述子の作成を禁止します。  
  
 `_O_RANDOM`  
 キャッシュがディスクからのランダム アクセスに最適化されるように指定します。ただし、ランダム アクセスに限定されるわけではありません。  
  
 `_O_RDONLY`  
 読み取り専用でファイルを開きます。  `_O_RDWR` または `_O_WRONLY` と共に指定することはできません。  
  
 `_O_RDWR`  
 読み取りと書き込みの両方のモードでファイルを開きます。  `_O_RDONLY` または `_O_WRONLY` と共に指定することはできません。  
  
 `_O_SEQUENTIAL`  
 キャッシュがディスクからのシーケンシャル アクセスに最適化されるように指定します。ただし、シーケンシャル アクセスに限定されるわけではありません。  
  
 `_O_TEXT`  
 ファイルをテキスト \(変換\) モードで開きます。  \(詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」および「[fopen](../../c-runtime-library/reference/fopen-wfopen.md)」を参照してください\)。  
  
 `_O_TRUNC`  
 ファイルを開き、長さゼロに切り詰めます。ファイルに書き込みアクセス許可が必要です。  `_O_RDONLY` と共に指定することはできません。  `_O_TRUNC` を `_O_CREAT` と共に使用すると、既存のファイルが開かれるか、新しいファイルが作成されます。  
  
> [!NOTE]
>  `_O_TRUNC` フラグによって、指定したファイルの内容は破棄されます。  
  
 `_O_WRONLY`  
 書き込み専用でファイルを開きます。  `_O_RDONLY` または `_O_RDWR` と共に指定することはできません。  
  
 `_O_U16TEXT`  
 Unicode UTF\-16 モードでファイルを開きます。  
  
 `_O_U8TEXT`  
 Unicode UTF\-8 モードでファイルを開きます。  
  
 `_O_WTEXT`  
 Unicode モードでファイルを開きます。  
  
 ファイル アクセス モードを指定するには、`_O_RDONLY`、`_O_RDWR`、または `_O_WRONLY` を指定する必要があります。  アクセス モードに既定値はありません。  
  
 ファイルを読み取り用に開くために `_O_WTEXT` が使用された場合、`_open` によってファイルの冒頭部が読み取られ、バイト オーダー マーク \(BOM\) がチェックされます。  BOM がある場合、ファイルは BOM に応じて UTF\-8 または UTF\-16LE として扱われます。  BOM がない場合、ファイルは ANSI として扱われます。  `_O_WTEXT` を使用してファイルが書き込み用に開かれた場合は、UTF\-16 が使用されます。  以前の設定またはバイト オーダー マークに関係なく、`_O_U8TEXT` が使用された場合はファイルは常に UTF\-8 として開かれ、`_O_U16TEXT` が使用された場合はファイルは常に UTF\-16 として開かれます。  
  
 `_O_WTEXT`、`_O_U8TEXT`、または `_O_U16TEXT` を使用してファイルが Unicode モードで開かれると、Input 関数によって、ファイルから読み取られたデータは `wchar_t` 型として格納された UTF\-16 データに変換されます。  Unicode モードで開かれたファイルに書き込む関数は、`wchar_t` 型として格納された UTF\-16 データがバッファーに含まれていると想定します。  ファイルが UTF\-8 としてエンコードされている場合、UTF\-16 データは書き込まれるときに UTF\-8 に変換され、ファイルの UTF\-8 でエンコードされた内容は読み取られるときに UTF\-16 に変換されます。  Unicode モードで奇数バイトの読み取りまたは書き込みを試みると、パラメーター検証エラーが発生します。  UTF\-8 としてプログラムに格納されたデータを読み取るか書き込む場合は、Unicode モードではなくテキストまたはバイナリ ファイル モードを使用します。  必要なエンコード変換は各自が行う必要があります。  
  
 `_open` は、`_O_WRONLY|_O_APPEND` \(追加モード\) および `_O_WTEXT`、`_O_U16TEXT`、または `_O_U8TEXT` を使用して呼び出された場合、最初に読み取りおよび書き込み用にファイルを開き、BOM を読み取り、次に書き込み専用で再度開こうとします。  読み取りおよび書き込み用にファイルを開くのに失敗した場合、書き込み専用でファイルを開き、Unicode モード設定の既定値を使用します。  
  
 `oflag` 引数を構成するために複数のマニフェスト定数が使用される場合、定数はビットごとの OR 演算子を使用して組み合わされます \(                       `|` を押します\)。  バイナリ モードとテキスト モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。  
  
 `pmode` が指定された場合にのみ `_O_CREAT` 引数が必要です。  ファイルが既に存在する場合、`pmode` は無視されます。  それ以外の場合は、`pmode` によってファイルのアクセス許可の設定が指定されます。これは、新しいファイルが最初に閉じられたときに設定されます。  `_open` では、アクセス許可が設定される前に、現在のファイル アクセス許可マスクが `pmode` に適用されます。  \(詳細については、「[\_umask](../../c-runtime-library/reference/umask.md)」を参照してください\)。`pmode` は、\<sys\\stat.h\> で定義されている次のマニフェスト定数のいずれか、または両方が含まれた整数式です。  
  
 `_S_IREAD`  
 読み取りのみが許可されます。  
  
 `_S_IWRITE`  
 書き込みが許可されます。  \(実際には、読み取りと書き込みが許可されます\)。  
  
 `_S_IREAD`  `|`  `_S_IWRITE`  
 読み取りと書き込みが許可されます。  
  
 両方の定数が指定されると、これらはビットごとの OR 演算子を使用して組み合わされます \(                       `|` を押します\)。  Windows では、すべてのファイルは読み取り可能です。書き込み専用のアクセス許可は使用できません。  したがって、`_S_IWRITE` モードと `_S_IREAD` `|` `_S_IWRITE` モードは等価です。  
  
 `_S_IREAD` と `_S_IWRITE` の組み合わせ以外の値が `pmode` に対して指定された場合 \(別のオペレーティング システムで有効な `pmode` が指定されている場合でも\)、または許可された `oflag` 値以外の値が指定された場合、この関数はアサーションをデバッグ モードで生成し、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。  実行の継続が許可された場合、この関数は \-1 を返し、`errno` を `EINVAL` に設定します。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_open`|\<io.h\>|\<fcntl.h\>、\<sys\\types.h\>、\<sys\\stat.h\>|  
|`_wopen`|\<io.h\> または \<wchar.h\>|\<fcntl.h\>、\<sys\\types.h\>、\<sys\\stat.h\>|  
  
 `_open` および `_wopen` は Microsoft 拡張機能です。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 使用例  
  
```  
// crt_open.c  
// compile with: /W3  
/* This program uses _open to open a file  
 * named CRT_OPEN.C for input and a file named CRT_OPEN.OUT  
 * for output. The files are then closed.  
 */  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int fh1, fh2;  
  
   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996  
   // Note: _open is deprecated; consider using _sopen_s instead  
   if( fh1 == -1 )  
      perror( "Open failed on input file" );  
   else  
   {  
      printf( "Open succeeded on input file\n" );  
      _close( fh1 );  
   }  
  
   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |   
                            _S_IWRITE ); // C4996  
   if( fh2 == -1 )  
      perror( "Open failed on output file" );  
   else  
   {  
      printf( "Open succeeded on output file\n" );  
      _close( fh2 );  
   }  
}  
```  
  
## 出力  
  
```  
Open succeeded on input file  
Open succeeded on output file  
```  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod、\_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_close](../Topic/_close.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_dup、\_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_sopen、\_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)