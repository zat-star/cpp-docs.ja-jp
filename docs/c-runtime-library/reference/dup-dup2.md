---
title: "_dup、_dup2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dup"
  - "_dup2"
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
  - "_dup2"
  - "_dup"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_dup 関数"
  - "_dup2 関数"
  - "dup 関数"
  - "dup2 関数"
  - "ファイル ハンドル [C++], 複製"
  - "ファイル ハンドル [C++], 再割り当て"
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _dup、_dup2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

開いているファイルの 2 つ目のファイル記述子 \(`_dup`\) を作成するか、ファイル記述子 \(`_dup2`\) を再割り当てします。  
  
## 構文  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### パラメーター  
 `fd`, `fd1`  
 開いているファイルを参照するファイル記述子。  
  
 `fd2`  
 任意のファイル記述子。  
  
## 戻り値  
 `_dup` は新しいファイル記述子を返します。  `_dup2` は成功したことを示すために 0 を返します。  エラーが発生した場合、各関数は \-1 を返し、ファイル記述子が無効な場合は `errno` を `EBADF` に設定し、これ以上のファイル識別子を使用できない場合は `EMFILE` に設定します。  ファイル記述子が無効な場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、関数によって無効なパラメーター ハンドラーも開始されます。  
  
 リターン コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_dup` 関数と `_dup2` 関数は、2 つ目のファイル記述子を現在開いているファイルに関連付けます。  これらの関数は、`stdout` のような定義済みファイル記述子を別のファイルに関連付けるために使用できます。  ファイル操作はいずれかのファイル記述子を使用して実行できます。  新しい記述子の作成によって、ファイルに対するアクセス権の種類が影響を受けることはありません。  `_dup` は、指定されたファイルに対して次に使用できるファイル記述子を返します。  `_dup2` は `fd2` に `fd1` と同じファイルを参照するよう強制します。  呼び出し時に `fd2` が開いているファイルに関連付けられている場合は、そのファイルが閉じられます。  
  
 `_dup` と `_dup2` はいずれもファイル記述子をパラメーターとして受け取ります。  これらの関数のいずれかに `(FILE *)` ストリームを渡すには、[\_fileno](../Topic/_fileno.md) を使用します。  `fileno` ルーチンは、指定したストリームに現在関連付けられているファイル記述子を返します。  次の例は、`stderr` \(Stdio.h で `FILE` `*` として定義\) をファイル記述子に関連付ける方法を示しています:  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|  
|----------|------------|  
|`_dup`|\<io.h\>|  
|`_dup2`|\<io.h\>|  
  
 コンソールは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリではサポートされていません。  コンソール \(`stdin`、`stdout`、および `stderr`\) に関連付けられている標準ストリームのハンドルは、C ランタイム関数によって [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリで使用する前に、リダイレクトする必要があります。  互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
  **これはまず stdout に移動します**  
**これは stdout に移動します**  
**data ファイルに含まれるもの:**  
**これは data ファイルに移動します**   
## 参照  
 [下位入出力](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../Topic/_close.md)   
 [\_creat、\_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)