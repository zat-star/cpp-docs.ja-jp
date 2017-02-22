---
title: "_pipe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_pipe"
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
  - "pipe"
  - "_pipe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pipe 関数"
  - "pipe 関数"
  - "パイプ"
  - "パイプ, 作成"
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _pipe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

読み取りおよび書き込み用のパイプを作成します。  
  
> [!IMPORTANT]
>  この API は、[!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行するアプリケーションでは使用できません。  詳細については、「[\/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」を参照してください。  
  
## 構文  
  
```  
  
      int _pipe(  
int *pfds,  
unsigned int psize,  
int textmode   
);  
```  
  
#### パラメーター  
 `pfds`\[2\]  
 読み取りおよび書き込みファイル記述子を格納する配列。  
  
 `psize`  
 予約するメモリの量。  
  
 `textmode`  
 ファイル モード。  
  
## 戻り値  
 処理が正常に終了した場合は 0 を返します。  エラーを示す –1 を返します。  エラーの場合、`errno` は、これらの値のいずれかに設定されます。  
  
-   `EMFILE`、これ以上のファイル記述子が使用できないことを示します。  
  
-   `ENFILE`、ファイル システム テーブルのオーバーフローを示します。  
  
-   `EINVAL`、配列 `pfds` が null ポインターであるか、または `textmode` に対して無効な値が渡されたことを示します。  
  
 リターン コードの詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 解説  
 `_pipe` 関数は、プログラムの他のプログラムに情報を渡すために使用する人為的な I\/O チャネルである*パイプ*を作成します。  パイプは、ファイル ポインター、ファイル記述子、またはその両方を持つファイルに似ており、標準ライブラリの入出力関数を使用して読み取りや書き込みを行うことができます。  ただし、パイプは、特定のファイルまたはデバイスを表しません。  代わりに、プログラム自体のメモリに関係なく、オペレーティング システムによって完全に制御されるメモリの一時的なストレージを表します。  
  
 `_pipe` は `_open` に似ていますが、読み取りおよび書き込み用のパイプを開き、ファイル記述子を 1 つではなく 2 つ返します。  プログラムはパイプの両側を使用するか、または必要としない一方の側のパイプを閉じることができます。  たとえば、Windows のコマンド プロセッサは `PROGRAM1 | PROGRAM2` などのコマンドを実行するときにパイプを作成します。  
  
 `PROGRAM1` の標準出力記述子は、パイプの書き込み記述子に添付されます。  `PROGRAM2` の標準入力記述子は、パイプの読み取り記述子に添付されます。  これにより、他のプログラムに情報を渡すための一時ファイルを作成する必要がなくなります。  
  
 `_pipe` 関数は `pfds` 引数でパイプに 2 つのファイル記述子を返します。  要素 `pfds`\[0\] には、読み取り記述子が含まれ、要素 `pfds`\[1\] には書き込み記述子が含まれます。  パイプのファイル記述子は、他のファイル記述子と同様に使用されます。\(低水準入出力関数 `_read` と `_write` はパイプからの読み取りやパイプへの書き込みができます\)。パイプの末尾の状態を検出するには、`_read` 要求が、読み取ったバイト数として 0 を返すかどうかをチェックします。  
  
 `psize` 引数は、パイプに予約するメモリの量をバイト数で指定します。  `textmode` 引数は、パイプの変換モードを指定します。  マニフェスト定数 `_O_TEXT` は、テキスト変換を指定し、定数 `_O_BINARY` はバイナリ変換を指定します\(テキスト モードとバイナリ モードの詳細については、「[fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)」を参照してください\)。`textmode` 引数が 0 の場合、`_pipe` は既定のモード変数 [\_fmode](../../c-runtime-library/fmode.md) により指定されている既定の変換モードを使用します。  
  
 マルチスレッド プログラムでは、ロックは実行されません。  返されたファイル記述子が新しく開き、`_pipe` 呼び出しが完了するまでスレッドでは参照できません。  
  
 `_pipe` の関数を使用して親プロセスと子プロセスの間で通信するには、各プロセスがパイプで開いている記述子を 1 つだけ持つことが必要です。  記述子は正反対である必要があります。親が開いている読み取り記述子を持つ場合、子は開いている書き込み記述子を持つ必要があります。  これを実行する最も容易な方法は、`OR` \(  `|`\) を `textmode` モードで `_O_NOINHERIT` フラグに対して実行することです。  次に、`_dup` または `_dup2` を使用して、子に渡すパイプ記述子の継承可能なコピーを作成します。  元の記述子を終了し、子プロセスを生成します。  生成の呼び出しから制御が戻ったら、親プロセスの重複記述子を閉じます。  詳細については、この記事で後述する例 2 を参照してください。  
  
 Windows オペレーティング システムでは、すべての記述子が閉じたときパイプは破棄されます。\(パイプですべての読み取り記述子が閉じられた場合、パイプへの書き込みによりエラーが発生します\)。パイプでのすべての読み取り操作と書き込み操作は、I\/O 要求を完了するために十分なデータまたは十分なバッファー領域が確保されるまで、待機状態になります。  
  
## 必要条件  
  
|ルーチン|必須ヘッダー|オプション ヘッダー|  
|----------|------------|----------------|  
|`_pipe`|\<io.h\>|\<fcntl.h\>,1 \<errno.h\>2|  
  
 1 は `_O_BINARY` 定義と `_O_TEXT` 定義向け。  
  
 2 は `errno` 定義。  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## 例 1  
  
```  
// crt_pipe.c  
/* This program uses the _pipe function to pass streams of  
 * text to spawned processes.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <io.h>  
#include <fcntl.h>  
#include <process.h>  
#include <math.h>  
  
enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */  
#define NUMPROBLEM 8  
  
int main( int argc, char *argv[] )  
{  
  
   int fdpipe[2];  
   char hstr[20];  
   int pid, problem, c;  
   int termstat;  
  
   /* If no arguments, this is the spawning process */  
   if( argc == 1 )  
   {  
  
      setvbuf( stdout, NULL, _IONBF, 0 );  
  
      /* Open a set of pipes */  
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )  
          exit( 1 );  
  
      /* Convert pipe read descriptor to string and pass as argument   
       * to spawned program. Program spawns itself (argv[0]).  
       */  
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );  
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],   
            hstr, NULL ) ) == -1 )  
          printf( "Spawn failed" );  
  
      /* Put problem in write pipe. Since spawned program is   
       * running simultaneously, first solutions may be done   
       * before last problem is given.  
       */  
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)  
      {  
  
         printf( "Son, what is the square root of %d?\n", problem );  
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );  
  
      }  
  
      /* Wait until spawned program is done processing. */  
      _cwait( &termstat, pid, WAIT_CHILD );  
      if( termstat & 0x0 )  
         printf( "Child failed\n" );  
  
      _close( fdpipe[READ] );  
      _close( fdpipe[WRITE] );  
  
   }  
  
   /* If there is an argument, this must be the spawned process. */  
   else  
   {  
  
      /* Convert passed string descriptor to integer descriptor. */  
      fdpipe[READ] = atoi( argv[1] );  
  
      /* Read problem from pipe and calculate solution. */  
      for( c = 0; c < NUMPROBLEM; c++ )  
      {  
  
        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );  
        printf( "Dad, the square root of %d is %3.2f.\n",  
                 problem, sqrt( ( double )problem ) );  
  
      }  
   }  
}  
```  
  
## 出力例  
  
```  
Son, what is the square root of 1000?  
Son, what is the square root of 2000?  
Son, what iDad, the square root of 1000 is 31.62.  
Dad, the square root of 2000 is 44.72.  
s the square root of 3000?  
Dad, the square root of 3000 is 54.77.  
Son, what is the square root of 4000?  
Dad, the square root of 4000 is 63.25.  
Son, what is the square root of 5000?  
Dad, the square root of 5000 is 70.71.  
Son, what is the square root of 6000?  
SonDad, the square root of 6000 is 77.46.  
, what is the square root of 7000?  
Dad, the square root of 7000 is 83.67.  
Son, what is the square root of 8000?  
Dad, the square root of 8000 is 89.44.  
```  
  
## 例 2  
 これは基本的なフィルター アプリケーションです。  これは、生成されたアプリケーションの標準出力をフィルターに指定するパイプを作成した後、アプリケーションの crt\_pipe\_beeper を生成します。  フィルターは ASCII 7 \(ビープ音\) 文字を削除します。  
  
```  
// crt_pipe_beeper.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   int   i;  
   for(i=0;i<10;++i)  
      {  
         printf("This is speaker beep number %d...\n\7", i+1);  
      }  
   return 0;  
}  
```  
  
 実際のフィルター アプリケーション:  
  
```  
// crt_pipe_BeepFilter.C  
// arguments: crt_pipe_beeper.exe  
  
#include <windows.h>  
#include <process.h>  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
#define   OUT_BUFF_SIZE 512  
#define   READ_FD 0  
#define   WRITE_FD 1  
#define   BEEP_CHAR 7  
  
char szBuffer[OUT_BUFF_SIZE];  
  
int Filter(char* szBuff, ULONG nSize, int nChar)  
{  
   char* szPos = szBuff + nSize -1;  
   char* szEnd = szPos;  
   int nRet = nSize;  
  
   while (szPos > szBuff)  
   {  
      if (*szPos == nChar)  
         {  
            memmove(szPos, szPos+1, szEnd - szPos);  
            --nRet;  
         }  
      --szPos;  
   }  
   return nRet;  
}  
  
int main(int argc, char** argv)  
{  
   int nExitCode = STILL_ACTIVE;  
   if (argc >= 2)  
   {  
      HANDLE hProcess;  
      int fdStdOut;  
      int fdStdOutPipe[2];  
  
      // Create the pipe  
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)  
         return   1;  
  
      // Duplicate stdout file descriptor (next line will close original)  
      fdStdOut = _dup(_fileno(stdout));  
  
      // Duplicate write end of pipe to stdout file descriptor  
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)  
         return   2;  
  
      // Close original write end of pipe  
      _close(fdStdOutPipe[WRITE_FD]);  
  
      // Spawn process  
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],   
       (const char* const*)&argv[1]);  
  
      // Duplicate copy of original stdout back into stdout  
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)  
         return   3;  
  
      // Close duplicate copy of original stdout  
      _close(fdStdOut);  
  
      if(hProcess)  
      {  
         int nOutRead;  
         while   (nExitCode == STILL_ACTIVE)  
         {  
            nOutRead = _read(fdStdOutPipe[READ_FD],   
             szBuffer, OUT_BUFF_SIZE);  
            if(nOutRead)  
            {  
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);  
               fwrite(szBuffer, 1, nOutRead, stdout);  
            }  
  
            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))  
               return 4;  
         }  
      }  
   }  
   return nExitCode;  
}  
```  
  
## 出力  
  
```  
This is speaker beep number 1...  
This is speaker beep number 2...  
This is speaker beep number 3...  
This is speaker beep number 4...  
This is speaker beep number 5...  
This is speaker beep number 6...  
This is speaker beep number 7...  
This is speaker beep number 8...  
This is speaker beep number 9...  
This is speaker beep number 10...  
```  
  
## 同等の .NET Framework 関数  
 使用できません。標準 C 関数を呼び出すには、`PInvoke` を使用します。詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。  
  
## 参照  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [\_open、\_wopen](../../c-runtime-library/reference/open-wopen.md)