---
title: "fclose、_fcloseall | Microsoft Docs"
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
  - "fclose"
  - "_fcloseall"
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
  - "fclose"
  - "_fcloseall"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fclose 関数"
  - "ストリーム、閉じる"
  - "_fcloseall 関数"
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fclose、_fcloseall
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ストリーム \(`fclose`\) を閉じ、またはすべての開いているストリーム \(`_fcloseall`\) を閉じます。  
  
## 構文  
  
```  
int fclose(   
   FILE *stream   
);  
int _fcloseall( void );  
```  
  
#### パラメーター  
 `stream`  
 `FILE` 構造体へのポインター。  
  
## 戻り値  
 `fclose`、ストリームが正常に閉じた 0 を返します。  `_fcloseall` を 決めるストリームの総数を返します。  エラーを示すどちらの関数を返します。`EOF`。  
  
## 解説  
 `fclose` 関数は `stream`を閉じます。  `stream` が `NULL` の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているように、無効なパラメーター ハンドラーが呼び出されます。  実行の継続 `fclose` は `EINVAL` に `errno` を設定し、`EOF`を返します。  `stream` のポインターがこの関数を呼び出す前に、常にチェックすることをお勧めします。  
  
 エラー コードの詳細については、「[\_doserrno、errno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
 `_fcloseall` 関数は `stdin`、`stdout`の `stderr` 閉じられます \(および、MS\-DOS、`_stdaux` と `_stdprn`を除くすべてのオープン ストリームを\)。  また、`tmpfile`で作成した一時ファイルを閉じ、削除します。  どちらの関数では、すべてが閉じる前にストリームに関連付けられたをフラッシュされますバッファリングされます。  システムが割り当てたバッファーは、ストリームを閉じるときに解放されます。  `setbuf` と `setvbuf` のユーザーが割り当てたバッファーは自動的に解放されません。  
  
 ストリームを閉じるには、これらの関数を使用する場合**注意 :** 基になるファイル記述子とオペレーティング システムのファイル ハンドル \(またはソケット\) 終了、ストリームです。  したがって、ファイルが最初に、ファイル ハンドルやファイル記述子開き、`fclose`と閉じる、またはファイル記述子を閉じるに `_close` を呼び出さないでください; ファイル ハンドルを終了する Win32 関数 `CloseHandle` を呼び出さないでください。  
  
 `fclose` と `_fcloseall` は他のスレッドで干渉から保護するためのコードが含まれています。  `fclose`をロックしないバージョンについては、`_fclose_nolock`を参照してください。  
  
## 必要条件  
  
|関数|必須ヘッダー|  
|--------|------------|  
|`fclose`|\<stdio.h\>|  
|`_fcloseall`|\<stdio.h\>|  
  
 互換性の詳細については、「C ランタイム ライブラリ」の「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。  
  
## 使用例  
 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)"の例を参照してください。  
  
## 同等の .NET Framework 関数  
  
-   [System::IO::BinaryReader::Close](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.close.aspx)  
  
-   [System::IO::BinaryWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.binarywriter.close.aspx)  
  
-   [System::IO::StringReader::Close](https://msdn.microsoft.com/en-us/library/system.io.stringreader.close.aspx)  
  
-   [System::IO::StringWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.stringwriter.close.aspx)  
  
-   [System::IO::Stream::Close](https://msdn.microsoft.com/en-us/library/system.io.stream.close.aspx)  
  
-   [System::IO::StreamReader::Close](https://msdn.microsoft.com/en-us/library/system.io.streamreader.close.aspx)  
  
-   [System::IO::StreamWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.streamwriter.close.aspx)  
  
-   [System::IO::TextReader::Close](https://msdn.microsoft.com/en-us/library/system.io.textreader.close.aspx)  
  
-   [System::IO::TextWriter::Close](https://msdn.microsoft.com/en-us/library/system.io.textwriter.close.aspx)  
  
## 参照  
 [ストリーム入出力](../../c-runtime-library/stream-i-o.md)   
 [\_close](../Topic/_close.md)   
 [\_fdopen、\_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [fflush](../Topic/fflush.md)   
 [fopen、\_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen、\_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)