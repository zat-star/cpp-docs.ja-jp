---
title: "_popen、_wpopen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _popen
- _wpopen
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
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
dev_langs: C++
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73c9e19556857c78a530f0a2ac89580ea3fec69c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="popen-wpopen"></a>_popen、_wpopen
パイプを作成し、コマンドを実行します。  
  
> [!IMPORTANT]
>  この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳しくは、「 [/ZW でサポートされない CRT 関数](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)」をご覧ください。  
  
## <a name="syntax"></a>構文  
  
```
FILE *_popen(
const char *command,
const char *mode
);
FILE *_wpopen(
const wchar_t *command,
const wchar_t *mode
);
```  
  
#### <a name="parameters"></a>パラメーター  
 *command*  
 実行するコマンド。  
  
 *モード*  
 返されるストリームのモード。  
  
## <a name="return-value"></a>戻り値  
 作成されたパイプの一方の端に関連付けられているストリームを返します。 パイプのもう一方の端は、開始されたコマンドの標準入力または標準出力に関連付けられます。 エラー発生時には、関数は **NULL** を返します。 *command* または *mode* が Null ポインターの場合、または *mode* が有効なモードでない場合など、エラーが無効なパラメーターである場合は、`errno` は `EINVAL` に設定されます。 有効なモードについては、「解説」を参照してください。  
  
 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。  
  
## <a name="remarks"></a>コメント  
 `_popen` 関数はパイプを作成し、非同期的に指定の文字列 *command* でコマンド プロセッサの開始されたコピーを実行します。 *mode* 文字列では、次のように、要求するアクセスの種類を指定します。  
  
 **"r"**  
 呼び出しプロセスは、返されたストリームを使用して、開始されたコマンドの標準出力を読み取ることができます。  
  
 **"w"**  
 呼び出しプロセスは、返されたストリームを使用して、開始されたコマンドの標準入力に書き込むことができます。  
  
 **"b"**  
 バイナリ モードで開きます。  
  
 **"t"**  
 テキスト モードで開きます。  
  
> [!NOTE]
>  Windows プログラムで使用すると、`_popen` 関数は無効なファイル ポインターを返し、その結果、プログラムは無期限に応答を停止します。 `_popen` は、コンソール アプリケーションで正しく動作します。 入力と出力をリダイレクトする Windows アプリケーションを作成するを参照してください。[リダイレクトされた入出力を子プロセスを作成する](http://msdn.microsoft.com/library/windows/desktop/ms682499)Windows SDK に含まれています。  
  
 `_wpopen` 関数は、`_popen` 関数のワイド文字バージョンです。`_wpopen` 関数の *path* 引数は、ワイド文字列です。 それ以外では、`_wpopen` と `_popen` の動作は同じです。  
  
### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ  
  
|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## <a name="requirements"></a>要件  
  
|ルーチン|必須ヘッダー|  
|-------------|---------------------|  
|`_popen`|\<stdio.h>|  
|`_wpopen`|\<stdio.h> または \<wchar.h>|  
  
 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」をご覧ください。  
  
## <a name="libraries"></a>ライブラリ  
 [C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。  
  
## <a name="example"></a>例  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## <a name="sample-output"></a>出力例  
 この出力は、現在のディレクトリに .c ファイル名拡張子を持つファイルが 1 個だけあると仮定しています。  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## <a name="see-also"></a>関連項目  
 [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)   
 [_pclose](../../c-runtime-library/reference/pclose.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)
